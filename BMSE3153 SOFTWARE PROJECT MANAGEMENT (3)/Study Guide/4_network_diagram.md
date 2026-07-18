# 4. Project Network Diagram & Critical Path

## What Is a Network Diagram?
A **network diagram** (Activity-on-Node / AON) shows tasks as **boxes (nodes)** and **arrows** show **precedence** (which task must finish before another starts).

- Each node shows: **Task ID / Task name / Duration**
- Arrow → means "must be completed before"

Drawn from a table of: **Task ID, Task Name, Duration, Predecessor**.

## How to Draw It (Step by Step)
1. List every task with its duration.
2. For each task, draw an arrow **from its predecessor(s)** into it.
3. Tasks with **no predecessor** start from the beginning.
4. A task with **multiple predecessors** (e.g. F needs C and E) only starts after **all** are done.
5. Find every path from start to end, sum the durations.

## PERT 3-Point Estimate (for uncertain durations — Chp2)
When a single duration is hard to estimate, use three estimates:
- **O** = Optimistic, **ML** = Most Likely, **P** = Pessimistic

    Expected time  te = (O + 4·ML + P) / 6

*Example (Chp2 activity F): O=3, ML=4, P=8 → te = (3+16+8)/6 = 4.5 weeks.*

## Critical Path
- The **critical path = the longest path** through the network.
- **Any delay on the critical path delays the whole project.**
- It determines the **minimum total project duration**.

---

## Worked Example — Tutorial 2, Question 2
**Table 1:**
| Task | Name | Duration (wks) | Predecessor |
| --- | --- | --- | --- |
| A | Collect requirements | 1 | None |
| B | Design online module | 1 | A |
| C | Code online module | 2 | B |
| D | Design offline module | 1 | A |
| E | Code offline module | 1 | D |
| F | Testing (online & offline) | 2 | C, E |

**(a) Network diagram (ASCII):**

```
        ┌─1wk─┐   ┌─1wk─┐   ┌─2wk─┐
    ───▶│  A  │──▶│  B  │──▶│  C  │──┐
   start└──────┘   └──────┘   └──────┘  │
        │                               ▼
        │   ┌─1wk─┐   ┌─1wk─┐   ┌─2wk─┐
        └──▶│  D  │──▶│  E  │──▶│  F  │──▶ end
            └──────┘   └──────┘   └──────┘
```
*(F starts only after BOTH C and E finish.)*

**(b) Critical path & total duration:**
- Path 1: **A → B → C → F** = 1 + 1 + 2 + 2 = **6 weeks**
- Path 2: A → D → E → F = 1 + 1 + 1 + 2 = **5 weeks**

> **Critical path = A → B → C → F**
> **Total project duration = 6 weeks**

Any delay in A, B, C, or F delays the whole project. D and E have 1 week of slack (they could be delayed up to 1 week without delaying the project).

---

## Related: Gantt Chart (Tutorial 2 Q3)
A Gantt chart is a bar chart of the same tasks; bars start after predecessors finish.
For the Q3 table (durations in months: 1=1, 2=1, 3=1.5, 4=1, 5=1, 6=1.5; pred: 1=None, 2=1, 3=2, 4=1, 5=4, 6=3&5):
- Task 6 starts after tasks 3 and 5 both finish. Task 3 ends at month 1+1+1.5 = 3.5; Task 5 ends at month 1+1+1 = 3. Starting June 2024, Task 6 begins ≈ **October 2024** and finishes ≈ **November/December 2024 (month ~5.5)**.

---

## Exam Tips
- Draw the diagram FIRST, then list every path and sum durations.
- Critical path = **longest** total duration (not shortest!).
- Tasks not on the critical path have **slack/float**.
- If the question gives O/ML/P, compute `te = (O + 4ML + P)/6` first, then use te as the duration.
