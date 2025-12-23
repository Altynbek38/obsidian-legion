
***

# Lecture 14 Test Planning
#TestPlanning #TestStrategy #RiskManagement #IEEE29119 #ExamPrep

## 1. Contextual Factors
Testing is **context-dependent**. The approach is influenced by:
*   **SDLC Model:** (Waterfall, Agile, V-Model).
*   **Test Levels/Types:** (Unit, Integration, System, Acceptance).
*   **Business Domain:** (e.g., Banking requires higher security than a Game).
*   **Risks:** Product and Project risks.
*   **Constraints:** Budget, resources, deadlines, regulations.
*   **Standards:** Internal policies or external compliance (ISO, IEEE).

## 2. The Testing Process (7 Core Activities)
A standard testing process consists of the following sequential (often overlapping) activities:

1.  **Test Planning:** Defining objectives and the approach to meet them.
2.  **Test Monitoring and Control:**
    *   *Monitoring:* Comparing actual progress vs. the plan.
    *   *Control:* Taking corrective actions to get back on track.
3.  **Test Analysis:** Analyzing the *Test Basis* (requirements) to identify *what* to test (Test Conditions).
4.  **Test Design:** Designing test cases and data. Determining *how* to test.
5.  **Test Implementation:** Creating test procedures, scripts, and setting up the environment. Checking if we are *ready* to run.
6.  **Test Execution:** Running the tests, logging results, reporting defects.
7.  **Test Completion:** Closing defect reports, archiving ware, creating summary reports, and analyzing lessons learned.

## 3. Test Strategy
A generalized description of the test process, usually at the product or organizational level.

### Common Types of Test Strategies
1.  **Model-based:** Tests designed based on a specific model (e.g., business process model, reliability model).
2.  **Process-compliant (Standard-compliant):** Follows external rules/standards (e.g., IEEE, industry regulations).
3.  **Directed (Consultative):** Driven by advice/guidance from stakeholders or domain experts.
4.  **Analytical:** Based on analysis of a specific factor.
    *   *Example:* **Risk-based testing** (prioritizing tests based on risk level).

## 4. Risk Management
**Risk** is the possibility of a future negative event.
$$Risk = Likelihood \times Impact$$

### Types of Risks
*   **Project Risks:** Risks to the project's success/management.
    *   *Examples:* Delays, inaccurate estimates, insufficient funds, skill shortages, personnel conflicts.
*   **Product Risks:** Risks to the quality of the software itself.
    *   *Examples:* Software fails to perform functions, poor architecture, incorrect computations, poor user experience.

### Risk-based Testing Strategy
*   Start testing early.
*   Perform constant risk analysis.
*   **Prioritize:** Focus testing on highest risks.
*   Don't ignore low risks (but test them less).
*   Perform regression testing.

## 5. The Test Plan Document
Documentation describing test objectives, resources, and schedule. It coordinates testing activities.

### Types of Plans
*   **Master Test Plan:** Coordinates multiple test levels (e.g., for the whole project).
*   **Level Test Plan:** Addresses a specific level (e.g., "System Test Plan").

### Content (based on ISO/IEC/IEEE 29119-3)
A good test plan includes:
*   **Scope & Objectives:** What is in/out of scope.
*   **Risk Register:** Identified risks.
*   **Test Strategy:** The overall approach.
*   **Testing Activities & Estimates:** What needs to be done and how long it takes.
*   **Staffing & Schedule:** Who and When.
*   **Context:** Introduction and specific document info.

### What should be in the plan? (Practical view)
*   **Approach:** How testing will be carried out.
*   **Decisions:** What to test, people required, resources needed.
*   **Metrics:** Selection of metrics for monitoring.
*   **Budgeting:** Cost estimation.

## Key Takeaways
1.  **Context is King:** Testing differs based on the project context.
2.  **Risk Drives Testing:** Identify Product and Project risks to prioritize efforts effectively.
3.  **The Plan is a Map:** A clear test plan ensures everyone knows the objectives, schedule, and responsibilities.
4.  **ISO Standard:** IEEE 29119-3 provides the standard structure for test documentation.