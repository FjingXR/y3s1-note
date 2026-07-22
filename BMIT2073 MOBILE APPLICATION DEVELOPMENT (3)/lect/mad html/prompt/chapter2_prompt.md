Create a single interactive HTML file at `lect/mad html/chapter2_interactive.html` that turns Chapter 2 of the BMIT2073 lecture notes into a study tool. Use the same dark theme as `claude_chapter1.1.html` (read it first for exact CSS variables, fonts, class names, and layout patterns).

## Structure

1. **Sticky navbar** — brand label `<ch2/>`, back link to `index.html`, and anchor links for each section (routes, navigator, send-data, return-data, shared-state, deep-linking, lifecycle)
2. **Hero section** — tag `BMIT2073 · Chapter 2 · App Lifecycle`, title `Chapter 2 — Routes, Navigation & App Lifecycle`, lead text explaining this covers Flutter's navigation system and app lifecycle states
3. **For each topic section**, create a `<section>` with:
   - A chapter pill (e.g. `MODULE 2`)
   - A slide reference in small muted text (e.g. "Lecture 2, slide 6") — mapped to the PDF lecture notes
   - A hide/show answer button (toggle, answer shown by default on page load)
   - **Question-driven learning**: each section presents 2–4 exam-style questions with toggle answers
   - **Visualization after every answer**: code blocks (for syntax), stack diagrams (for navigator), state flow diagrams (for lifecycle), side-by-side cards, etc.
   - A `"Where to find it"` callout pointing to the exact lecture PDF and slide range
   - After each major sub-topic, add a practice section with 2–3 similar questions (toggle answers) and a short summary box

## Content rules

- **All answers must come from the lecture PDF source material** — read `Chapter 2 App Lifecycle.pdf` to extract exact content
- If a lecture PDF is unavailable for a topic, note it clearly and use general Flutter knowledge as fallback
- **B1-level English only** — short sentences, common words, no academic jargon. If a technical term is necessary, put a simple explanation in parentheses next to it
- Every answer must be concise — think bullet-point cheat sheet, not essay

## Topic-to-chapter mapping

| Topic | Chapter | Slides |
|---|---|---|
| What are routes | Ch 2 | "Route and Navigator" — screens/pages are called routes; route = widget in Flutter |
| Routes in Android vs iOS vs Flutter | Ch 2 | Slide 4 — Android Activity, iOS ViewController, Flutter widget |
| Navigator stack | Ch 2 | Slide 6–7 — Navigator displays screens as a stack, push/pop |
| Navigator.push() | Ch 2 | Slide 8 — MaterialPageRoute, transition animation |
| Navigator.pop() | Ch 2 | Slide 9 — pop to go back |
| Send data between screens | Ch 2 | Slide 10–14 — pass data via constructor (e.g., Todo object) |
| Return data from a screen | Ch 2 | Slide 15–16 — Navigator.pop(context, 'Returned Data'), .then() callback |
| Shared state with Provider | Ch 2 | Slide 17–20 — ChangeNotifier, Consumer, sharing data across screens |
| Deep linking | Ch 2 | Slide 21–23 — linking directly to specific content, app links (Android), universal links (iOS) |
| App lifecycle overview | Ch 2 | Slide 24–26 — 4 primary states, why lifecycle matters |
| Resumed state | Ch 2 | Slide 29 — visible, active, fetch data, process interactions, play media |
| Paused state | Ch 2 | Slide 30 — background, pause tasks, save data, release resources |
| Inactive state | Ch 2 | Slide 31 — brief transition, pause network requests, prepare for state change |
| Detached state | Ch 2 | Slide 32 — not attached, clean up resources, persist critical data |
| AppLifecycleListener | Ch 2 | Slide 34 — code example with onResume, onPause, onDetach callbacks |

## Visualization examples to include

- **Routes concept table**: 3-column table (Flutter, Android, iOS) showing what a "route" equals in each platform — widget, Activity, ViewController
- **Navigator stack diagram**: horizontal stack visualization showing push/pop — Screen 1 → Screen 2 → Screen 3 with arrows
- **Send data flow**: side-by-side code cards — "Main Screen" (blue border) pushes data, "Detail Screen" (green border) receives data
- **Return data flow**: numbered flow — push screen → user action → pop with data → .then() callback handles result
- **Lifecycle states diagram**: horizontal flow with 4 boxes — Resumed → Inactive → Paused → Detached — with arrows and color-coded borders (green, amber, red, pink)
- **Lifecycle actions table**: 4-row table (State, Visibility, Typical Actions) for each lifecycle state
- **AppLifecycleListener code block**: annotated code example with highlighted callbacks

## Footer

`bmit2073 · chapter 2 · app lifecycle · study guide`
