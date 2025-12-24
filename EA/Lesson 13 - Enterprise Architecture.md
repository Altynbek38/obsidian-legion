### **Lesson #13 - Establishing an Enterprise Architecture Practice**

This lesson focuses on the organizational side of EA. How do you set up an Architecture Department? How do you get authority (mandate)? How do you govern the process?

---

### **Part 1: Lecture Notes (Vital for Exam)**

#### **► Developing an EA Capability**
Setting up an Enterprise Architecture practice is, in itself, a business project. You should use the TOGAF ADM to build the "EA Capability".

*   **Treat "EA Team" as a Business:**
    *   **Business Architecture:** Define the team structure, governance boards, and processes.
    *   **Data Architecture:** Define the Architecture Repository and Enterprise Continuum (where you store models).
    *   **Application Architecture:** Select the tools (e.g., Archi, Sparx) needed to do the work.
    *   **Technology Architecture:** The infrastructure required to run those tools.

#### **► The Mandate (Authority)**
You cannot be an effective architect without a **Mandate**. Mandate is the official authority to make decisions and enforce them.

*   **What is a Mandate?** It means you are allowed to:
    *   Spend time building the architecture.
    *   Have your suggestions heard by management.
    *   Stop projects that violate the architecture (Compliance).
*   **How to get it?**
    *   *Wrong way:* Just having a title "Enterprise Architect".
    *   *Right way:* **"Provide winning architectures."**
*   **The "Winning" Architecture:** It is not necessarily the technically "best" or "perfect" architecture. It is the solution that **management chooses to implement**.
    *   *Key:* Win the ear of the customer + Technical Quality = Mandate Increase.

#### **► The Governance Structure**
Governance ensures that IT resources align with business goals.

*   **Frameworks:** TOGAF often works alongside:
    *   **COBIT:** For overall IT Governance and controls.
    *   **ITIL:** For IT Service Management.
*   **Organizational Structure:**
    1.  **Chief Architect:** Leads the practice.
    2.  **Architecture Board:** Group of stakeholders that approves architectures and enforces compliance.
    3.  **Domain Architects:** Specialists (Business, Data, App, Tech) who do the detailed modeling.
*   **Maturity:** Companies evolve from "Ad-hoc" (chaos) to "Optimized" (Architecture drives strategy).

---

### **Part 2: Practice Session Notes (Case Study: Bosch)**

*   **Company Profile:** Robert Bosch GmbH (Germany). Established 1886.
*   **Core Philosophy:** *"I would rather lose money than trust."* (Robert Bosch). Quality and reliability are paramount.
*   **The Transformation:** Moving from a pure hardware manufacturer (Drills, Spark plugs, Washing machines) to an **IoT (Internet of Things)** company.
*   **Strategic Focus:**
    *   **IoT is the main technology (2020-2030):** Bosch is embedding sensors and connectivity into *everything*.
    *   **Bosch IoT Suite:** A cloud platform connecting over **6.2 million** devices (sensors, cars, home appliances).
*   **Key Solutions:**
    1.  **Automated Valet Parking:** Cars park themselves (collaboration with Mercedes-Benz).
    2.  **Smart Agriculture:** Sensors for fields.
    3.  **Smart Home:** Connected appliances.
*   **Lesson for EA:** Even a 100-year-old manufacturing giant can pivot its **Business Architecture** to become a software/service provider by leveraging **Technology Architecture** (IoT).

---

### **Part 3: Assignment #06 - Answers**

*Note: This assignment covers topics from Lessons 11 & 12 (RM, Phase H, Burberry, Realisation).*

**Question 1: Why is the Requirements Management phase positioned at the center of the ADM cycle and connected to all other phases?**

Requirements Management is placed at the center because requirements are **dynamic**, not static. They drive the entire ADM process. Requirements are not just gathered once in Phase A; they are identified, refined, and updated throughout every phase (B, C, D, etc.). Placing it in the center symbolizes that changes in business requirements must immediately feed into all architectural domains to ensure the final solution solves the actual business problem.

**Question 2: What is the significance of the Architecture Change Management phase (Phase H) within the ADM? Discuss its primary objectives.**

**Phase H** is significant because it recognizes that the enterprise is a living organism. Its primary objective is to manage changes to the architecture *after* implementation.
*   **Objectives:** To ensure the architecture capability remains relevant and doesn't become obsolete.
*   **Necessity:** It determines whether a change is simple maintenance (handled by operations) or a major structural change (requiring a new ADM cycle). Without Phase H, the architecture would "rot" and misalign with business goals over time.

**Question 3: Analyze Burberry’s digital strategy in the context of enterprise architecture. What role did the implementation of an OmniChannel approach play in supporting Burberry’s success?**

Burberry used Enterprise Architecture to transform from an aging brand into a "digital media company."
*   **Strategy:** They aligned their **Business Architecture** (Brand purity, targeting millennials) with **Technology Architecture** (Digital platforms).
*   **Omnichannel Role:** This was the key enabler. By integrating data across all channels (Web, Mobile, Physical Stores), they created a seamless customer journey. For example, customers could buy items instantly from a livestream ("Runway to Reality"). This unified experience restored the brand's relevance and prestige.

**Question 4: Please describe The Realisation Iteration. What Phase of ADM is it happening in parallel? Please provide some examples of people behind some company success.**

**The Realisation Iteration** involves the actual construction and deployment of the IT solution. It happens in parallel with **Phase G (Implementation Governance)**. While developers build the system, architects govern the process to ensure compliance.
*   **Examples:**
    *   **Gwynne Shotwell (SpaceX):** As COO, she ensures the realization of engineering visions into operational success.
    *   **Sato Koji (Toyota):** Moved from Chief Engineer (Lexus) to CEO, bridging the gap between product realization and corporate strategy.
    *   **Angela Ahrendts (Apple/Burberry):** Managed the realization of retail and digital strategies.