# Project Proposal Reference

## Project Title

TARUMT Class Replacement System: Cross-Cohort Schedule Synchronisation Module

## Student Information

- **Student ID:** 25SMR10186
- **Student Name:** Poong Foo Jing
- **Programme:** Bachelor of Information Technology (Honours) in Software Systems Development (RSD)
- **Faculty:** Faculty of Computing and Information Technology (FOCS)
- **Campus:** TAR UMT Sabah
- **Supervisor:** Mr. Lim Jia Zheng
- **Moderator:** Ms. Teng Nga Sing

## Project Team

| Role | Name |
|---|---|
| Developer / Investigator | Poong Foo Jing |
| Supervisor | Mr. Lim Jia Zheng |
| Moderator | Ms. Teng Nga Sing |
| Domain Expert (FOCS PL) | Pn. Surayaini Binti Basri |
| Domain Expert (FOCS PL) | En. Mohd Nur Rahmat Bin Mohd Taat |

## Problem Statement

Timetabling at TARUMT Sabah FOCS is structured around fixed cohort-specific schedules. When a lecturer is absent or a class must be rescheduled, the Programme Leader (PL) must manually coordinate across multiple stakeholders to find a suitable replacement slot. This manual process involves cross-referencing lecturer availability, cohort timetables, and room capacity through email threads and printed timetables — a process that is time-consuming, error-prone, and lacks real-time visibility.

Existing timetabling solutions (such as aSc Timetables, FET, and Unitime) focus on *initial timetable generation* at the start of a semester but do not address *ad-hoc cross-cohort replacement* during the semester. No known system combines millisecond-precision Optimistic Concurrency Control (OCC) for slot reservation with a First-Come-First-Served (FCFS) approval queue and cohort-aware matrix intersection.

## Objectives

1. **Matrix Intersection Engine** — To develop an algorithm that computes the intersection of Lecturer availability ∩ Cohort 1 timetable ∩ Cohort 2 timetable ∩ Room capacity to produce all valid replacement slots in real time.

2. **Optimistic Concurrency Control (OCC)** — To implement a millisecond-precision slot validation mechanism using the integer version column pattern, preventing double-booking without pessimistic row-level locks.

3. **FCFS Digital Approval Queue** — To build a Programme Leader dashboard that displays all pending replacement requests chronologically with one-click approve/reject and automated email notification.

4. **Role-Based Access Control (RBAC)** — To enforce three-tier access: Student (view-only), Lecturer (create/submit/edit own pending requests), Programme Leader (hybrid: full lecturer rights + queue management).

5. **Notification (Email)** — To dispatch email notifications (Laravel Mail + SMTP queue) on submission, approval, and rejection. In-app notifications explicitly out of scope.

## Scope

### In Scope

- Lecturer dashboard for initiating replacement requests
- Matrix Intersection Algorithm for slot suggestion
- OCC-based slot validation with version column pattern
- FCFS approval queue for Programme Leaders
- Role-based access control (Student / Lecturer / PL)
- Email notifications for submission, approval, and rejection
- PostgreSQL database with slot state machine (Available → Pending → Reserved → Occupied)
- Seed data: 14 lecturers across 3 departments (DCIT: 9L + 2PL, DACB: 2, DSSH: 1), 14 cohorts (11 FOCS + 3 FAFB), 23 Block B rooms with capacity and type metadata

### Out of Scope

- In-app / real-time notifications (WebSocket, SSE, Pusher)
- Mobile application (responsive web only)
- Automatic timetable generation (initial semester scheduling)
- Integration with external LMS (Moodle, Google Classroom)
- Payment or financial modules
- Student self-service replacement requests

## Methodology

**Development Model:** Iterative and Incremental (Waterfall within each increment)

| Phase | Activities | Deliverable |
|---|---|---|
| Requirements Analysis | Functional specs, use case modelling | SRS Document |
| System Design | Architecture, ERD, Class Diagram, OCC sequence | Design Document |
| Implementation | Laravel 13, PostgreSQL 16, Blade/TailwindCSS | Working Prototype |
| Testing | Unit (PHPUnit), Integration, OCC conflict simulation | Test Report |
| Deployment | Nginx + Vite production build | Deployed System |

## Timeline

### FYP1 (Weeks 1–14: 15 Jun – 20 Sep 2026)

| Week | Milestone |
|---|---|
| 1–3 | Project identification, problem analysis, proposal submission |
| 4–7 | Literature review, requirements analysis, SRS |
| 8–10 | System design, database schema, wireframes |
| 11–13 | Interim prototype development, core modules |
| 14 | FYP1 portfolio submission |

