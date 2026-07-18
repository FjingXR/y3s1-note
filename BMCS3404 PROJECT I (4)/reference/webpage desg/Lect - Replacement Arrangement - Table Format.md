## Prompt

The timetable currently has a large empty area below the last row (Sunday) because the timetable container fills the remaining viewport height. Instead of leaving this space blank, redesign it into a **Selection Summary** panel.

### Goal

Transform the unused space directly below the timetable into a useful information panel that summarizes the user's selected replacement slots.

### Layout

The Selection Summary should span the full width of the timetable and visually feel like part of the timetable rather than a separate card.

It should have a subtle divider separating it from the timetable grid.

Use the existing theme variables (`--surface`, `--surface-variant`, `--outline`, `--primary`, etc.) instead of hardcoded colors.

---

## Panel Header

Display a header such as:

```
Selection Summary
```

or

```
Selected Replacement Slots
```

On the right side of the header display:

```
x / 4 Selected
```

where:

* first number = currently selected slots
* second number = maximum allowed selections

---

## Empty State

When nothing is selected, show a centered empty state.

Example:

```
No time slots selected.

Click an available (green) time slot to begin.
```

Optionally include a calendar or schedule icon.

Use muted colors.

---

## Selected State

Once the user selects slots, replace the empty state with a clean list.

Example:

```
✓ Saturday
03 Sep 2026
10:00 – 11:00

✓ Saturday
03 Sep 2026
11:00 – 12:00
```

Display each selected slot as a compact card or chip.

Each card should include:

* check icon
* day
* date
* start time
* end time

Arrange them:

* vertically if there are few selections
* or in a responsive grid (2–4 columns) depending on available width.

---

## Visual Design

Each selected slot card should have:

* background: `var(--primary-container)`
* text: `var(--on-primary-container)`
* subtle border
* rounded corners (8–10px)
* slight hover animation

Example structure:

```
✓ Saturday

03 Sep 2026

10:00 → 11:00
```

---

## Additional Information

Below the selected slots, show a small summary such as:

```
Total Selected:
2 of 4 slots

Total Duration:
2 hours

Building:
B104
```

---

## Remove Action

Each selected slot should have a small "×" button or trash icon to deselect that slot without clicking the timetable again.

Hover:

* background becomes `var(--error-container)`
* icon becomes `var(--error)`

---

## Footer

At the bottom of the Selection Summary panel display:

```
Tip:
You can select up to 4 available time slots.
```

or

```
Click another green time slot to add more selections.
```

---

## Responsive Behavior

On desktop:

* summary appears below the timetable
* cards arranged in multiple columns

On tablets:

* 2 columns

On mobile:

* single column

---

## Animation

When a slot is selected:

* card fades in
* slight slide upward
* duration around 200ms

When removed:

* fade out smoothly

---

## Requirements

* Generate the panel dynamically from the selected timetable cells.
* Keep the Proceed button enabled only when at least one slot is selected.
* The selection counter should update automatically.
* The panel should replace the previous empty area so there is no unused whitespace below the timetable.

The final design should feel like a modern Material Design scheduling application, making the previously empty space informative and useful while maintaining the overall layout and theme.
