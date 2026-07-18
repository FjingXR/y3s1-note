# My Timetable — View-Only Design Guideline

> **Design Style:** Clean, simple, modern, dashboard-oriented. Minimum plain text — more icons & buttons. Corporate TAR UMT aesthetic with gold/blue/burgundy branding.
> **Primary Goal:** Enable lecturers to view their weekly timetable, identify replacement classes, monitor schedule conflicts, and browse course schedules by cohort, lecturer, or room.
> **Target Audience:** University lecturers, academic staff, timetable administrators, programme leaders.
> **Page Structure:** 3 sub-views — Cohort Timetable, Lecturer Timetable, Room Timetable — sharing a common grid UI.

---

## 1. Layout & Structure

### 1.1 Screen Canvas

Base viewport: **1366 × 768 px**. Layout is full-width, single-page dashboard with no vertical scroll on the timetable itself (horizontal scroll only when many time columns overflow).

### 1.2 Page Sections (top→bottom)

```
┌─────────────────────────────────────────────────────────────────────┐
│  Top Navigation Bar           (y: 0–55, h: 56px, full width)       │
├────────────────────────────────┬────────────────────────────────────┤
│  Left Sidebar /               │  Main Content Area                  │
│  Week Selector                │  (x: 385–1366)                     │
│  (x: 0–384, w: 384px)        │                                     │
│  (y: 56–100, h: ~44px)       │  ┌─ Time Header Row ──────────────┐ │
│                                │  │  (y: 104–182, h: ~78px)       │ │
│                                │  ├────────────────────────────────┤ │
│                                │  │  Timetable Grid Body           │ │
│                                │  │  (y: 183–560)                  │ │
│                                │  │  (rows: days, cols: times)     │ │
│                                │  └────────────────────────────────┘ │
├────────────────────────────────┴────────────────────────────────────┤
│  Legend Bar                    (y: 716–765, h: ~50px, full width)   │
└─────────────────────────────────────────────────────────────────────┘
```

### 1.3 Visual Hierarchy

1. **Top navigation bar** — brand identity, active page indicator, user session (profile + notifications).
2. **Left sidebar** — week selector context (current semester/week range).
3. **Time header row** — day+date labels on left, hourly time slots across top.
4. **Timetable grid** — the primary data display; user scans from day labels (left) across to find their scheduled classes.
5. **Legend bar** — color key for schedule statuses (viewed after grid, but statuses should also be self-evident from block styling).

---

## 2. Top Navigation Bar

### 2.1 Dimensions & Colors

| Property | Value |
|----------|-------|
| Height | 56px (y: 0–55) |
| Background (left) | `--color-primary-container` (`#a7c3e6` / light blue) — spans x: 0–1145 |
| Background (right) | `--color-secondary-container` (`#aee6cc` / light green) — spans x: 1147–1365 |
| Text color | `--color-on-primary-container` (`#071b33` / dark blue) |
| Active nav indicator | `--color-tertiary-container` (`#e4e6bb` / light yellow) — subtle highlight behind active item |

### 2.2 Component Layout

| Region | Position | Content |
|--------|----------|---------|
| Logo | Far left | TAR UMT logo icon (~32×32px) + system title |
| Nav items | Center-left (x: ~130–1080) | Horizontal menu: Dashboard, My Timetable, Replacement Arrangement, etc. |
| Active item | x: ~1084–1135 | Highlighted with `--color-tertiary-container` background + bold dark text |
| Notification bell | Right side (green area) | Bell icon with unread badge (red dot/number) |
| User avatar | Far right (green area) | Circular avatar / Staff ID badge with role label |

### 2.3 Navigation Item Spacing

Nav items are roughly evenly spaced. Based on the reference image, each item occupies ~110–130px horizontally with text centered. The active item distinctly uses the tertiary-container yellow highlight to signal current page.

---

## 3. Left Sidebar — Week Selector

### 3.1 Dimensions

| Property | Value |
|----------|-------|
| Width | 384px (x: 0–384) |
| Height | ~44px (y: 56–100) |
| Background | `--color-secondary-container` (`#aee6cc` / light green) |
| Text color | `--color-on-secondary-container` (`#0c3321` / dark green) |

### 3.2 Content

- **Semester label** (e.g., "Semester 3, Session 2025/2026")
- **Week range** (e.g., "Week 11 · 01 Sep – 07 Sep 2026")
- **Dropdown arrow icon** (if week switching is available) or static label (if view-only single-week)

### 3.3 Visual Treatment

The sidebar uses the same secondary-container green as the nav bar's right section, creating a visual connection between the user profile area and the week context. Text is set in `--color-on-secondary-container` dark green with medium font weight.

---

## 4. Time Header Row

