# **Chapter 2 : Quarter-final** 

# **2.1 Current Class Replacement Workflow at TARUMT**

**2.1.1 View-Only Timetable Systems**

**TARCApp (Students)**

- TARCApp is TARUMT's central mobile/web application used across **all branches** (KL, Penang, Perak, Johor, Pahang, Sabah)  
- Primary users: **students** — each student accesses their own personal timetable through the app  
- Function: **view-only** timetable system — no create, modify, or manage replacement classes  
- Timetable data visible: subject, time, venue, lecturer, cohort (confirmed schedules only)  
- **Limitations:**  
  - ❌ Pending replacement requests are **not shown** — students only see the final confirmed slot  
  - ❌ No email notifications — TARCApp does not send alerts for timetable changes

**Staff Intranet (Staff)**

- The web-based internal portal serving as the **authoritative timetable repository** for TARUMT Sabah

- Primary users: **lecturers and administrative staff** — each staff member accesses published schedules through institutional credentials

- Function: **view-only publication** of confirmed schedules — staff can browse timetable data but cannot create or manage replacement classes

- The authoritative source where Programme Leaders push confirmed replacement schedules after approval (§2.1.2, step 5\)

- **Limitations:**

  - ❌ Pending replacement requests are **not shown** — only final confirmed schedules are visible  
  - ❌ No email notifications — the intranet does not push alerts for timetable updates  
  - ❌ No replacement class management — no interface for proposing, approving, or tracking class replacement requests  
- A replacement audit trail — capturing who proposed a slot, what slot was involved, when the action occurred, and whether the outcome was approved or rejected — exists only for final published schedules in TAR Intranet, not for the replacement negotiation process

**2.1.2 Current Replacement Method (Google Sheets)**

- Current workflow when a lecturer is absent:  
  1. **Lecturer identifies replacement need** — knows their own absence or public holiday in advance  
  2. **Lecturer manually cross-references** — scans **multiple PDF files** (lecturer own availability, cohort timetable, room capacity) to find possible replacement slots  
  3. **Proposes a slot** — writes replacement details into a shared **Google Sheet** (subjects, proposed time, venue, affected cohort, etc)  
  4. **PL manually validates** — Programme Leader checks the proposal against PDF timetables to confirm no scheduling conflicts  
  5. **PL decides** — writes `"Y"` (approved) or `"N"` (rejected) in Google Sheets; if approved, **updates the timetable** in **TAR Intranet** (the authoritative system)  
- **Pain points:**  
  - ❌ No concurrency control — two Lecturers editing same sheet causes overwrite conflicts. This absence of transaction isolation mirrors the vulnerability that Kung and Robinson (1981) addressed through Optimistic Concurrency Control. Google Sheets Revision History logs changes but does not prevent overwrites (Google, 2026\)  
  - ❌ No conflict detection — overlapping slot assignments go unnoticed until discovered downstream  
  - ❌ Implicit state tracking — pending is represented by a blank cell (convention, not explicit), while approved (Y) and rejected (N) carry no timestamp or actor for each transition  
  - ❌ No real-time visibility — lecturers and students cannot see pending changes until confirmed in TAR Intranet  
  - ❌ Relies on **PDF scanning** — error-prone, time-consuming, no automated intersection  
  - The NP-hard complexity of timetabling (Babaei et al., 2015\) makes manual PDF cross-referencing inherently error-prone — the core pain point this system addresses (§1.2.1)  
  - Bernstein, Hadzilacos, and Goodman (1987) formally defined serializability as the correctness criterion for concurrent transaction processing — a standard that Google Sheets does not satisfy  
  - Schaerf (1999) classified timetabling as a constraint satisfaction problem — manual PDF cross-referencing provides no such constraint enforcement

Together, these findings validate the proposed system's adoption of a perspective-based state machine (Available → Pending (Self) / Reserved (Other) → Occupied) over the Current Replacement Method's binary Y/blank model, directly addressing the serializability gap identified by Bernstein et al. (1987).

