# Extra Set 1 — BMIT2073 Mobile Application Development

## Instructions
Answer all questions. Write your answers on separate sheets of paper.

---

## Question 1

### a)

(i) Construct a table to briefly compare between **Material Design** and **Cupertino** design systems based on the following FIVE (5) criteria:

- Platform focus
- Widget naming convention
- Navigation style
- Color scheme approach
- Default interaction behavior

(15 marks)

(ii) A developer is building a food delivery app that must run on both Android and iOS. Select the most suitable design system (Material Design or Cupertino) and briefly justify your selection.

(2 marks)

### b)

Identify the FOUR (4) primary states in the Flutter app lifecycle (explanation is not required). In addition, provide a suitable task example for each of them.

(8 marks)

---

**[Total: 25 marks]**

---

## Question 2

### a)

Provide TWO (2) differences between StatelessWidget and StatefulWidget.

(4 marks)

### b)

Discover THREE (3) approaches for efficient image loading in relation to performance best practices for mobile apps.

(6 marks)

### c)

Present any TWO (2) methods of internationalising mobile apps for adapting to different languages, cultures, and regions. Briefly elaborate your answers.

(4 marks)

### d)

Examine TWO (2) differences between AlertDialog and Snackbar. Then, explain when you would use each of them.

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

| Criteria | Material Design | Cupertino |
|---|---|---|
| **Platform focus** | Android, web, and desktop | iOS and macOS only |
| **Widget naming convention** | Uses generic names (AppBar, Button, Card) | Prefixed with "Cupertino" (CupertinoNavigationBar, CupertinoButton) |
| **Navigation style** | Drawer-based navigation, bottom navigation bar | Tab bar at bottom, swipe-based navigation |
| **Color scheme approach** | Uses ColorScheme with seed colors and Material palette | Follows Apple's Human Interface Guidelines color palette |
| **Default interaction behavior** | Ripple touch feedback, material elevation on press | Smooth transitions, iOS-style haptic feedback |

#### a)(ii) Selection and Justification

**Material Design** is more suitable because the app targets both Android and iOS. Material Design is Flutter's default and works across all platforms. Using Cupertino would only suit iOS users. Alternatively, the developer could use Material Design as the base and add Cupertino widgets for iOS-specific screens.

#### b) App Lifecycle States

| State | Task Example |
|---|---|
| **Resumed** | Play audio or video, process user interactions (taps, swipes), fetch and display data |
| **Paused** | Pause animations and location updates, save unsaved user data, release non-essential resources |
| **Inactive** | Briefly pause ongoing network requests, prepare for potential state change |
| **Detached** | Clean up resources (close databases, release memory), persist critical data before app closes |

---

### Question 2

#### a) Differences between StatelessWidget and StatefulWidget

| StatelessWidget | StatefulWidget |
|---|---|
| Does not hold any internal state; appearance is fixed after building | Maintains its own state which reacts to user interactions or data changes |
| Does not rebuild when data changes; no setState() method | Rebuilds via setState() when state changes |

#### b) Three Approaches for Efficient Image Loading

1. **Use Image.network with caching** — Implement appropriate caching and loading strategies for network images to reduce repeated downloads.
2. **Optimize image size** — Resize images to the appropriate size for the app to avoid loading unnecessarily large files that waste memory.
3. **Use efficient image formats** — Use formats like WebP instead of JPEG, PNG, or GIF to reduce file size while maintaining quality.

#### c) Two Methods of Internationalisation

1. **Language Translation** — Create .arb (Android Resource Bundle) files for each supported language and use Intl.message() to mark translatable strings. At runtime, the appropriate string resource set is loaded based on the device locale.
2. **Date, Number, and Currency Formatting** — Use Intl.NumberFormat and Intl.DateFormat to format dates, numbers, and currencies according to the user's locale (e.g., different currency symbols, date order, decimal separators).

#### d) Differences between AlertDialog and Snackbar

| AlertDialog | Snackbar |
|---|---|
| High priority — requires user action before continuing | Low priority — informs user without blocking |
| Blocks app usage until user taps a button or dismisses | Disappears automatically after a few seconds |

**When to use AlertDialog:** Use when the user must make a critical decision or acknowledge important information (e.g., "Are you sure you want to delete this item?").

**When to use Snackbar:** Use for brief, non-critical messages about actions that just happened (e.g., "Item deleted" with an optional Undo button).

#### e) Five Navigation Principles

1. **Fixed start destination** — Every app has a fixed start destination; this is also the last screen seen when returning to the launcher after pressing Back.
2. **Navigation state is represented as a stack of destinations** — The top of the stack is the current screen; previous destinations represent history.
3. **Up and Back are identical within your app's task** — The Up button (in the app bar) and the Back button behave identically within the app.
4. **The Up button never exits your app** — At the start destination, the Up button does not appear because it never exits the app.
5. **Deep linking simulates manual navigation** — A deep link should navigate the user to the same screen as if they had navigated manually through the app.
