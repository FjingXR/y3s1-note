## Software Process Model: Incremental Model

### Selected Model

The **Incremental Model** has been chosen for the Jobs Recruitment Website project. Under this model, the system is developed in smaller functional releases known as increments. Each increment includes a set of features that undergo design, development, testing, and review before progressing to the next increment.

The model suits this project because the Jobs Recruitment Website consists of **independent modules** — User Management, Job Seeker Portal, Employer Portal, Recruitment Management, Resume Management, Notification, and Administration — each of which can be developed as a separate increment without blocking others.

---

### Advantages

**1. Early stakeholder visibility and validation**

Core functions such as user registration, job seeker profile creation, and job vacancy browsing can be delivered in Increment 1 within the first month of development. This allows LingJiaBan Co.'s management and recruitment officers to interact with a working system early in the project timeline rather than waiting until full completion. Feedback from these early reviews can be incorporated into subsequent increments, reducing the risk of delivering a system that does not align with business needs. This is especially important for a client transitioning from manual to digital processes, as they can progressively adapt to the new system.

**2. Flexible requirement handling**

Since the Incremental Model develops modules independently, changes requested by LingJiaBan's stakeholders during the review of earlier increments can be accommodated without disrupting the entire system architecture. For example, if recruitment officers request additional filter fields in the Candidate Search function after testing Increment 1, changes can be scoped within the Recruitment Management Module (Increment 3) without affecting the already-completed User Management or Job Seeker modules. This flexibility is critical for this project, as LingJiaBan Co. is moving from a fully manual workflow to a digital platform and may discover new requirements as they see each increment.

---

### Disadvantages

**1. Integration complexity**

As independent modules such as the Notification Module and Recruitment Management Module are developed in separate increments, ensuring they communicate correctly through a shared database and unified user interface becomes increasingly difficult. For example, the Job Seeker Module (Increment 1) and the Notification Module (Increment 4) must integrate so that job applications trigger email alerts — a dependency that may not surface until late in development. This requires additional integration testing between increments and careful API contract design, which may extend the testing phase beyond initial estimates.

**2. Coordination and planning overhead**

Managing multiple increments requires detailed release planning, strict version control, and continuous alignment with the client's priorities. The Project Manager must define clear boundaries for each increment, ensure no two increments overlap in conflicting ways, and prevent scope creep from one increment leaking into another. This increases administrative effort and documentation requirements compared to a sequential model like Waterfall, placing greater demand on the small four-person team to maintain disciplined project management practices.

---

### Transparency with Stakeholders

Communicating these disadvantages transparently to LingJiaBan Co.'s stakeholders ensures informed decision-making and aligns with professional conduct standards. By disclosing that integration complexity and coordination overhead are trade-offs for early visibility and flexibility, the project team demonstrates ethical project management practices under CLO3 — building trust and managing stakeholder expectations realistically from the outset.
