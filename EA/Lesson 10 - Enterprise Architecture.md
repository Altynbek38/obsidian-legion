### **Lesson #10 - Opportunities, Solutions & Implementation (Phases E, F, G)**

This lesson moves from "Designing the Architecture" to "Making it Happen." It covers how to plan the migration, how to manage projects (Waterfall vs. Agile), and how to govern the implementation.

---

### **Part 1: Lecture Notes (Vital for Exam)**

#### **► Phase E: Opportunities and Solutions**
Phase E is where we figure out **how** to deliver the architecture we designed in Phases B, C, and D.

*   **Objective:**
    *   Generate the initial **Architecture Roadmap**.
    *   Identify **Work Packages** (groups of changes) to implement the Target Architecture.
    *   Identify **Transition Architectures**. (If the change is too big to do in one step, we define intermediate steps).
*   **Key Output:** The roadmap showing "what we will build and when."

#### **► Phase F: Migration Planning**
Phase F takes the roadmap from Phase E and turns it into a detailed, funded project plan.

*   **Objective:**
    *   Finalize the **Implementation and Migration Plan**.
    *   Calculate the **Cost, Time, and Risk** of the project.
    *   Integrate with the company's Portfolio/Project Management office.
*   **Critical Concept:** Project Management (PM) is **not** part of TOGAF ADM, but Phase F is where Architecture *handshakes* with Project Management.

#### **► Implementation Techniques (Project Management)**
Once the architecture is planned, it must be built. There are different methodologies to manage this:

1.  **Waterfall:** Linear approach (Requirements -> Design -> Implementation -> Verification). Best when requirements are fixed and clear.
2.  **Agile (Scrum):** Iterative approach.
    *   **Sprints:** Short cycles (2-4 weeks) to deliver working software.
    *   **Roles:** Product Owner (defines value), Scrum Master (facilitates), Team (builds).
    *   **Artifacts:** Backlog (list of tasks), Burndown Chart (progress).
3.  **Kanban:** Visual workflow management (To Do -> Doing -> Done). Focuses on continuous flow and limiting "Work In Progress."
4.  **Six Sigma (DMAIC):** Focuses on quality control and removing defects (Define, Measure, Analyze, Improve, Control).

#### **► Phase G: Implementation Governance**
*   **Goal:** Ensure the builders (developers/engineers) follow the architect's design.
*   It functions as a "compliance check" during the building process.

---

### **Part 2: Practice Session Notes (Case Study: Amazon)**

*   **Amazon's Evolution:** Started as a bookstore (1994), now the "Everything Store" and a tech giant (AWS).
*   **Deep Learning (The Future):** Amazon uses Deep Learning across all products:
    *   **Recommendation Engine:** "People who bought X also bought Y."
    *   **Logistics:** Predicting where to store products before they are ordered.
    *   **Alexa:** Voice recognition.
*   **Amazon Go ("Just Walk Out" Technology):**
    *   **Concept:** No checkout lines. Grab and go.
    *   **Architecture Behind It:**
        1.  **Computer Vision:** Cameras track you and the items.
        2.  **Sensor Fusion:** Combines data from cameras and weight sensors on shelves.
        3.  **Deep Learning:** Algorithms process the data in real-time to identify "who took what."
    *   *Significance:* This is a perfect example of **Technology Architecture (Phase D)** enabling a revolutionary **Business Architecture (Phase B)**.

---

### **Part 3: Assignment #05 - Answers**

These answers combine the lecture logic with the assignment prompts.

**Question 1: Why do you think that AR has a bright future comparing to VR even though there is a metaverse world behind VR? Please use VisionPro as an example.**

AR (Augmented Reality) has a brighter future because it *adds* to the real world rather than replacing it, making it more practical for daily use. VR (Virtual Reality) isolates the user.
*   **VisionPro Example:** Apple’s Vision Pro uses "Spatial Computing" (Passthrough AR). It allows users to see their physical room while floating digital apps in front of them. This enables collaboration and productivity in the real world, whereas VR is mostly limited to gaming or total immersion simulations.

**Question 2: Please describe how Amazon GO works.**

Amazon Go uses "Just Walk Out" technology, which relies on three key technologies found in self-driving cars:
1.  **Computer Vision:** Hundreds of cameras track customer movement.
2.  **Sensor Fusion:** Weight sensors on shelves detect when an item is picked up or put back.
3.  **Deep Learning:** The system processes this data to create a "virtual cart." When the customer leaves, the system automatically charges their Amazon account.

**Question 3: Please describe Emerging Technologies in Technology Architecture. Why is it important for companies to consider?**

Emerging technologies (defined in **Phase D**) are new tech trends that disrupt industries (e.g., AI, Metaverse, Neuromorphic Computing).
*   **Importance:** Companies must consider them because they act as **drivers for business transformation**. If a company ignores emerging tech (like Nokia ignored smartphones or Blockbuster ignored streaming), their Business Architecture becomes obsolete. The Technology Architecture must identify these opportunities (Phase E) to keep the business competitive.

**Question 4: Why is there no meaning to apply ADM if there are no opportunities and solutions in Phase F ADM?**

*(Correction: Opportunities are identified in Phase E, Plan is made in Phase F).*
If there are no opportunities or solutions identified (Phase E) and no implementation plan (Phase F), the architecture remains just a theoretical model or a "drawing on paper." The goal of TOGAF ADM is to deliver **business value**. Without the **Migration Plan (Phase F)** to actually execute the changes, the organization cannot move from the Baseline (AS-IS) to the Target (TO-BE), rendering the architectural effort useless.