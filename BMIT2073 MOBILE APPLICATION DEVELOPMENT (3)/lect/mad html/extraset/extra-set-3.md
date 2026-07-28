# Extra Set 3 — BMIT2073 Mobile Application Development

## Instructions
Answer all questions. Write your answers on separate sheets of paper.

---

## Question 1

### a)

(i) Construct a table to briefly compare between **Provider** and **setState** for state management based on the following FIVE (5) criteria:

- Scope of data sharing
- Data persistence
- Code complexity
- Best suited for
- When to use

(15 marks)

(ii) A developer is building a real-time chat application where messages must be shared across multiple screens and persist between sessions. Select the most suitable state management approach (Provider or setState) and briefly justify your selection.

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

Present any TWO (2) methods of loading images in Flutter from different sources. Briefly elaborate your answers.

(4 marks)

### d)

Examine TWO (2) differences between AlertDialog and SimpleDialog. Then, explain when you would use each of them.

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

| Criteria | Provider | setState |
|---|---|---|
| **Scope of data sharing** | Global — data can be accessed by any widget in the app | Local — data is confined to a single widget |
| **Data persistence** | Can persist between sessions when combined with storage solutions | Does not persist; data is lost when the widget is disposed |
| **Code complexity** | More setup required (provider class, ChangeNotifier, Consumer) | Simple — just call setState() within a StatefulWidget |
| **Best suited for** | Complex apps with data shared across multiple screens | Simple apps or widgets with self-contained state |
| **When to use** | When multiple widgets need the same data (e.g., shopping cart, user login) | When only one widget needs to track changes (e.g., toggle button, animation) |

#### a)(ii) Selection and Justification

**Provider** is the most suitable approach because a real-time chat app requires messages to be shared across multiple screens (chat list, chat room, notifications) and persist between sessions. Provider with ChangeNotifier allows all screens to listen for new messages and update automatically. setState cannot share data across screens or persist data.

#### b) App Lifecycle States

| State | Task Example |
|---|---|
| **Resumed** | Process user interactions (taps, swipes), play audio or video, fetch and display data |
| **Paused** | Pause animations and location updates, save unsaved user data, release non-essential resources |
| **Inactive** | Briefly pause ongoing network requests, prepare for potential state change |
| **Detached** | Clean up resources (close databases, release memory), persist critical data before app closes |

---

### Question 2

#### a) Differences between StatelessWidget and StatefulWidget

| StatelessWidget | StatefulWidget |
|---|---|
| Simpler; has a fixed appearance and behavior; does not hold any internal state | Maintains its own state which reacts to user interactions or data changes |
| Does not rebuild when data changes | Rebuilds via setState() when state changes |

#### b) Three Approaches for Efficient Image Loading

1. **Use Image.network with caching** — Implement appropriate caching and loading strategies for network images to avoid re-downloading the same images repeatedly.
2. **Optimize image size** — Resize images to the appropriate size for the app to avoid loading unnecessarily large files that consume excess memory and bandwidth.
3. **Use efficient image formats** — Use formats like WebP instead of JPEG, PNG, or GIF to reduce file size while maintaining acceptable quality.

#### c) Two Methods of Loading Images

1. **From assets (Image.asset)** — Store images in the app's assets folder, declare them in pubspec.yaml, and load them using Image.asset('path/image.png'). The system automatically selects the appropriate resolution variant (1x, 2x, 3x) based on the device's screen density.
2. **From network (Image.network)** — Load images from a URL using Image.network('https://example.com/image.jpg'). This is useful for dynamic content like user avatars or product photos. Note that network loading is asynchronous and may take time depending on connection speed.

#### d) Differences between AlertDialog and SimpleDialog

| AlertDialog | SimpleDialog |
|---|---|
| Displays a message that requires acknowledgment; user must take action | Offers a list of options for the user to choose from |
| Has a title, content area, and action buttons | Has a title and a list of selectable options (SimpleDialogOption) |

**When to use AlertDialog:** Use when you need to inform the user about a situation that requires acknowledgment or a decision (e.g., "Are you sure you want to delete this?" with Approve and Cancel buttons).

**When to use SimpleDialog:** Use when you want to present the user with multiple choices to select from (e.g., "Choose a department" with Treasury, State, Defence options).

#### e) Five Navigation Principles

1. **Fixed start destination** — Every app has a fixed start destination; this is also the last screen seen when returning to the launcher after pressing Back.
2. **Navigation state is represented as a stack of destinations** — The top of the stack is the current screen; previous destinations represent history.
3. **Up and Back are identical within your app's task** — The Up button (in the app bar) and the Back button behave identically within the app.
4. **The Up button never exits your app** — At the start destination, the Up button does not appear because it never exits the app.
5. **Deep linking simulates manual navigation** — A deep link should navigate the user to the same screen as if they had navigated manually through the app.
