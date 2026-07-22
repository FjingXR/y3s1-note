Create a single interactive HTML file at `lect/mad html/chapter3_1_interactive.html` that turns Chapter 3.1 of the BMIT2073 lecture notes into a study tool. Use the same dark theme as `claude_chapter1.1.html` (read it first for exact CSS variables, fonts, class names, and layout patterns).

## Structure

1. **Sticky navbar** — brand label `<ch3.1/>`, back link to `index.html`, and anchor links for each section (widgets, stateless-stateful, design-systems, layout, slivers, performance)
2. **Hero section** — tag `BMIT2073 · Chapter 3.1 · User Interfaces`, title `Chapter 3.1 — Widgets, Layout & Performance`, lead text explaining this covers Flutter widgets, layout systems, design systems, and performance best practices
3. **For each topic section**, create a `<section>` with:
   - A chapter pill (e.g. `MODULE 3.1`)
   - A slide reference in small muted text (e.g. "Lecture 3.1, slide 4") — mapped to the PDF lecture notes
   - A hide/show answer button (toggle, answer shown by default on page load)
   - **Question-driven learning**: each section presents 2–4 exam-style questions with toggle answers
   - **Visualization after every answer**: code blocks, comparison tables, widget hierarchy diagrams, side-by-side cards, etc.
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
| What are widgets | Ch 3.1 | Slide 4 — UI components, define appearance/layout/behavior, nested hierarchically |
| Widget characteristics | Ch 3.1 | Slide 7–10 — customizable, reusable |
| Basic widgets list | Ch 3.1 | Slide 11 — Text, TextField, ElevatedButton, Image, Row/Column, Scaffold, Placeholder, Icon, AppBar |
| Text widget | Ch 3.1 | Slide 12–15 — Text, Text.rich, TextSpan, overflow |
| TextField widget | Ch 3.1 | Slide 16–25 — InputDecoration, 3 ways to read value (onChanged, onSubmitted, Controller), TextEditingController, keyboard types |
| ElevatedButton | Ch 3.1 | Slide 26–27 — enabled/disabled states |
| Image widget | Ch 3.1 | Slide 29–36 — 3 sources (assets, file, network), Image.asset, Image.file, Image.network, formatting with fit/alignment |
| Row/Column | Ch 3.1 | Slide 37–39 — horizontal/vertical arrangement, Expanded, MainAxisAlignment |
| Icon widget | Ch 3.1 | Slide 40 — Icons class, color, size, semanticLabel |
| Scaffold | Ch 3.1 | Slide 41 — basic Material Design layout structure |
| AppBar | Ch 3.1 | Slide 45–46 — title, actions, IconButton |
| Single-child layout | Ch 3.1 | Slide 72–73 — Padding, SizedBox |
| Multi-child layout | Ch 3.1 | Slide 74–82 — Row/Column, GridView, ListView, Stack, Wrap, alignment, spacing, sizing |
| Form widgets | Ch 3.1 | Slide 83 — TextField, Checkbox, RadioListTile, DropdownButtonFormField |
| Sliver widgets | Ch 3.1 | Slide 86–92 — CustomScrollView, SliverAppBar, SliverList, SliverGrid, SliverToBoxAdapter, SliverFixedExtentList |
| Performance best practices | Ch 3.1 | Slide 94–100 — minimize rebuilds (const), optimize layout (flat tree), efficient image loading, state management, use built-in widgets |

## Visualization examples to include

- **Widget hierarchy diagram**: tree structure showing nested widgets (Container → Column → Text, Row, etc.)
- **Basic widgets grid**: card grid showing each widget type with icon and one-line description
- **Text widget cards**: side-by-side — "Text" (blue border) vs "Text.rich" (green border)
- **TextField value reading**: 3-card layout — onChanged, onSubmitted, Controller — with descriptions
- **Image sources table**: 3-column table (Source, Widget, Use Case) — assets, file, network
- **Layout widgets comparison**: table showing single-child (Padding, SizedBox) vs multi-child (Row, Column, Stack, GridView, ListView, Wrap)
- **Sliver widgets table**: 5-row table (Widget, Purpose, Use Case)
- **Performance checklist**: numbered list with accent borders — 5 best practices

## Footer

`bmit2073 · chapter 3.1 · user interfaces · study guide`