**2.1.3 Gap Analysis: Existing Tools vs Proposed System**

| Capability | View-Only Systems (TARCApp & Staff Intranet) | Current Replacement Method (Google Sheets) | Proposed System |
| :---- | :---- | :---- | :---- |
| View timetable (confirmed) | ✅ All branches | ❌ | ✅ |
| View pending replacements | ❌ | ❌ | ✅ Student & Lecturer |
| Email notifications for updates | ❌ | ❌ | ✅ Submit/Approve/Reject |
| Automated conflict detection | ❌ | ❌ | ✅ Matrix intersection engine |
| Concurrency control | N/A (read-only) | ❌ No locks | ✅ OCC (version column) |
| State machine tracking | ❌ | ❌ | ✅ Available→Pending/Reserved→Occupied (role-dependent — same slot state, different label for proposer vs others) |
| FCFS Approval queue | ❌ | ✅ | ✅ FCFS queue |
| Replacement audit trail (who, what, when, outcome) | ✅ Final only | ❌ | ✅ Full history |
| Role-based access | ✅ (auth only) | ❌ | ✅ Student/Lecturer/PL |
| Cross-cohort availability search  | ❌ | ❌ (manual PDF only) |  ✅ Matrix intersection engine |

- **Key takeaway:** TARCApp and Staff Intranet both provide view-only schedules with **no write, no pending status, no notifications**. The Current Replacement Method (Google Sheets, Sabah branch) provides a manual editing surface but relies on **manual** **PDF scanning \+ manual validation** with zero locking or state tracking. The proposed system bridges both by combining TARCApp-like viewing with automated matrix intersection, OCC-based locking, and a full FCFS approval pipeline. Chen et al. (2021) confirmed that ad-hoc rescheduling remains understudied in the literature, further supporting the need for a dedicated replacement system.

# **2.2 Existing Timetabling Systems: A Comparative Review**

This section surveys general-purpose timetabling engines and academic approaches to constraint-based scheduling, positioning the proposed system within the existing literature and identifying the gap that motivates this project.

## **2.2.1 General-Purpose Timetabling Engines**

Three systems dominate practical university timetabling deployment:

- **aSc Timetables (automatic school timetable software)** — commercial, GUI-driven automatic timetable generator; ingests institutional constraints (rooms, lecturers, student groups, subjects) and produces a full-semester timetable via its proprietary solver (aSc Timetables, 2026\). However, aSc is designed for complete-semester generation; once published, all adjustments must be handled externally through Google Sheets (§2.1.2) — aSc offers no mechanism for post-publication single-slot replacement.  
- **FET (Free Timetabling Software)** — free, open-source constraint-based generator; encodes constraints as a single weighted constraint-satisfaction problem and uses a heuristic local-search algorithm to allocate all classes for a term (FET, 2026\)  
- **UniTime (University Timetabling System)** — open-source enterprise university timetabling; adopted by dozens of universities for course-level and examination scheduling, generating complete schedules from enrollment and room data (UniTime, 2026\)

Shared design assumption: all three **generate a complete timetable from scratch** at the start of a term. They assume no prior fixed schedule constrains the search, and they optimize across the entire semester.

Shared limitation for this project: none of the three supports **ad-hoc, single-slot replacement** on an already-published, locked timetable. They have no concept of "Cohort A and Cohort B both already hold fixed schedules; find a common free slot for one replacement class." Post-publication adjustments are performed by re-running the full solver or manual edits — not a targeted real-time search.

## **2.2.2 Academic Approaches**

The research literature is similarly oriented toward full-generation problems:

- **Constraint satisfaction** — Barták et al. (2010) survey constraint satisfaction as the foundational formalism for scheduling; timetabling is modelled as assigning resources to time slots under hard and soft constraints  
- **Foundational surveys** — Schaerf (1999) provides the canonical review of automated timetabling, cataloguing graph-colouring, integer programming, and constraint-based formulations  
- **Search-based approaches** — Lewis (2008) reviews search techniques for building university timetables, such as genetic algorithms (search that mimics natural selection). These methods work best when creating a complete timetable from scratch  
- **Hybrid and classification studies** — Babaei et al. (2015) classify timetabling approaches by technique; Chen et al. (2021) review them, confirming that the dominant research focus is initial timetable generation