### 4.1 Dimensions

| Property | Value |
|----------|-------|
| Height | ~78px (y: 104–182) |
| Background | `--color-surface-variant` (`#d9dfe6` / light gray) |
| Separator line (bottom) | y: 182, `--color-outline-strong` (medium gray border) |

### 4.2 Column Structure

| Column | Width | Content |
|--------|-------|---------|
| Day label (first) | ~150px (x: 1–151) | Sticky left column. Header text: "Day / Time" |
| Time slot (each) | ~108px each | Header shows the hour (e.g., "08:00") with 30-min sub-label below (e.g., "08:30") |
| Slot count | ~11 visible hours | Typically 8:00 AM through 6:30 PM (22 half-hour slots) |

### 4.3 Sticky Behavior

The day column (x: 0–151) is **sticky** — it remains visible when the grid scrolls horizontally. The time header row (y: 104–182) is also **sticky** atop the grid when scrolling vertically.

---

## 5. Timetable Grid Body

### 5.1 Grid Layout

| Property | Value |
|----------|-------|
| Start | y: 183 (after header separator) |
| End | y: ~560 |
| Row height | ~60–105px per day row (varies by content density) |
| Column width | ~108px per time slot |
| Border | 1px solid `--color-outline` between cells |

### 5.2 Row Structure (Days)

Each row represents a **day of the week** (Mon–Sat in the reference data, or Mon–Sun). The sticky left column shows:

- **Day abbreviation** (e.g., "Mon", "Tue")
- **Date** (e.g., "01 Sep 2026")
- **Public holiday label** (if applicable) — displayed in `--color-error` (`#E69490`), uppercase, small text

### 5.3 Column Structure (Time Slots)

Time headers display hour labels in 12-hour or 24-hour format. Each header cell shows:
- **Top label:** Hour (e.g., "08:00")
- **Bottom label:** Half-hour (e.g., "08:30") — smaller, slightly transparent

### 5.4 Event Blocks (Timetable Cells)

Each non-empty cell contains a **colored block** representing a scheduled class. These blocks span multiple time slots when a class is longer than 30 minutes.

#### 5.4.1 Color Coding

| Status | Container Color | Text Color | Meaning |
|--------|----------------|------------|---------|
| **Normal / Scheduled** | `--color-secondary-container` (`#aee6cc` / light green) | `--color-on-secondary-container` (`#0c3321`) | Regular timetabled class |
| **Replacement / Mixed** | `--color-tertiary-container` (`#e4e6bb` / light yellow) | `--color-on-tertiary-container` (`#323315`) | Class with replacement arrangement |
| **Conflict / Clash** | `--color-error-container` (`#e6aca9` / light red) | `--color-on-error-container` (`#330b09`) | Scheduling conflict or overlapping class |
| **Public Holiday** | `--color-error-container` (`#e6aca9`) | `--color-on-error-container` | Day-level indicator (entire day row affected) |
| **Empty / No class** | `--color-surface` (`#fbfcfc` / white) | — | No scheduled activity |

#### 5.4.2 Block Content

Each event block displays **minimal info** inline (to keep the grid clean):

| Line | Content | Example |
|------|---------|---------|
| 1 | Subject code | `BMIT6767` |
| 2 | Class type | `L` (Lecture) / `T` (Tutorial) |
| 3 | Venue (optional, space permitting) | `B103` |

Additional details are deferred to a **modal pop-up** on click (see Section 7).

#### 5.4.3 Block Sizing

- Single-slot (30 min): ~52px height
- Multi-slot blocks: height = count × 52px + (count−1) × gap
- Blocks fill the entire cell area with a consistent padding (~4–6px)
- Rounded corners optional but consistent with the replacement-arrangement template

### 5.5 Row Height Distribution

From pixel analysis of the reference:
- **Row 1** (first day): ~105px (tallest — contains multi-hour event blocks)
- **Row 2**: ~61px (empty or short events)
- **Row 3**: ~63px
- **Row 4**: ~82px
- **Row 5**: ~60px

Rows automatically expand to contain their tallest event block. Empty rows maintain a minimum height of ~52px.

---

## 6. Event Block Interaction (View-Only)

### 6.1 Click Behavior

- Entire event block is **clickable** (not just small icons inside it).
- Clicking opens a **modal pop-up** with full class details.
- No drag, no edit, no selection — this is **view-only**.

### 6.2 Hover State

- Hovered block gets a slight brightness increase (`filter: brightness(1.05)`) or subtle border highlight.
- Cursor changes to `pointer`.

### 6.3 Tooltips (Optional)

If the eye/cursor icons from the Canva reference are retained, they must include **tooltips on hover** (e.g., "View details", "Open class info"). However, the recommended approach is to make the entire block clickable and remove the icons entirely for a cleaner UI.

