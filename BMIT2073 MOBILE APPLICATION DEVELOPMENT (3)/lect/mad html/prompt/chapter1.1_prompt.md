Create a single interactive HTML file at `lect/mad html/chapter1_1_interactive.html` that turns Chapter 1.1 of the BMIT2073 lecture notes into a study tool. Use the same dark theme as `claude_chapter1.1.html` (read it first for exact CSS variables, fonts, class names, and layout patterns).

## Structure

1. **Sticky navbar** — brand label `<ch1.1/>`, back link to `index.html`, and anchor links for each section (ecosystem, app-types, dev-tools, flutter-arch, reactive-ui)
2. **Hero section** — tag `BMIT2073 · Chapter 1.1 · Introduction to Mobile App Development`, title `Chapter 1.1 — Mobile OS, App Types & Flutter Architecture`, lead text explaining this covers the mobile landscape, app types, and Flutter fundamentals
3. **For each topic section**, create a `<section>` with:
   - A chapter pill (e.g. `MODULE 1.1`)
   - A slide reference in small muted text (e.g. "Lecture 1.1, slide 19") — mapped to the PDF lecture notes
   - A hide/show answer button (toggle, answer shown by default on page load)
   - **Question-driven learning**: each section presents 2–4 exam-style questions with toggle answers
   - **Visualization after every answer**: comparison tables (for app types), OS ecosystem table (for mobile OS), architecture diagram (for Flutter), flow diagrams, side-by-side cards, etc.
   - A `"Where to find it"` callout pointing to the exact lecture PDF and slide range
   - After each major sub-topic, add a practice section with 2–3 similar questions (toggle answers) and a short summary box

## Content rules

- **All answers must come from the lecture PDF source material** — read `Chapter 1 Merged.pdf` to extract exact content
- If a lecture PDF is unavailable for a topic, note it clearly and use general Flutter/Dart knowledge as fallback
- **B1-level English only** — short sentences, common words, no academic jargon. If a technical term is necessary, put a simple explanation in parentheses next to it
- Every answer must be concise — think bullet-point cheat sheet, not essay

## Topic-to-chapter mapping

| Topic | Chapter | Slides |
|---|---|---|
| Mobile OS ecosystem | Ch 1.1 | "Mobile Operating Systems" — Android, iOS, Tizen, KaiOS, Harmony OS, Fuchsia |
| Mobile device categories | Ch 1.1 | "Mobile devices" — Flagship, Mid-range, Entry, Basic |
| Mobile challenges | Ch 1.1 | "Key Mobile Challenges" — Processing, Memory, Battery, Network |
| Types of mobile apps (native/hybrid/web) | Ch 1.1 | "Types of Mobile Apps" slide 18–19 |
| Comparison of app types | Ch 1.1 | "Comparison of Apps" slide 19 |
| Development tools | Ch 1.1 | "Development Tools" — Android Studio, XCode, Flutter, React Native, etc. |
| Kotlin Multiplatform Mobile | Ch 1.1 | "KMM" section |
| Flutter layered architecture | Ch 1.1 | "Flutter Architecture" — Framework → Engine → Embedder |
| Reactive UI / Declarative paradigm | Ch 1.1 | "Declarative vs Imperative", "Data flow" |
| State management landscape | Ch 1.1 | Provider, BLoC, Riverpod overview |

## Visualization examples to include

- **Mobile OS table**: a 6-row × 4-column table (OS, Kernel, Developer, Key Notes) with colored headers
- **App types comparison**: a 5-row × 4-column table (Criteria, Native, Hybrid, Mobile Web) with colored headers — same as the lecture slide 19 table
- **App type cards**: three side-by-side cards — "Native" (blue border), "Hybrid" (amber border), "Web" (green border)
- **Flutter architecture diagram**: vertical layered diagram with 3 boxes — Framework (Dart) → Engine (C++) → Embedder — with accent borders and labels
- **Mobile device tiers**: table or card grid showing Flagship/Mid-range/Entry/Basic with characteristics
- **Declarative vs Imperative**: two-column comparison table
- **Data flow diagram**: numbered 3-step flow — Constraints go down → Sizes go up → Position is set

## Footer

`bmit2073 · chapter 1.1 · introduction to mobile app development · study guide`
