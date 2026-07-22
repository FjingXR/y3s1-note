Create a single interactive HTML file at `lect/mad html/chapter3_3_interactive.html` that turns Chapter 3.3 of the BMIT2073 lecture notes into a study tool. Use the same dark theme as `claude_chapter1.1.html` (read it first for exact CSS variables, fonts, class names, and layout patterns).

## Structure

1. **Sticky navbar** — brand label `<ch3.3/>`, back link to `index.html`, and anchor links for each section (state-mgmt, provider, nav-principles, tab, drawer, dialog, picker, snackbar)
2. **Hero section** — tag `BMIT2073 · Chapter 3.3 · State Management & Navigation`, title `Chapter 3.3 — State Management, Navigation Principles & UI Patterns`, lead text explaining this covers ephemeral vs app state, Provider pattern, navigation principles, and common UI patterns (tabs, drawers, dialogs, snackbars)
3. **For each topic section**, create a `<section>` with:
   - A chapter pill (e.g. `MODULE 3.3`)
   - A slide reference in small muted text (e.g. "Lecture 3.3, slide 5") — mapped to the PDF lecture notes
   - A hide/show answer button (toggle, answer shown by default on page load)
   - **Question-driven learning**: each section presents 2–4 exam-style questions with toggle answers
   - **Visualization after every answer**: code blocks, comparison tables, side-by-side cards, numbered flow diagrams, etc.
   - A `"Where to find it"` callout pointing to the exact lecture PDF and slide range
   - After each major sub-topic, add a practice section with 2–3 similar questions (toggle answers) and a short summary box

## Content rules

- **All answers must come from the lecture PDF source material** — read `Chapter 3 Merged.pdf` to extract exact content
- If a lecture PDF is unavailable for a topic, note it clearly and use general Flutter knowledge as fallback
- **B1-level English only** — short sentences, common words, no academic jargon. If a technical term is necessary, put a simple explanation in parentheses next to it
- Every answer must be concise — think bullet-point cheat sheet, not essay

## Topic-to-chapter mapping

| Topic | Chapter | Slides |
|---|---|---|
| What is state management | Ch 3.3 | Slide 1–4 — managing data that changes and triggers UI updates, state = everything in memory |
| Ephemeral state | Ch 3.3 | Slide 4 — also called UI state or local state, contained in a single widget |
| App state | Ch 3.3 | Slide 4 — also called shared state, shared across many parts of app, persists between sessions |
| Ephemeral vs App state examples | Ch 3.3 | Slide 5 — ephemeral: current page, animation progress, selected tab; app: user preferences, login info, shopping cart, notifications |
| Provider pattern | Ch 3.3 | Slide 6–11 — ChangeNotifier, notifyListeners(), ChangeNotifierProvider, MultiProvider, Consumer widget, context.read() |
| Navigation principles (5) | Ch 3.3 | Slide 16–23 — (1) Fixed start destination, (2) Stack of destinations, (3) Up = Back, (4) Up never exits, (5) Deep linking simulates manual nav |
| Tab navigation | Ch 3.3 | Slide — TabBar + TabBarView, TabController, DefaultTabController, Fixed vs Scrollable tabs, 3-step setup |
| Drawer navigation | Ch 3.3 | Slide — Scaffold + Drawer widget, 5-step setup (create Scaffold, add drawer, populate, open programmatically, close), when to use (≥5 destinations, ≥2 levels) |
| Dialog - AlertDialog | Ch 3.3 | Slide — informs user, optional title + actions, showDialog(), barrierDismissible |
| Dialog - SimpleDialog | Ch 3.3 | Slide — offers choices, SimpleDialogOption, showDialog() with switch |
| Date/Time Pickers | Ch 3.3 | Slide — showDatePicker, showTimePicker, initialDate, firstDate, lastDate |
| Snackbar | Ch 3.3 | Slide — low priority, auto-dismiss, optional action (Undo), ScaffoldMessenger.showSnackBar() |
| Snackbar vs Dialog | Ch 3.3 | Slide — Snackbar (low priority, optional action, auto-dismiss) vs Dialog (high priority, required action, blocks app) |

## Visualization examples to include

- **State types comparison**: two-column diff table — 🔄 Ephemeral (local, single widget, not shared) vs 📦 App State (shared, persistent, many screens)
- **Provider setup flow**: numbered 4-step flow — ChangeNotifier class → ChangeNotifierProvider in main → Consumer in widget → context.read() for actions
- **Navigation principles**: numbered vertical flow with accent borders and icons — 5 principles with one-line descriptions and visual diagrams
- **Navigator stack diagram**: horizontal stack visualization — Start → A → B → C with arrows and visibility labels
- **Tab setup steps**: 3-step code flow — DefaultTabController → TabBar (tabs) → TabBarView (content)
- **Drawer setup steps**: 5-step numbered list — Scaffold → Drawer → populate ListView → openDrawer() → Navigator.pop()
- **Dialog comparison table**: 3-column (Feature, AlertDialog, SimpleDialog) — purpose, content, use case
- **Snackbar vs Dialog table**: 4-column (Aspect, Snackbar, Dialog) — priority, user action, dismissal, use case

## Footer

`bmit2073 · chapter 3.3 · state management and navigation · study guide`
