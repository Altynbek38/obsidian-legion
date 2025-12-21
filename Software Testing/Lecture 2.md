
# Lecture 2: Requirements Analysis
#SoftwareTesting #Requirements #SMART #UseCase #ExamPrep

## 1. What are Requirements?
Requirements are a specification of what should be implemented. They describe how the system should behave, its properties, attributes, and constraints.
*   **The Communication Gap:** There is often a disconnect between what the customer explains, what the team understands, and what is actually built (The famous "Tree Swing" analogy).
*   **Cost of Fixing Errors:**
    *   **Specification/Design Phase:** Low cost ($1 - $10).
    *   **Release Phase:** Exponentially high cost ($1000+).
    *   *Takeaway:* Finding bugs during requirements analysis is the cheapest way to ensure quality.

## 2. Types of Requirements Formats

| Feature | **User Story** | **Use Case** |
| :--- | :--- | :--- |
| **Format** | Narrative, simple sentence structure. | Structured, tabular document. |
| **Structure** | "As a `<role>`, I want to `<goal>`, so that `<benefit>`." | Pre-conditions, Post-conditions, Main Flow, Alternative Flows, Exception Flows. |
| **Criteria** | Includes **Acceptance Criteria** (Conditions of satisfaction). | Includes specific input/output steps and system responses. |
| **Focus** | Focus on value/benefit to the user. | Focus on system functionality and steps. |

## 3. Stakeholders
Who needs the **Requirements Document**?
*   **Customer:** To verify needs.
*   **Project Management:** To plan scope and timeline.
*   **Development Team:** To build the feature.
*   **QA Team:** To design tests.
*   **Support:** To understand how to help users later.

## 4. Testing Requirements (The Analysis Process)
You cannot just "read" requirements; you must approach them to find gaps before code is written.

### What to analyze/look for:
*   **Inconsistencies:** Logic that contradicts itself.
*   **Testability:** Can this actually be tested?
*   **Dependencies:** Unaccounted external factors (e.g., 2FA, API limits).
*   **Alternative Flows:** What happens if the user clicks "Back"? What if they cancel?
*   **Negative Scenarios:** What if the internet cuts out? What if the password is wrong?
*   **Clarity:** Are error messages defined? Are next steps clear?

> **Example of Analysis (Change Password Feature):**
> *   *Requirement:* "User changes password."
> *   *QA Questions:* Do we handle 2FA? What if the IP is banned? What specific error message displays on failure? Where does the user go after success?

## 5. SMART Requirements
Ideally, requirements should follow the **SMART** criteria:

*   **S - Specific:** Defined goal, no unclear language (Who, What, Where, Why).
*   **M - Measurable:** Can you track progress? How do you know it's done?
*   **A - Attainable/Achievable:** Is the goal reasonable and within reach?
*   **R - Relevant:** Is it worthwhile? Does it fit business goals?
*   **T - Timely & Traceable:**
    *   *Timely:* Includes a time limit/deadline.
    *   *Traceable:* Can be tracked from origin to testing (e.g., Req ID $\rightarrow$ Test Case).

## 6. Visual Approaches to Requirements
Text is often insufficient. Visual aids help identify missing logic.

### A. User Flow Diagram
Visualizes the path a user takes through the system.
*   **Symbols:**
    *   *Oval:* Start/End.
    *   *Line:* Relationship/Direction.
    *   *Parallelogram:* Input/Output.
    *   *Rectangle:* Process.
    *   *Diamond:* Decision (Yes/No).
*   **QA Analysis of Flows:** Look for "Steps Back" (loops), dead ends, and missing decision outcomes.

### B. Prototypes
Visual mockups (UI/UX) of the application. Helps visualize the user journey before coding.

### C. Work Breakdown Structure (WBS)
A hierarchical decomposition of the total scope of work.
*   *Example:* **Ticket Reservation** (Root)
    *   1. Register
    *   2. Select Showtime
    *   3. Reserve Seat
    *   4. Payment
        *   4.1 Log on
        *   4.2 Select Method
        *   4.3 Confirm

## Key Takeaways
1.  The two main formats are **User Stories** and **Use Cases**.
2.  The whole team (Dev, QA, PM, Support) relies on requirements.
3.  Use **SMART** criteria to evaluate requirement quality.
4.  Don't just read; visualize using **Flow Diagrams**, **Prototypes**, and **WBS** to find hidden bugs.