Shared limitation: every surveyed approach targets **batch generation of an entire timetable**. None addresses real-time, bounded slot search on top of two pre-existing fixed schedules — the precise scenario this project confronts.

## **2.2.3 Gap Analysis**

- No surveyed commercial engine or academic method supports **cross-cohort replacement** where both cohorts already hold fixed, published schedules  
- The full-generation approach (constraint-based or search-based) is **too complex** for a single-slot adjustment and cannot give reliable, verifiable results within milliseconds  
- **This project's contribution**: a fast, reliable, real-time slot-search mechanism (the Matrix Intersection Algorithm, detailed in Chapter 3\) combined with Optimistic Concurrency Control and a Slot State Machine (both detailed in Chapter 3\) — a gap that existing literature does not cover  
- The proposed approach does not replace existing engines: it works *after* a timetable is published, handling the replacement process that general-purpose systems leave to manual PDF scanning (§2.1.2)

# **2.3 Comparative Analysis: Problem-Solution Mapping**

This section maps each pain point identified in the current workflow (§2.1) to a specific proposed feature and explains how it resolves the underlying limitation — demonstrating that the proposed system directly addresses every gap in the existing approaches surveyed in §2.2.

| Problem | Current Limitation | Proposed Feature | How It Solves It |
| :---- | :---- | :---- | :---- |
| Manual PDF cross-referencing | Lecturer scans 3+ PDF files (availability, cohort timetable, room capacity) and mentally intersects them — error-prone and time-consuming | Matrix Intersection Algorithm | Automates the search by computing the set intersection of Lecturer Availability ∩ Cohort A Timetable ∩ Cohort B Timetable ∩ Room Vacancy in milliseconds, returning only valid slots |
| No concurrency control | Two Lecturers editing the same Google Sheet row causes silent overwrites — the second writer's data replaces the first without detection | Optimistic Concurrency Control (OCC) via version column | Each slot has a version number; if another transaction committed between read and write, the version mismatch aborts the second attempt and notifies the client to retry — guarantees no lost updates |
| No state tracking | A replacement is either blank (unprocessed) or marked Y/N — no distinction between proposed, pending, approved, or rejected; a rejected proposal leaves no record | Slot State Machine (Available → Pending (Self) / Reserved (Other) → Occupied) | Each replacement follows an explicit lifecycle; every transition (propose, approve, reject) is recorded with timestamp and actor — the status is always known |
| No replacement audit trail | Who proposed which slot, when, and what the outcome was is lost after the sheet is updated | State machine \+ OCC combined | The state machine logs each transition (who, what slot, when, outcome), while OCC guarantees that concurrent edits do not corrupt the log; full accountability for every action |
| No real-time visibility | Students and Lecturers cannot see pending replacement requests until the PL confirms them in TAR Intranet | FCFS approval queue \+ email notifications | Replacement requests appear immediately in the dashboard upon submission; PL receives an email to review, and the outcome is emailed to the proposer — no waiting for manual broadcast |
| No write capability for replacement management (Staff Intranet) | Staff Intranet cannot create, propose, or track replacement requests — it only displays confirmed schedules | RBAC with role-specific interfaces | Each role (Student, Lecturer, PL) sees a customised dashboard: Lecturers propose slots, PLs approve/reject, Students view pending and confirmed changes; no role can act outside its permission boundary |

**Synthesis**