### FYP2 (Weeks 1–7: 2 Nov – 20 Dec 2026)

| Week | Milestone |
|---|---|
| 1–2 | Full implementation sprint (RBAC, Matrix, OCC) |
| 3–4 | Approval dashboard, email notifications, integration |
| 5–6 | Testing (unit, integration, UAT), bug fixes |
| 7 | Final report, viva, submission |

## Technology Stack Summary

| Layer | Technology |
|---|---|
| Backend Framework | Laravel 13 (PHP 8.5+) |
| Database | PostgreSQL 16 |
| Frontend | Blade + TailwindCSS + Alpine.js |
| Build Tool | Vite |
| Web Server | Nginx |
| Email (Dev) | Mailtrap (via SMTP) |
| Email (Prod) | SMTP (Gmail / Postmark / Mailgun) |
| Authentication | Laravel Fortify (session-based) |
| OS | Linux — CachyOS (Arch-based) |

## Similar Projects at TARUMT (eprints.tarc.edu.my)

### Most Directly Relevant

| Project | Author | Year | Programme | Relevance |
|---|---|---|---|---|
| **Time Management System** | Leang, Chang Yeong | 2015 | SE | **Closest match.** Explicitly states: "lecturers can easily find a class for replacement when there is a cancellation of class." Covers timetable generation, venue allocation, clash prevention. Broader in scope (full timetable generator) but does not implement OCC or cross-cohort-specific replacement workflow. The proposed system targets a larger 14-cohort, 23-room dataset at FOCS Sabah. |
| **Faculty Office Automation System** | Too, Seng Lim | 2021 | RSD | Semester Workload module for Programme Leaders to plan lecturer assignments. Academic management context. |
| **TARUC Classroom** | Ng, Wei Lun | 2022 | RSD | Digital classroom management, class creation, attendance integration. FERN stack (Firebase, Express, React, Node). |
| **Solving Invigilation Scheduling Problem Using Tabu Search** | Liong, Jee Yuen | 2019 | MM | Algorithmic scheduling applied to invigilation at TARUMT. Demonstrates institutional research into scheduling optimisation. |
| **Online Academic Staff Booking Appointment Platform** | Chew, Jane | 2021 | RSD | Time slot booking for academic staff — booking module + time schedule module. |
| **Facility Booking System** | Ong, Zhe Zhun | 2020 | RSD | Venue/room availability checking and facility scheduling. |
| **Bright Minds - Course Management Application** | Cham, Kai Ling | 2023 | SE | Booking module for academic staff consultation hours. |
| **Final Year Project Management System** | Ho, Hong Meng | 2024 | SE | Schedule & Appointment module with Google Calendar integration. |
| **TARUMT E-Classroom** | Kuan, Zhen Hin | 2024 | BSE | Latest LMS-style classroom management system at TARUMT. |
| **Programme Management System** | Tan, Jun Hao | 2022 | RSD | Programme-level data management for academic administration. |
| **TARC Automatic Timetabling System** | Yap, Soon Siang | 2011 | AS | Earliest timetabling system found at TARUMT (predecessor institution). |

### Gap Analysis

| Capability | Time Mgmt System (2015) | Faculty Office Auto (2021) | TARUC Classroom (2022) | **Proposed System** |
|---|---|---|---|---|
| Cross-cohort awareness | Partial | No | No | **Yes** |
| OCC slot validation | No | No | No | **Yes** |
| FCFS approval queue | No | No | No | **Yes** |
| RBAC (3 tiers) | No | Partial | Partial | **Yes** |
| Email notification | No | No | No | **Yes** |
| Dedicated replacement workflow | Partial | No | No | **Yes** |
| Millisecond-precision locking | No | No | No | **Yes** |

## Key References

- Babaei, H., Karimpour, J., & Hadidi, A. (2015). A survey of approaches for university course timetabling problem. *Computers & Industrial Engineering*, 86, 43–59.
- Kung, H. T., & Robinson, J. T. (1981). On optimistic methods for concurrency control. *ACM Transactions on Database Systems*, 6(2), 213–226.
- Al-Hawari, T., Alouneh, S., & Barham, H. (2020). A systematic literature review of course timetabling algorithms. *International Transactions on Operational Research*, 27(5), 2245–2285.
- Laravel Documentation. (2026). *Mail*. https://laravel.com/docs/11.x/mail
- PostgreSQL Documentation. (2026). *Serializable Isolation Level*. https://www.postgresql.org/docs/16/transaction-iso.html
