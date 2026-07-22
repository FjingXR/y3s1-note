Create a single interactive HTML file at `lect/mad html/chapter2_interactive.html` that turns Chapter 2 of the BMIT2073 lecture notes into a **theory-focused** study tool. Use the same dark theme as `claude_chapter1.1.html` (read it first for exact CSS variables, fonts, class names, and layout patterns).

## Content philosophy

- **95% theory, 5% code** — this is a theory midterm prep tool, not a coding tutorial
- Focus on **how things work** and **the flow** — explain concepts as processes, not syntax
- Code is only allowed when it directly illustrates a concept (e.g. one line showing Navigator.push) — no multi-line code blocks, no full class examples
- Every answer should read like a **conceptual explanation**, not a code walkthrough
- Use **tables, flow diagrams, and bullet points** to explain — avoid prose paragraphs

## Structure

1. **Sticky navbar** — brand label `<ch2/>`, back link to `index.html`, and anchor links for each section (routes, navigator, send-data, return-data, shared-state, deep-linking, lifecycle)
2. **Hero section** — tag `BMIT2073 · Chapter 2 · App Lifecycle`, title `Chapter 2 — Routes, Navigation & App Lifecycle`, lead text explaining this covers Flutter's navigation system and app lifecycle states
3. **For each topic section**, create a `<section>` with:
   - A chapter pill (e.g. `MODULE 2`)
   - A slide reference in small muted text (e.g. "Lecture 2, slide 6") — mapped to the PDF lecture notes
   - A hide/show answer button (toggle, answer shown by default on page load)
   - **Question-driven learning**: each section presents 2–4 exam-style questions with toggle answers
   - **Visualization after every answer**: flow diagrams, tables, side-by-side cards, numbered steps — NOT code blocks
   - A `"Where to find it"` callout pointing to the exact lecture PDF and slide range
   - After each major sub-topic, add a practice section with 2–3 similar questions (toggle answers) and a short summary box

## Content rules

- **All answers must come from the lecture PDF source material** — read `Chapter 2 App Lifecycle.pdf` to extract exact content
- If a lecture PDF is unavailable for a topic, note it clearly and use general Flutter knowledge as fallback
- **B1-level English only** — short sentences, common words, no academic jargon. If a technical term is necessary, put a simple explanation in parentheses next to it
- Every answer must be concise — think bullet-point cheat sheet, not essay
- **No code-heavy explanations** — explain concepts as "what happens when..." flows, not "type this code..."

## Topic-to-chapter mapping

| Topic | Chapter | Slides | Focus |
|---|---|---|---|
| What are routes | Ch 2 | "Route and Navigator" — screens/pages are called routes; route = widget in Flutter | Definition + how it relates to Android/iOS equivalents |
| Routes in Android vs iOS vs Flutter | Ch 2 | Slide 4 — Android Activity, iOS ViewController, Flutter widget | Comparison table |
| Navigator stack | Ch 2 | Slide 6–7 — Navigator displays screens as a stack, push/pop | How the stack works conceptually (like plates) |
| Navigator.push() | Ch 2 | Slide 8 — MaterialPageRoute, transition animation | What happens when you push — the flow |
| Navigator.pop() | Ch 2 | Slide 9 — pop to go back | What happens when you pop — the flow |
| Send data between screens | Ch 2 | Slide 10–14 — pass data via constructor (e.g., Todo object) | How data flows from Screen A to Screen B |
| Return data from a screen | Ch 2 | Slide 15–16 — Navigator.pop(context, 'Returned Data'), .then() callback | How data flows back from Screen B to Screen A |
| Shared state with Provider | Ch 2 | Slide 17–20 — ChangeNotifier, Consumer, sharing data across screens | Why Provider exists, how it shares data across screens |
| Deep linking | Ch 2 | Slide 21–23 — linking directly to specific content, app links (Android), universal links (iOS) | What deep linking is, how it differs per platform |
| App lifecycle overview | Ch 2 | Slide 24–26 — 4 primary states, why lifecycle matters | Why lifecycle matters for resource management |
| Resumed state | Ch 2 | Slide 29 — visible, active, fetch data, process interactions, play media | When it happens, what you should do |
| Paused state | Ch 2 | Slide 30 — background, pause tasks, save data, release resources | When it happens, what you should do |
| Inactive state | Ch 2 | Slide 31 — brief transition, pause network requests, prepare for state change | When it happens, what you should do |
| Detached state | Ch 2 | Slide 32 — not attached, clean up resources, persist critical data | When it happens, what you should do |
| AppLifecycleListener | Ch 2 | Slide 34 — code example with onResume, onPause, onDetach callbacks | Concept only: it exists, it has callbacks for each state |

## Visualization examples to include (NO CODE)

- **Routes concept table**: 3-column table (Flutter, Android, iOS) showing what a "route" equals in each platform
- **Navigator stack diagram**: horizontal stack visualization showing push/pop — Screen 1 → Screen 2 → Screen 3 with arrows
- **Send data flow**: numbered flow diagram — Screen A creates data → pushes Screen B with data → Screen B receives and displays data
- **Return data flow**: numbered flow — push screen → user action → pop with data → Screen A receives data
- **Provider flow**: 3-step diagram — ChangeNotifier holds data → Provider shares it → Consumer screens read and rebuild
- **Lifecycle states diagram**: horizontal flow with 4 boxes — Resumed → Inactive → Paused → Detached — with arrows and color-coded borders (green, amber, pink, red)
- **Lifecycle actions table**: 4-row table (State, Visible?, What Happens, What You Should Do)
- **Lifecycle transitions table**: when does each transition happen (user presses home, incoming call, app destroyed, etc.)

## Summary section requirements

The summary/cheat sheet at the end must be **99% theory and flow**:
- Tables comparing concepts (routes vs activities vs view controllers)
- Flow descriptions (what happens step by step when user navigates)
- Lifecycle state descriptions (what each state means, when it happens, what to do)
- **Zero code blocks** in the summary
- **Zero syntax explanations** in the summary
- Focus entirely on: definitions, comparisons, flows, and when-to-do-what

## Footer

`bmit2073 · chapter 2 · app lifecycle · study guide`
