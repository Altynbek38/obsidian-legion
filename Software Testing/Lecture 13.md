
***

# Lecture 13: Software Development Methodologies
#SDLC #Waterfall #VModel #Agile #Lean #ExamPrep

## 1. Software Development Life Cycle (SDLC)
A framework defining the phases and activities of the software creation process.
*   **Goal:** Deliver high-quality software in line with client expectations while lowering risks.
*   **Testing in SDLC:**
    *   For every development activity, there is a corresponding **test activity**.
    *   Testing should start **early** (reviewing requirements/drafts) to minimize cost of defects.

## 2. Sequential Models
Linear progression where one phase must finish before the next begins.

### A. Waterfall Model
*   **Process:** Requirements $\rightarrow$ Design $\rightarrow$ Implementation $\rightarrow$ Testing $\rightarrow$ Maintenance.
*   **Pros:** Simple, easy to manage, clear milestones.
*   **Cons:** No working software until the end, high risk, difficult to handle changes.
*   **Usage:** Best for projects with **fixed, stable requirements** (e.g., Military, Nuclear control systems).

### B. V-Model
*   **Concept:** Extension of Waterfall where execution of tests is sequential, but test *design* happens early.
*   **Structure:** Each development phase has a corresponding testing phase.
    *   *Requirements Analysis* $\leftrightarrow$ *Acceptance Testing*
    *   *System Design* $\leftrightarrow$ *System Testing*
    *   *Architecture Design* $\leftrightarrow$ *Integration Testing*
    *   *Module Design* $\leftrightarrow$ *Unit Testing*
*   **Advantage:** Supports early testing (verification) before coding begins.

## 3. Iterative & Incremental Models
Development is broken down into smaller cycles (iterations).

### A. Spiral Model
*   **Focus:** **Risk Analysis**.
*   **Flow:** Multiple spirals containing: Planning $\rightarrow$ Risk Analysis $\rightarrow$ Engineering $\rightarrow$ Evaluation.
*   **Usage:** Large, high-risk projects where requirements might change.

### B. Lean Model
Based on manufacturing principles (Toyota).
*   **Core Concepts:**
    *   **Identify Value:** What brings profit?
    *   **Eliminate Waste:** Remove anything useless.
    *   **Pull System:** Work is pulled only when there is demand.
    *   **Continuous Improvement:** Always optimizing the workflow.

***

# Agile & Testing in Agile
#Agile #Scrum #Kanban #Sprint #Manifesto #ExamPrep

## 1. The Agile Manifesto
A mindset focusing on iterative delivery and flexibility. The 4 Values:
1.  **Individuals and interactions** over processes and tools.
2.  **Working software** over comprehensive documentation.
3.  **Customer collaboration** over contract negotiation.
4.  **Responding to change** over following a plan.

## 2. Scrum Methodology
An iterative framework dividing work into time-boxed **Sprints** (1–4 weeks).
*   **3 Pillars:** Transparency, Inspection, Adaptation.

### Roles
*   **Product Owner (PO):** Owns the Product Backlog, prioritizes features, represents the business/customer.
*   **Scrum Master:** Facilitator, removes obstacles, ensures Scrum process is followed.
*   **Scrum Team:** Cross-functional team (Devs + QA) that delivers the work.

### Artifacts
*   **Product Backlog:** Prioritized list of all desired work (User Stories).
*   **Sprint Backlog:** Selected items to be done in the *current* Sprint.
*   **Burndown Chart:** Visualizes work remaining vs. time.

### Ceremonies (Events)
1.  **Sprint Planning:** Defining *what* to do (Sprint Backlog) and *how* to do it.
2.  **Daily Scrum:** 15-min sync (What did I do? What will I do? Blockers?).
3.  **Sprint Review (Demo):** Showcasing the *working software* to stakeholders for feedback.
4.  **Sprint Retrospective:** Team discusses *process* improvements (What went well? What didn't?).
5.  **Backlog Refinement:** Ongoing activity to break down and estimate future items.

## 3. Kanban Methodology
A flow-based method focusing on visualization and efficiency.
*   **Kanban Board:** Visualizes workflow (Columns: To Do, In Progress, Done).
*   **WIP Limits (Work-In-Progress):** Restricts how many tasks can be in a column at once to prevent bottlenecks.
*   **Philosophy:** "Stop starting, start finishing." (Pull system).

## 4. Scrum vs. Kanban

| Feature | **Scrum** | **Kanban** |
| :--- | :--- | :--- |
| **Cadence** | Time-boxed **Sprints** (e.g., 2 weeks). | Continuous flow (no fixed iterations). |
| **Roles** | Defined (PO, Scrum Master, Team). | No required roles. |
| **Release** | At the end of each Sprint. | Continuous delivery (whenever ready). |
| **Key Metric** | Velocity (Story points per sprint). | Cycle Time / Lead Time. |
| **Change** | No changes allowed mid-sprint. | Changes allowed anytime if capacity exists. |
| **Reset** | Board resets every sprint. | Board is persistent. |