Create a single interactive HTML file at `lect/mad html/chapter1_2_interactive.html` that turns Chapter 1.2 of the BMIT2073 lecture notes into a study tool. Use the same dark theme as `claude_chapter1.1.html` (read it first for exact CSS variables, fonts, class names, and layout patterns).

## Structure

1. **Sticky navbar** — brand label `<ch1.2/>`, back link to `index.html`, and anchor links for each section (intro, variables, types, control-flow, functions)
2. **Hero section** — tag `BMIT2073 · Chapter 1.2 · Introduction to Dart`, title `Chapter 1.2 — Dart Programming Basics`, lead text explaining this covers Dart's core syntax, variables, types, control flow, and functions
3. **For each topic section**, create a `<section>` with:
   - A chapter pill (e.g. `MODULE 1.2`)
   - A slide reference in small muted text (e.g. "Lecture 1.2, slide 5") — mapped to the PDF lecture notes
   - A hide/show answer button (toggle, answer shown by default on page load)
   - **Question-driven learning**: each section presents 2–4 exam-style questions with toggle answers
   - **Visualization after every answer**: code blocks (for syntax), comparison tables (for data types), flow diagrams (for control flow), side-by-side cards (for var vs explicit types), etc.
   - A `"Where to find it"` callout pointing to the exact lecture PDF and slide range
   - After each major sub-topic, add a practice section with 2–3 similar questions (toggle answers) and a short summary box

## Content rules

- **All answers must come from the lecture PDF source material** — read `Chapter 1 Merged.pdf` to extract exact content
- If a lecture PDF is unavailable for a topic, note it clearly and use general Dart knowledge as fallback
- **B1-level English only** — short sentences, common words, no academic jargon. If a technical term is necessary, put a simple explanation in parentheses next to it
- Every answer must be concise — think bullet-point cheat sheet, not essay

## Topic-to-chapter mapping

| Topic | Chapter | Slides |
|---|---|---|
| What is Dart | Ch 1.2 | "Introduction" — open-source, general-purpose, by Google |
| Dart key features | Ch 1.2 | "Key features" — OOP, strongly typed, fast, modern |
| Program structure (main function) | Ch 1.2 | "Structure" — void main(), print(), comments |
| Variables & declaration keywords | Ch 1.2 | "Variable" — int, double, String, bool, var, nullable (?) |
| Data types | Ch 1.2 | "Data Types" — Numbers (int, double, num), Text (String), Logical (bool) |
| Nullable types | Ch 1.2 | "double? area = null" — nullable declaration with ? |
| var vs explicit types | Ch 1.2 | "var infers String based on assignment" — type inference |
| Control flow — if/else | Ch 1.2 | "Basic Structures" — if, else if, else |
| Control flow — for loop | Ch 1.2 | "Basic Structures" — for loop, for-in loop |
| Control flow — while loop | Ch 1.2 | "Basic Structures" — while loop |
| Functions — declaration | Ch 1.2 | "Functions" — return type, parameters, return statement |
| Functions — recursion | Ch 1.2 | "Functions" — fibonacci recursive example |
| Arrow syntax (=>) | Ch 1.2 | "Functions" — bool isNoble(...) => expression |
| Higher-order functions | Ch 1.2 | "Functions" — .where(), .forEach(), lambda/anonymous functions |

## Visualization examples to include

- **Data types table**: a 4-row × 3-column table (Type, Category, Example) with colored headers — int, double, num, String, bool
- **Declaration keywords comparison**: side-by-side cards — "Explicit type" (blue border) vs "var" (green border) vs "Nullable ?" (amber border)
- **Control flow diagram**: numbered 3-step flow — if/else → for → while, with code snippets
- **Function anatomy**: code block with annotated parts (return type, name, parameters, body)
- **Arrow vs block function**: two-column comparison showing `=>` one-liner vs `return` block
- **Code examples**: use `.cli` class for code blocks with syntax highlighting (green text on dark background, matching `chapter1_intro.html` pattern)

## Footer

`bmit2073 · chapter 1.2 · introduction to dart · study guide`
