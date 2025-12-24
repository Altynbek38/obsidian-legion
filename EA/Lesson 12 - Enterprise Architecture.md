### **Lesson #12 - Change Management & Requirements Management (Phase H & RM)**

This lesson covers the final phase of the ADM cycle (managing change) and the central process that drives the entire cycle (Requirements Management). It also discusses the role of the Business Analyst.

---

### **Part 1: Lecture Notes (Vital for Exam)**

#### **► Phase H: Architecture Change Management**
Phase H deals with the architecture *after* it has been implemented. It ensures the architecture remains relevant and provides value over time.

*   **Objective:**
    *   Ensure the architecture lifecycle is maintained.
    *   Ensure the Architecture Governance Framework is executed.
    *   Ensure the EA Capability meets current requirements.
*   **The Process:** It involves monitoring the business and technology environment (new drivers, new tech).
*   **Decision Point:** When a change is requested, Phase H determines:
    1.  **Simplification/Maintenance:** Handle it within the current cycle.
    2.  **Re-architecting:** Trigger a **new ADM cycle** (Start again at Phase A) because the change is too big (e.g., strategic shift, merger).
*   **Key Concept:** Architecture is dynamic, not static. It must flexible to evolve.

#### **► Requirements Management (RM)**
Requirements Management is **not** a sequential phase (like A, B, C). It is the **central circle** of the ADM diagram because it drives *all* other phases.

*   **Objective:**
    *   Manage architecture requirements identified during any execution of the ADM cycle.
    *   Ensure relevant requirements are available for use by each phase.
*   **Dynamic Nature:** Requirements are not static; they change constantly due to market changes, new legislation, or global shifts.
*   **Methods:** TOGAF doesn't mandate a specific tool but mentions methods like **ATAM** (Architecture Tradeoff Analysis Method) and **Volere** (testing requirements with "fit criteria").

#### **► The Role of Business Analysis**
The Business Analyst (BA) acts as a liaison between the business side and the service providers (IT).

*   **Responsibilities:**
    *   Analyze business needs.
    *   Identify business problems.
    *   Propose solutions.
    *   **Translation:** Translate business needs into specific requirements that developers/architects can act upon.

---

### **Part 2: Practice Session Notes (Case Study: Disney)**

*   **The Problem (2011):** Disney World faced declining customer satisfaction.
*   **The Solution: MyMagic+ ($1 Billion Investment):**
    *   **Components:** Website, Mobile App, and **MagicBand** (RFID wristband).
    *   **Functionality:** The MagicBand serves as a room key, ticket, wallet, and FastPass.
    *   **Data Architecture:** It acts as a "vacation management system," tracking guests in real-time.
    *   **Business Value:**
        *   **Personalization:** Characters can greet children by name (birthday greetings).
        *   **Efficiency:** Reduces friction (no lines for tickets/payment).
        *   **Result:** Satisfaction rating rose to >90% ("Very Good/Excellent").

*   **Streaming Strategy (Disney+ vs Netflix):**
    *   **Strategy:** "Quality over Quantity."
    *   **Content is King:** Leverages massive IP library (Disney, Pixar, Marvel, Star Wars, National Geographic).
    *   Unlike Netflix, which aims for volume, Disney focuses on retaining subscribers through high-value franchises (e.g., *The Mandalorian*).

---

### **Part 3: Assignment #06 - Answers**

*Note: This assignment combines concepts from Lesson 11 (Burberry, Realisation) and Lesson 12 (RM, Phase H).*

**Question 1: Why is the Requirements Management phase positioned at the center of the ADM cycle and connected to all other phases (excluding the Preliminary Phase)?**

Requirements Management is positioned at the center because requirements are **dynamic** and drive the entire architectural process. They are not just gathered once at the beginning; they are identified, updated, and refined in *every* phase (A through H). For example, a business requirement in Phase B might change due to a technical constraint discovered in Phase D. The central position ensures that changes in requirements are immediately propagated to all other affected phases, maintaining consistency.

**Question 2: What is the significance of the Architecture Change Management phase (Phase H) within the Architecture Development Method (ADM)? Discuss its primary objectives and explain why it is a necessary component.**

**Phase H** is significant because an enterprise architecture is a living entity, not a static document. Its primary objective is to manage changes to the architecture in a cohesive way.
*   **Why necessary:** Without Phase H, the architecture would quickly become obsolete as the business environment and technology landscape change. Phase H monitors these changes and decides whether to handle them as simple maintenance or to initiate a **new ADM cycle** (re-architecting), ensuring the EA capability remains viable and aligned with business value.

**Question 3: Analyze Burberry’s digital strategy in the context of enterprise architecture. What role did the implementation of an OmniChannel approach play in supporting Burberry’s success in the digital era?**

*(From Lesson 11)*
Burberry’s digital strategy transformed the brand from an aging icon into the "first fully digital luxury company."
*   **Omnichannel Approach:** This played a crucial role by removing the barriers between the online and physical worlds. Burberry synchronized its inventory and customer experience across all channels (Web, Mobile, Store).
*   **Example:** "Runway to Reality" allowed customers to buy items online immediately after seeing them on a live-streamed fashion show, rather than waiting months. This seamless integration revitalized the brand's appeal to younger generations (Millennials/Gen Z).

**Question 4: Please describe The Realisation Iteration. What Phase of ADM is it happening in parallel? Please provide some examples of people behind some company success.**

*(From Lesson 11)*
**The Realisation Iteration** involves the actual building and deployment of the solution. It happens in parallel with **Phase G (Implementation Governance)**. While the project managers and developers build the system, the architects provide oversight to ensure compliance.
*   **Examples of People:**
    *   **Gwynne Shotwell (SpaceX):** As President/COO, she manages the operations and realization of engineering goals. Quote: *"You want to see failure in development... not in operation."*
    *   **Tim Cook (Apple):** Before becoming CEO, he was the SVP of Worldwide Operations, responsible for the realization/supply chain of Apple's products.
    *   **Sato Koji (Toyota):** Moved from Chief Engineer (Lexus LC 500) to CEO, emphasizing the link between engineering realization and company leadership.