---

## 7. Class Detail Modal

### 7.1 Trigger

Clicking any timetable event block opens the modal.

### 7.2 Modal Specification

| Property | Value |
|----------|-------|
| Backdrop | Fixed overlay, `rgba(0,0,0,0.55)`, `backdrop-filter: blur(4px)` |
| Width | Max: 460px, centered vertically+horizontally |
| Background | `--color-surface` (`#fbfcfc` light / `#2a2c2e` dark) |
| Border | 1px solid `--color-outline` |
| Radius | 16px |
| Animation | Scale-in + translate-up (0.2s ease) |

### 7.3 Modal Content Fields

```
┌──────────────────────────────────────────────┐
│  Class Details                      [×]      │
├──────────────────────────────────────────────┤
│  Subject Code     │  BMIT6767                 │
│  Subject Name     │  Object-Oriented Prog     │
│  Class Type       │  Lecture (L)              │
│  Lecturer         │  Dr. Christopher Lazarus  │
│  Cohort           │  DFT2 (S1)                │
│  Venue            │  B103                     │
│  Day              │  Monday                   │
│  Date             │  01 Sep 2026              │
│  Time             │  10:00 AM – 12:00 PM      │
│  Status           │  Normal / Replacement     │
│  Remarks          │  Room changed from B105   │
└──────────────────────────────────────────────┘
```

### 7.4 Close Behavior

- Click × button, click outside modal, or press Escape.
- No save/submit — view-only.

---

## 8. Legend Bar

### 8.1 Position & Dimensions

| Property | Value |
|----------|-------|
| Position | Bottom of page (y: 716–765) |
| Height | ~50px |
| Background | `--color-primary-container` (`#a7c3e6` / light blue) |
| Width | Full width (x: 0–1366) |
| Text color | `--color-on-primary-container` (`#071b33` / dark blue) |

### 8.2 Legend Items

```
◼ Normal Class    ◼ Replacement    ◼ Conflict    ◼ Public Holiday
   (green)           (yellow)         (red)          (red, day-level)
```

Swatch size: ~18×18px, rounded corners (4px), with 1px outline border.

### 8.3 Design

The legend bar is a full-width strip at the bottom. Items are evenly spaced with ~18px gaps between them. Each item has a colored swatch followed by a text label. The bar is visually anchored to the page bottom, providing a final reference after scanning the timetable.

---

## 9. Design System Tokens (CSS Variables)

All colors reference the existing `theme.css` shared design system. The timetable additionally uses:

| Token | Dark Value | Light Value | Usage |
|-------|-----------|-------------|-------|
| `--timetable-day-col` | — | — | 150px width for sticky day column |
| `--timetable-slot-w` | — | — | 108px width per time slot |
| `--timetable-row-min` | — | — | 52px minimum row height |
| `--color-event-normal` | `--color-secondary-container` | same | Green event blocks |
| `--color-event-replacement` | `--color-tertiary-container` | same | Yellow event blocks |
| `--color-event-conflict` | `--color-error-container` | same | Red event blocks |

No new color tokens needed — reuse the existing container/on-container pair pattern.

---

## 10. UI Components Inventory

| # | Component | Section | Notes |
|---|-----------|---------|-------|
| 1 | Top navigation bar | Top bar | Blue primary-container bg, green right section |
| 2 | Active nav menu item | Top bar | Tertiary-container yellow highlight |
| 3 | Week selector / Semester info | Left sidebar | Green secondary-container bg, ~384px wide |
| 4 | Calendar-style timetable grid | Main area | Days as rows, time slots as columns |
| 5 | Day + date labels | Grid (left column) | Sticky, shows day name + date |
| 6 | Time slot headers | Grid (top row) | Sticky, shows hour:minute |
| 7 | Timetable event blocks | Grid cells | Colored containers (green/yellow/red) |
| 8 | Public holiday indicator | Grid (day row) | Error-color "PUBLIC HOLIDAY" label |
| 9 | Mail notification icon | Top bar (right) | Bell icon with unread badge |
| 10 | User profile section | Top bar (right) | Avatar/name in green section |
| 11 | Schedule status legend | Bottom bar | Full-width blue strip with swatches |
| 12 | Class detail modal | Overlay | Triggered by clicking an event block |

---

## 11. Accessibility & Responsiveness

### 11.1 Usability Notes

- Event block colors are distinguishable by hue (green/yellow/red) — no reliance on luminance alone.
- The legend provides a quick reference, but status should be inferable from context (e.g., "Public Holiday" label, event block text).
- Click targets (event blocks) are large enough for pointer interaction (min ~52px height).

