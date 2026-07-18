# Technology Stack Reference

## Overview

| Layer | Technology | Version | Purpose |
|---|---|---|---|
| Backend Framework | Laravel | 13 (PHP 8.5+) | MVC web application framework |
| Programming Language | PHP | 8.5+ | Server-side scripting |
| Database | PostgreSQL | 16 | Relational database with JSONB, serialisable isolation |
| Frontend Templating | Blade | — | Laravel's built-in templating engine |
| CSS Framework | TailwindCSS | 3.x+ | Utility-first responsive styling |
| JavaScript Framework | Alpine.js | 3.x+ | Lightweight reactive UI components |
| Build Tool | Vite | 5.x+ | Asset bundling and HMR |
| Web Server | Nginx | — | Reverse proxy and static file serving |
| Operating System | Linux (CachyOS) | Arch-based | Development and deployment environment |
| Authentication | Laravel Fortify | 1.x | Session-based authentication backend |
| Email (Development) | Mailtrap | — | SMTP email sandbox for testing |
| Email (Production) | SMTP (Gmail/Postmark) | — | Real email delivery via queue |
| Testing | PHPUnit | — | Unit and integration testing |

---

## Backend: Laravel 13

### Why Laravel

| Factor | Justification |
|---|---|
| MVC Architecture | Clear separation of concerns (Model-View-Controller) suitable for academic projects |
| Eloquent ORM | Active Record implementation maps cleanly to the PostgreSQL schema (time_slots, users, replacement_requests) |
| Built-in Mail System | `Mail` facade + `Mailable` classes + queue integration — no third-party email package needed |
| Queue Support | Database queue driver for async email dispatch without Redis/Beanstalkd |
| Blade Templating | Server-side rendering with component slots, no client-side framework required |
| Artisan CLI | Rapid scaffolding of models, migrations, mailables, and controllers |
| Fortify | Headless authentication with session management, rate limiting, and two-factor support |
| Mature Ecosystem | Largest PHP framework community, extensive documentation, long-term support |
| FOSS | Zero licensing cost — aligned with academic/open-source philosophy |

### Key Packages

| Package | Purpose |
|---|---|
| `laravel/fortify` | Authentication backend (login, registration, session management) |
| `laravel/tinker` | Interactive REPL for quick testing and debugging |
| `livewire/livewire` | Dynamic UI components (optional — for approval dashboard interactivity) |

### Not Used (Justification)

| Package | Reason for Exclusion |
|---|---|
| Pusher / WebSockets | In-app notifications explicitly out of scope — email-only |
| Laravel Nova | Commercial product — not required for FYP scope |
| Laravel Sanctum | API tokens not needed — session-based auth only |
| Redis | Queue driver defaults to database — sufficient for FYP email volume |
| Livewire (if not used) | Alpine.js alone sufficient for interactive elements |

---

## Database: PostgreSQL 16

### Why PostgreSQL over MySQL

| Feature | How It Serves This Project |
|---|---|
| Serializable Isolation | Supports true serialisable transaction isolation for OCC validation — MySQL's REPEATABLE READ allows phantom reads under certain conditions |
| JSONB Data Type | Flexible slot metadata storage without schema migration |
| Row-Level Security (RLS) | Policy-based row filtering for RBAC at the database level |
| `SKIP LOCKED` | Safe queue polling for FCFS approval dashboard — skip rows locked by other transactions |
| Version Column Support | Integer version column for OCC — UPDATE ... SET version = version + 1 WHERE version = :old_version |
| Rich Indexing | Partial indexes, BRIN indexes for timestamp-range queries on time_slots |
| ACID Compliance | Full transaction guarantees for slot state transitions |
| FOSS | No licensing cost |

### Key Schema Design Principles

- `time_slots` table with integer `version` column for OCC
- `replacement_requests` table with state machine (available → pending → occupied → rejected)
- `users` table with `role` enum (student / lecturer / programme_leader)
- Composite unique constraints preventing double-booking at the slot level
- Foreign keys from requests → slot and requests → requester

### Database Queue for Emails

```php
// config/queue.php
'default' => env('QUEUE_CONNECTION', 'database'),
```

The `jobs` table stores outgoing email jobs. The queue worker processes them asynchronously:

```bash
php artisan queue:work --queue=emails
```

---

## Frontend: Blade + TailwindCSS + Alpine.js

### Why This Combination

| Technology | Role | Alternative Rejected |
|---|---|---|
| Blade | Server-side HTML rendering with layout inheritance and components | React/Vue (overkill for server-rendered app with modest interactivity) |
| TailwindCSS | Utility-first responsive CSS — consistent design without writing custom CSS | Bootstrap (opinionated, heavier) |
| Alpine.js | Lightweight reactive UI for interactive elements (dropdowns, modals, toggles) | jQuery (outdated paradigm), Vue/React (too heavy) |

### Component Architecture

```
resources/views/
├── layouts/
│   └── app.blade.php          # Main layout (nav, sidebar, footer)
├── components/
│   ├── slot-grid.blade.php     # Matrix intersection time-slot grid
│   ├── slot-cell.blade.php     # Individual slot with colour-coded state
│   └── approval-queue.blade.php # FCFS queue table with Alpine.js sorting
├── livewire/                   # (if Livewire used)
│   └── approval-dashboard.php  # Real-time queue management
└── emails/
    ├── replacement-submitted.blade.php
    ├── replacement-approved.blade.php
    └── replacement-rejected.blade.php
```

