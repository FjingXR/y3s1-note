# Extra Set 2 — BMIT2073 Mobile Application Development

## Instructions
Answer all questions. Write your answers on separate sheets of paper.

---

## Question 1

### a)

(i) Construct a table to briefly compare between **single-child layout widgets** and **multi-child layout widgets** based on the following FIVE (5) criteria:

- Number of children supported
- Common examples
- Arrangement control
- Spacing control
- Typical use case

(15 marks)

(ii) A developer is building a photo gallery app that displays images in a scrollable grid. Select the most suitable layout type (single-child or multi-child) and briefly justify your selection.

(2 marks)

### b)

Identify the FOUR (4) primary states in the Flutter app lifecycle (explanation is not required). In addition, provide a suitable task example for each of them.

(8 marks)

---

**[Total: 25 marks]**

---

## Question 2

### a)

Provide TWO (2) differences between ephemeral state and app state.

(4 marks)

### b)

Discover THREE (3) accessibility features that should be implemented in mobile apps to support users with disabilities.

(6 marks)

### c)

Present any TWO (2) methods of supporting different screen sizes and densities in mobile apps. Briefly elaborate your answers.

(4 marks)

### d)

Examine TWO (2) differences between TabBar navigation and Drawer navigation. Then, explain when you would use each of them.

(6 marks)

### e)

Identify the FIVE (5) navigation principles (explanation is not required).

(5 marks)

---

**[Total: 25 marks]**

---

## Suggested Answers

### Question 1

#### a)(i) Comparison Table

| Criteria | Single-Child Layout Widgets | Multi-Child Layout Widgets |
|---|---|---|
| **Number of children supported** | One child only | Multiple children |
| **Common examples** | Container, Padding, Align, Center, SizedBox | Row, Column, ListView, GridView, Stack, Wrap |
| **Arrangement control** | Positions or sizes the single child within the parent | Arranges multiple children horizontally, vertically, or in a grid |
| **Spacing control** | Uses padding, margin, or SizedBox for spacing | Uses mainAxisAlignment, crossAxisAlignment, or spacing properties |
| **Typical use case** | Wrapping and styling a single element | Building complex layouts with groups of widgets |

#### a)(ii) Selection and Justification

**Multi-child layout widgets** are more suitable because a photo gallery requires arranging multiple images in a scrollable grid. GridView (a multi-child widget) is designed for this purpose — it displays items in a 2D scrollable grid. A single-child widget cannot handle multiple images at once.

#### b) App Lifecycle States

| State | Task Example |
|---|---|
| **Resumed** | Process user interactions (taps, swipes), play audio or video, fetch and display data |
| **Paused** | Pause animations and location updates, save unsaved user data, release non-essential resources |
| **Inactive** | Briefly pause ongoing network requests, prepare for potential state change |
| **Detached** | Clean up resources (close databases, release memory), persist critical data before app closes |

---

### Question 2

#### a) Differences between Ephemeral State and App State

| Ephemeral State | App State |
|---|---|
| Local state contained within a single widget | Global state shared across many parts of the app |
| Managed using StatefulWidget and setState() | Managed using libraries like Provider, Riverpod, or BLoC |

**Example of ephemeral state:** Current page in a PageView, current selected tab in a BottomNavigationBar.

**Example of app state:** Shopping cart in an e-commerce app, user login/authentication info, user preferences.

#### b) Three Accessibility Features

1. **Screen reader support (Semantics)** — Use the Semantics widget to describe UI elements so that screen readers can announce them to visually impaired users.
2. **Adequate colour contrast** — Ensure text has sufficient contrast against its background so that users with low vision or colour blindness can read it. Use tools like the Material Design colour picker to verify contrast ratios.
3. **Large touch targets** — Make interactive elements at least 48×48 pixels with adequate spacing (minimum 8dp) between them so that users with motor impairments can tap accurately.

#### c) Two Methods of Supporting Different Screen Sizes

1. **Adaptive design with Flexible and Expanded** — Use these widgets to distribute space among child widgets so that layouts adjust dynamically to different screen sizes. Flexible lets children shrink or grow based on available space, while Expanded forces children to fill available space.
2. **Responsive images with FittedBox** — Use FittedBox to scale images to fit the available space without distortion. Also provide different image assets for different screen densities (1x, 2x, 3x) in separate asset folders.

#### d) Differences between TabBar and Drawer

| TabBar | Drawer |
|---|---|
| Displays tabs at the top of the screen; content switches within the same view | Slides in from the left edge; navigates to entirely different screens |
| Best for 2–5 related sections | Best for 5+ destinations or deep navigation hierarchy |

**When to use TabBar:** Use when you have 2 to 5 related sections that users switch between frequently (e.g., music genres, chat contacts vs settings).

**When to use Drawer:** Use when you have 6 or more destinations, multiple levels of navigation hierarchy, or need quick access between unrelated sections of the app.

#### e) Five Navigation Principles

1. **Fixed start destination** — Every app has a fixed start destination; this is also the last screen seen when returning to the launcher after pressing Back.
2. **Navigation state is represented as a stack of destinations** — The top of the stack is the current screen; previous destinations represent history.
3. **Up and Back are identical within your app's task** — The Up button (in the app bar) and the Back button behave identically within the app.
4. **The Up button never exits your app** — At the start destination, the Up button does not appear because it never exits the app.
5. **Deep linking simulates manual navigation** — A deep link should navigate the user to the same screen as if they had navigated manually through the app.
