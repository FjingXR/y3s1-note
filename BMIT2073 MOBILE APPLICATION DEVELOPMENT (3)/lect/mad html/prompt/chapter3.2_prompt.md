Create a single interactive HTML file at `lect/mad html/chapter3_2_interactive.html` that turns Chapter 3.2 of the BMIT2073 lecture notes into a study tool. Use the same dark theme as `claude_chapter1.1.html` (read it first for exact CSS variables, fonts, class names, and layout patterns).

## Structure

1. **Sticky navbar** — brand label `<ch3.2/>`, back link to `index.html`, and anchor links for each section (colors, themes, typography, internationalization, screens, accessibility)
2. **Hero section** — tag `BMIT2073 · Chapter 3.2 · Platforms, Themes & Design`, title `Chapter 3.2 — Themes, Typography & Design for Everyone`, lead text explaining this covers colors, Material Design themes, typography, internationalization, screen support, and accessibility
3. **For each topic section**, create a `<section>` with:
   - A chapter pill (e.g. `MODULE 3.2`)
   - A slide reference in small muted text (e.g. "Lecture 3.2, slide 10") — mapped to the PDF lecture notes
   - A hide/show answer button (toggle, answer shown by default on page load)
   - **Question-driven learning**: each section presents 2–4 exam-style questions with toggle answers
   - **Visualization after every answer**: code blocks, comparison tables, side-by-side cards, flow diagrams, etc.
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
| Color class | Ch 3.2 | Slide 3–8 — Color constructors (Color, fromARGB, fromRGBO), ColorSwatch, swatches 100–900, accent swatches |
| ColorSwatch | Ch 3.2 | Slide 8 — collection of colors related to a base color, custom palettes with named keys |
| Material Design | Ch 3.2 | Slide 10 — open-source design system by Google, default UI for Flutter |
| Styles vs Themes | Ch 3.2 | Slide 11 — Theme → App, Style → Widget |
| ThemeData | Ch 3.2 | Slide 12–16 — colorScheme, textTheme, Theme.of(context), app-wide themes, applying themes |
| Theme override | Ch 3.2 | Slide 17–18 — two ways: unique ThemeData instance or extend parent theme |
| Fonts & Typography | Ch 3.2 | Slide 21–22 — typeface, size, style, weight; TextTheme categories (Display, Headline, Title, Label, Body) + size variations |
| Google Fonts | Ch 3.2 | Slide 23 — fonts.google.com, using GoogleFonts package |
| Serif vs Sans-Serif | Ch 3.2 | Slide 24–25 — readability comparison at different sizes |
| Design for Everyone | Ch 3.2 | Slide 27–28 — accessible and usable by all, regardless of age/ability/background |
| Internationalizing | Ch 3.2 | Slide 30–41 — .arb files, flutter_localizations, localizationsDelegates, supportedLocales, language translation, date/number/currency formatting, text direction, ISO 639 codes |
| Supporting different screens | Ch 3.2 | Slide 42–58 — screen size/density categories (ldpi to xxxhdpi), adaptive design (Flexible, Expanded, FittedBox), platform-specific assets, orientation, display cutouts, minSdkVersion/targetSdkVersion |
| Accessibility - Navigation | Ch 3.2 | Slide 60–68 — Semantics widget, easy-to-follow navigation, large touch targets (min 48x48px, 8dp spacing), gesture navigation |
| Accessibility - Readability | Ch 3.2 | Slide 69–73 — color contrast, more than color for info, Material Design Tools, media accessibility (pause/stop, transcripts) |
| Accessibility - Guidance | Ch 3.2 | Slide 74 — clear interactive controls, text labels, tooltips, consistent terminology |

## Visualization examples to include

- **Color class table**: 4-column table (Constructor, Example, Use Case) for Color(), Color.fromARGB(), Color.fromRGBO(), ColorSwatch
- **Theme hierarchy diagram**: vertical flow — Theme (App-wide) → Style (Widget-level) → Specific widget overrides
- **ThemeData properties**: two-card layout — colorScheme (blue border) vs textTheme (green border)
- **Typography categories table**: 2-column (Category, Variations) — Display/Headline/Title/Label/Body × Small/Medium/Large
- **Internationalization setup flow**: numbered steps — pubspec.yml → .arb files → localizationsDelegates → supportedLocales
- **Screen density table**: 3-column (Size, Density, Example) — Small/Normal/Large/xLarge × ldpi to xxxhdpi
- **Accessibility checklist**: numbered list with icons — 6 accessibility methods (navigation, readability, guidance)
- **Touch target diagram**: side-by-side cards — "Do" (green border, 48×48px) vs "Don't" (red border, too small)

## Footer

`bmit2073 · chapter 3.2 · platforms themes and design · study guide`