### Vite Configuration

```js
// vite.config.js
export default defineConfig({
    plugins: [
        laravel({
            input: ['resources/css/app.css', 'resources/js/app.js'],
            refresh: true,
        }),
    ],
});
```

**Build command for production:**
```bash
npm run build
```

---

## Email System

### Architecture

```
[Lecturer submits request]
        │
        ▼
[Controller: ReplacementRequestController]
        │
        ▼
[Mail::to($pl->email)->queue(new ReplacementRequestSubmitted($request))]
        │
        ▼
[Database Queue (jobs table)]
        │
        ▼
[Queue Worker: php artisan queue:work]
        │
        ▼
[SMTP Transport]
        │
        ├── Dev: Mailtrap (mailtrap.io)
        └── Prod: Gmail / Postmark / Mailgun
```

### Mailtrap Setup (Development)

```env
MAIL_MAILER=smtp
MAIL_HOST=smtp.mailtrap.io
MAIL_PORT=2525
MAIL_USERNAME=your_mailtrap_username
MAIL_PASSWORD=your_mailtrap_password
MAIL_ENCRYPTION=tls
MAIL_FROM_ADDRESS=noreply@tarc.edu.my
MAIL_FROM_NAME="TARUMT Class Replacement System"
```

### Mailable Classes

| Class | Trigger | Recipient |
|---|---|---|
| `ReplacementRequestSubmitted` | Lecturer submits request | Programme Leader |
| `ReplacementRequestApproved` | PL approves request | Requesting Lecturer |
| `ReplacementRequestRejected` | PL rejects request (with reason) | Requesting Lecturer |

---

## Web Server: Nginx

### Site Configuration (Production)

```nginx
server {
    listen 80;
    server_name class-replacement.tarc.edu.my;
    root /var/www/class-replacement-system/public;

    index index.php;

    location / {
        try_files $uri $uri/ /index.php?$query_string;
    }

    location ~ \.php$ {
        fastcgi_pass unix:/var/run/php/php8.5-fpm.sock;
        fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
        include fastcgi_params;
    }

    location ~ /\.ht {
        deny all;
    }
}
```

---

## Development Environment

### OS: Linux CachyOS (Arch-based)

| Tool | Command |
|---|---|
| PHP + Extensions | `sudo pacman -S php php-pgsql php-pdo php-fpm php-intl php-xml php-mbstring php-curl` |
| Composer | `sudo pacman -S composer` |
| PostgreSQL | `sudo pacman -S postgresql` → `sudo -u postgres initdb -D /var/lib/postgres/data` → `sudo systemctl start postgresql` |
| Node.js + npm | `sudo pacman -S nodejs npm` |
| Nginx | `sudo pacman -S nginx` |
| Laravel Installer | `composer global require laravel/installer` |

### Quick Start Commands

```bash
# Clone and setup
cd ~/Desktop/tarumt/degree/y3s1/BMCS3404\ PROJECT\ I\ \(4\)/class-replacement-system
composer install
cp .env.example .env

# Generate app key
php artisan key:generate

# Create PostgreSQL database
sudo -u postgres createdb class_replacement
sudo -u postgres psql -c "CREATE USER your_username WITH PASSWORD 'your_password';"
sudo -u postgres psql -c "GRANT ALL PRIVILEGES ON DATABASE class_replacement TO your_username;"

# Update .env with DB credentials, then:
php artisan migrate

# Email testing (log driver)
php artisan tinker --execute="Mail::raw('Testing', function(\$m) { \$m->to('test@tarc.edu.my')->subject('Test'); });"

# View logged email
tail storage/logs/laravel.log
```

### Queue Worker

```bash
# Start queue worker for email dispatch
php artisan queue:work --queue=emails
```

---

## Deployment Checklist

| Step | Command / Action |
|---|---|
| Install dependencies | `composer install --no-dev --optimize-autoloader` |
| Build assets | `npm install && npm run build` |
| Set environment | `APP_ENV=production`, `APP_DEBUG=false` |
| Cache config | `php artisan config:cache` |
| Cache routes | `php artisan route:cache` |
| Cache views | `php artisan view:cache` |
| Run migrations | `php artisan migrate --force` |
| Set permissions | `chmod -R 775 storage bootstrap/cache` |
| Configure Nginx | Use site config above, `sudo systemctl reload nginx` |
| Start queue worker | Set up Supervisor to run `php artisan queue:work` persistently |
| Switch email | Update `.env` with production SMTP credentials |
| SSL | `sudo certbot --nginx -d class-replacement.tarc.edu.my` |

---

## References

- Laravel 13 Documentation. (2026). *Mail*. https://laravel.com/docs/11.x/mail
- Laravel 13 Documentation. (2026). *Queues*. https://laravel.com/docs/11.x/queues
- PostgreSQL 16 Documentation. (2026). *Serializable Isolation Level*. https://www.postgresql.org/docs/16/transaction-iso.html
- PostgreSQL 16 Documentation. (2026). *Row Security Policies*. https://www.postgresql.org/docs/16/ddl-rowsecurity.html
- TailwindCSS Documentation. (2026). https://tailwindcss.com/docs
- Alpine.js Documentation. (2026). https://alpinejs.dev/docs
- Mailtrap Documentation. (2026). *SMTP Configuration*. https://mailtrap.io/blog/smtp-settings/
- Nginx Documentation. (2026). *PHP FastCGI*. https://nginx.org/en/docs/http/ngx_http_fastcgi_module.html