The three core pillars — Optimistic Concurrency Control, the Matrix Intersection Algorithm, and the Slot State Machine — work together as an integrated solution rather than isolated features. OCC ensures data integrity during concurrent booking attempts by outdated stale writes at the database level, which is essential because the FCFS queue must handle multiple Lecturers proposing overlapping slots simultaneously. The Matrix Intersection Algorithm addresses the root cause of the current workflow's inefficiency — manual PDF scanning — by automating availability search across four data sources in real time. The Slot State Machine provides lifecycle tracking that the current Google Sheets approach entirely lacks — where a replacement's status is inferred from whether a cell is blank (proposed), marked Y (approved), or marked N (rejected), with no enforced transition order and no history of who acted or when — giving every replacement an auditable record from proposal through to approval or rejection.

The literature supports each pillar individually: Kung and Robinson (1981) established OCC as a proven alternative to pessimistic locking for low-contention environments such as this one; Harel (1987) formalised state machines for modelling system behaviour, directly applicable to the replacement lifecycle; and Barták et al. (2010) surveyed constraint satisfaction as the foundational technique for scheduling problems, which the Matrix Intersection Algorithm applies in a bounded, real-time context. Together, these three pillars form a system that directly counters every limitation identified in §2.1 and §2.2 — no existing tool (aSc, FET, UniTime, Google Sheets, or TARCApp) provides this combination of concurrency-safe, state-tracked, automated cross-cohort slot search.



# **2.4 Feasibility Studies**

**2.4.1 Technical Feasibility**

- • The technology stack includes Laravel 13 (PHP 8.5+), PostgreSQL 16, TailwindCSS, Alpine.js, and Blade, all recognized open-source tools for web development.