### 11.2 Mobile Adaptation

| Breakpoint | Changes |
|-----------|---------|
| < 1024px | Collapse nav into hamburger menu. Sidebar moves to top or collapses. |
| < 768px | Replace full grid with vertically stacked daily agenda view (cards). |
| Swipe | Allow day-by-day navigation with left/right swipe or day tabs. |
| Event cards | Each event becomes a card: subject, time, venue, status label. |
| Sticky headers | Day/date labels persist while scrolling the agenda list. |
| Legend | Status labels shown directly on each card to avoid constant legend reference. |

---

## 12. Implementation Notes

### 12.1 File Structure

```
resources/views/
├── layouts/
│   └── app.blade.php          ← Shared layout with nav bar
├── pages/
│   └── my-timetable.blade.php   ← Main My Timetable page
```

Or if using the 3-view approach already scoped:

```
resources/views/
├── timetable/
│   ├── cohort.blade.php
│   ├── lecturer.blade.php
│   └── room.blade.php
└── partials/
    └── timetable-grid.blade.php   ← Shared grid partial
    └── class-detail-modal.blade.php
```

### 12.2 Inline Style Convention

Follow the existing pattern in `replacement-arrangement-UIdesign-template.blade.php`:
- No Tailwind utility classes (skip Laravel's Tailwind build for design templates)
- Use `<style>` blocks in `<head>` with CSS custom properties
- Use `theme.css` shared tokens for colors/radius/shadows
- Dark/light mode via `.dark`/`.light` on `<html>`

### 12.3 Grid Implementation

The timetable should use:
- A `<table>` with `table-layout: fixed` for predictable column widths
- Sticky positioning for the day column (`position: sticky; left: 0`)
- Sticky positioning for the header row (`position: sticky; top: 0`)
- A scrollable wrapper (`overflow: auto`) around the table
- Day labels + dates in the left sticky column
- Time slots as `<th>` elements in `<thead>`

### 12.4 Sample Data Fields (Mock)

Each timetable entry should contain (for mock/seed data):

```
{
  subject_code: "BMIT6767",
  subject_name: "Object-Oriented Programming",
  class_type: "L" | "T",
  lecturer_name: "Dr. Christopher Lazarus",
  cohort_code: "DFT2 (S1)",
  venue: "B103",
  day_of_week: 1,        // 1=Mon, 6=Sat (or 0=Sun)
  start_time: "10:00",
  end_time: "12:00",
  status: "normal" | "replacement" | "conflict",
  remarks: "Room changed from B105"
}
```

### 12.5 Interaction Summary

| Element | Click | Hover |
|---------|-------|-------|
| Nav items | Navigate to page | Brightness change |
| Event block (normal) | Open modal with details | `brightness(1.05)` |
| Event block (replacement) | Open modal with details | `brightness(1.05)` |
| Event block (conflict) | Open modal with details | `brightness(1.05)` |
| Public holiday cell | No action | No change |
| Empty cell | No action | No change |

---

## 13. Page-Load States

### 13.1 Initial Load
- Week selector defaults to current week (hardcoded for mock)
- Timetable grid renders with all event blocks
- No loading skeleton needed (static mock data)

### 13.2 Empty State
- If no events exist for a day, all cells show empty (white/`--color-surface`)
- The legend is still visible for context
- A subtle hint text can appear: "No classes scheduled for this week"

### 13.3 Error State (View-Only Non-Applicable)
- Since this is view-only with mock data, no error state is required
- If connecting to a real backend in the future, display a toast: "Unable to load timetable"

---

## 14. Color Reference (Quick Lookup)

| Role | HEX | Usage |
|------|-----|-------|
| Primary | `#1A5FB4` | Nav bar accent, sticky header borders |
| Primary Container | `#A7C3E6` | Nav bar background (left), legend background |
| Secondary | `#2EC27E` | Button fills, success indicators |
| Secondary Container | `#AEE6CC` | Nav bar (right), sidebar, normal event blocks |
| Tertiary Container | `#E4E6BB` | Active nav highlight, replacement event blocks |
| Error Container | `#E6ACA9` | Conflict event blocks, public holiday |
| Surface | `#fbfcfc` | Empty cells, page background |
| Surface Variant | `#d9dfe6` | Time header row |
| Outline | `rgba(159,168,179,0.2)` | Cell borders, dividers |
| On-Primary Container | `#071B33` | Dark text on blue containers |
| On-Secondary Container | `#0C3321` | Dark text on green containers |
| On-Tertiary Container | `#323315` | Dark text on yellow containers |
| On-Error Container | `#330B09` | Dark text on red containers |

> Full theme with dark/light mode variables is defined in `class-replacement-system/public/css/theme.css`.