- • Laravel supports Optimistic Concurrency Control with Eloquent (Laravel's database tool) version columns, background email sending via a database-backed queue driver, and session-based RBAC using Laravel Fortify (the login and permission system).

- • JetBrains (2024; 2025\) indicates Laravel's 61-64% adoption among PHP developers, solidifying its status as the leading PHP framework.

- • A study by Castillo and Castellanos (2026) ranked Laravel highest in learning curve and documentation quality, crucial for single-developer projects.

- • Szewczyk and Skublewska-Paszkowska (2025) found Laravel's code to be compact for the data volume, while Zajączkowski (2024) noted adequate CRUD performance, with human PDF scanning as the primary bottleneck.

- • PostgreSQL 16 is favored over MySQL for its concurrency control, offering Serializable Snapshot Isolation (SSI) with minimal performance overhead (Ports and Grittner, 2012).

- • Comparative benchmarks show PostgreSQL 16 outperforms MySQL 8.0 in complex transactions (14% higher speed) and analytics (3x faster).

- • PostgreSQL prevents double-booking errors that arose from concurrent edits, confirming its suitability for transaction-safe applications.

- • The Laravel Documentation (2026) validates the use of built-in features, ensuring no additional packages are necessary, which lowers implementation risks.

- • The project scale includes 14 lecturers, 14 cohorts, 23 rooms, and roughly 185 users, indicating that performance issues will likely come from human delays rather than database latency.

- • Laravel's code generation tools help minimize development time and ensure the stack meets all project requirements efficiently.

**2.4.2 Economic / Cost Feasibility**

- • All core technologies used are open-source with no licensing costs:  
  1. \- Laravel (MIT)  
  2. \- PostgreSQL (PostgreSQL license)  
  3. \- TailwindCSS (MIT)  
  4. \- Alpine.js (MIT)  
- • Development occurs entirely on localhost (CachyOS), which removes costs associated with hosting, domain, and servers.  
- • Mailtrap's free tier is enough for email testing during development.  
- • No paid APIs or third-party services are required, and personal hardware meets all system demands.  
- • Wheeler (2015) estimated that open-source software decreases total cost of ownership by 20–30% compared to paid options, confirming that the project incurs no direct financial costs.

**2.4.3 Operational Feasibility**

- • Target users at TARUMT Sabah are familiar with browser-based interfaces, easing the adoption of the new web-based system.  
- • The three-tier Role-Based Access Control (RBAC) corresponds to the existing organizational hierarchy (Student, Lecturer, Programme Leader), minimizing the learning curve for users.  
- • The First-Come-First-Served (FCFS) approval queue replicates the current email-based workflow (propose, validate, receive outcome), reducing process adaptation.  
- • The matrix intersection engine automates and improves upon the time-consuming task of manually scanning PDF files for available slots, offering real-time intersection.  
- • Whether users believe the system is useful (Davis, 1989\) is a key factor in technology acceptance, addressing a major pain point in the workflow.  
- • The FCFS queue includes necessary audit tracking, which is missing in the current Google Sheets approach.  
- • Adoption risk is moderate, as Lecturers will transition from PDF and Google Sheets to the new interface, which is reduced by retaining familiar role structures and simplifying interactions (few clicks to propose, one click to approve/reject).

**2.4.4 Schedule Feasibility**

The project is planned across two semesters. Five discrete modules (Matrix Engine, OCC, FCFS Queue, RBAC, Email) enable incremental delivery within time-boxed sprints.

### **FYP1 (Weeks 1–14): Documentation and Planning**

| Week | Milestone |
| :---- | :---- |
| 2 | Form 2 Proposal approval |
| 4 | Chapter 1 (Introduction) |
| 6 | System Requirements Specification, use case diagrams |
| 8 | Chapter 2 (Literature Review) |
| 9 | Database schema design |
| 10 | Chapter 3 (Methodology and Requirements) |
| 12 | Chapter 4 (System Design) |
| 13 | Interim prototype |
| 14 | Full FYP1 portfolio submission |

### **FYP2 (Weeks 1–7): Implementation and Defence**

| Week | Sprint | Deliverable |
| :---- | :---- | :---- |
| 2 | Sprint 1 | Matrix Intersection Engine |
| 4 | Sprint 2 | OCC and FCFS Dashboard integration |
| 5 | Sprint 3 | Full UI integration with RBAC |
| 6–7 | — | Final thesis compilation and viva defence |

The most technically challenging features — the Matrix Intersection Engine and OCC — are scheduled earliest in FYP2 to provide maximum testing time. This risk-prioritisation approach is consistent with Agile development practice (Sutherland & Schwaber, 2020). A total of 21 weeks across FYP1 and FYP2 for five well-defined modules is realistic.

**2.4.5 Legal & Ethical Feasibility**

- • The system only processes timetable schedules, staff names, and cohort codes.  
- • These data categories are exempt from Malaysia's Personal Data Protection Act 2010 (Act 709).  
- • TARUMT's current data classification allows timetable access for both staff and students.  
- • Development occurs exclusively on localhost, preventing any data from leaving the institution.  
- • No legal or ethical obstacles to implementation have been identified.

## **References**

Al-Hawari, F., Al-Ashi, M., Abawi, F., & Alouneh, S. (2020). A practical three-phase ILP approach for solving the examination timetabling problem. *International Transactions in Operational Research*, *27*(2), 924–944. [https://doi.org/10.1111/itor.12471](https://doi.org/10.1111/itor.12471)

aSc Timetables. (2026). *aSc Timetables — automatic school timetable software*. [https://www.a-sc.com/](https://www.a-sc.com/)

Babaei, H., Karimpour, J., & Hadidi, A. (2015). A survey of approaches for university course timetabling problem. *Computers & Industrial Engineering*, *86*, 43–59.

Barták, R., Salido, M. A., & Rossi, F. (2010). New trends in constraint satisfaction, planning, and scheduling: A survey. *The Knowledge Engineering Review*, *25*(3), 249–279. [https://doi.org/10.1017/S0269888910000202](https://doi.org/10.1017/S0269888910000202)

Bernstein, P. A., Hadzilacos, V., & Goodman, N. (1987). *Concurrency control and recovery in database systems*. Addison-Wesley.

Castillo, C., & Castellanos, O. (2026). Empirical evaluation of MVC frameworks: Performance, scalability, developer experience and learning curve. In *Advanced Research in Technologies, Information, Innovation and Sustainability (ARTIIS 2025)*, Communications in Computer and Information Science (Vol. 2792). Springer. [https://doi.org/10.1007/978-3-032-16851-1_24](https://doi.org/10.1007/978-3-032-16851-1_24)

Chen, M. C., Sze, S. N., Goh, S. L., Sabar, N. R., & Kendall, G. (2021). A survey of university course timetabling problem: Perspectives, trends and opportunities. *IEEE Access*, *9*, 106515–106529. [https://doi.org/10.1109/ACCESS.2021.3100613](https://doi.org/10.1109/ACCESS.2021.3100613)

Davis, F. D. (1989). Perceived usefulness, perceived ease of use, and user acceptance of information technology. *MIS Quarterly*, *13*(3), 319–340. [https://doi.org/10.2307/249008](https://doi.org/10.2307/249008)

FET. (2026). *FET free timetabling software*. [https://lalescu.ro/liviu/fet/](https://lalescu.ro/liviu/fet/)

Google. (2026). *Google Sheets API overview*. Google Developers. [https://developers.google.com/sheets/api](https://developers.google.com/sheets/api) (accessed 9 July 2026)

Harel, D. (1987). Statecharts: A visual formalism for complex systems. *Science of Computer Programming*, *8*(3), 231–274. [https://doi.org/10.1016/0167-6423(87)90035-9](https://doi.org/10.1016/0167-6423(87)90035-9)

JetBrains. (2024). *Developer Ecosystem Survey 2024*. [https://www.jetbrains.com/lp/devecosystem-2024/](https://www.jetbrains.com/lp/devecosystem-2024/)

JetBrains. (2025). *Developer Ecosystem Survey 2025*. [https://www.jetbrains.com/lp/devecosystem-2025/](https://www.jetbrains.com/lp/devecosystem-2025/)

Kung, H. T., & Robinson, J. T. (1981). On optimistic methods for concurrency control. *ACM Transactions on Database Systems*, *6*(2), 213–226.

Laravel Documentation. (2026). *Eloquent: Serialization*. [https://laravel.com/docs/11.x/eloquent-serialization](https://laravel.com/docs/11.x/eloquent-serialization)

Lewis, R. (2008). A survey of metaheuristic-based techniques for university timetabling problems. *OR Spectrum*, *30*(1), 167–190. [https://doi.org/10.1007/s00291-007-0097-0](https://doi.org/10.1007/s00291-007-0097-0)

Ports, D. R. K., & Grittner, K. (2012). Serializable snapshot isolation in PostgreSQL. *Proceedings of the VLDB Endowment*, *5*(12), 1850–1861. [https://doi.org/10.14778/2367502.2367523](https://doi.org/10.14778/2367502.2367523)

Schaerf, A. (1999). A survey of automated timetabling. *Artificial Intelligence Review*, *13*(2), 87–127. [https://doi.org/10.1023/A:1006576209967](https://doi.org/10.1023/A:1006576209967)

Sutherland, J., & Schwaber, K. (2020). *The Scrum Guide*. [https://scrumguides.org/scrum-guide.html](https://scrumguides.org/scrum-guide.html)

Szewczyk, M., & Skublewska-Paszkowska, M. (2025). Performance comparison of development frameworks in selected environments in REST API architecture. *Journal of Computer Sciences Institute*, *35*, 205–214. [https://doi.org/10.35784/jcsi.7041](https://doi.org/10.35784/jcsi.7041)

UniTime. (2026). *UniTime — university timetabling system*. [https://www.unitime.org/](https://www.unitime.org/)

Wheeler, D. A. (2015). *How to evaluate open source software / free software (OSS/FS) programs*. [https://dwheeler.com/oss_fs_eval.html](https://dwheeler.com/oss_fs_eval.html)

Zajączkowski, M. (2024). Performance comparison of working with a database in Spring Boot version 3.2.3 and Laravel version 8.83.27. *Journal of Computer Sciences Institute*, *32*, 205–209. [https://doi.org/10.35784/jcsi.6279](https://doi.org/10.35784/jcsi.6279)


