### **Lesson #09 - Information Systems & Technology Architecture (Phases C & D)**

This lesson covers the technical side of the TOGAF ADM. After defining the Business Architecture (Phase B), we move to the **Information Systems Architecture (Phase C)** and **Technology Architecture (Phase D)** to build the systems that support the business.

---

### **Part 1: Lecture Notes (Vital for Exam)**

#### **► Phase C: Information Systems Architecture (ISA)**
Phase C is divided into two distinct but related architectures. It describes **software and data**.

1.  **Data Architecture:**
    *   **Goal:** Define how data is stored, managed, and used.
    *   **Key Deliverables:** Conceptual, Logical, and Physical Data Models.
    *   **Why it matters:** Data must be consistent across the enterprise (e.g., "Customer" data in Sales must match "Customer" data in Shipping).
2.  **Application Architecture:**
    *   **Goal:** Define the software applications needed to process the data and support the business.
    *   **Not the same as "System Design":** It defines *logical* groups of capabilities (e.g., "We need a CRM"), not the specific code.
    *   **Key Examples:**
        *   **ERP (Enterprise Resource Planning):** SAP, Oracle, Microsoft Dynamics. Core internal operations.
        *   **CRM (Customer Relationship Management):** Salesforce, HubSpot. Managing customer interactions.
        *   **SCM (Supply Chain Management):** Logistics and inventory.
        *   **BI (Business Intelligence):** Tableau, PowerBI. Analytics and reporting.

*   **Netflix Case (AWS):** Netflix demonstrates a strong Phase C. They use a microservices architecture on AWS to handle massive data streams (events, operations) and content distribution (CDN) to ensure seamless playback.

#### **► Phase D: Technology Architecture (TA)**
Phase D describes the **infrastructure** needed to run the applications and data defined in Phase C.

*   **Scope:** Hardware, software platforms, networks, communications, and middleware.
*   **The Pyramid:** Technology Architecture is the **base** that supports Application, Data, and Business Architectures.
*   **Emerging Technologies:** A major driver for Phase D is adopting new tech to transform business.
    *   **Gartner Trends (2025-2026):**
        *   **AI:** Agentic AI, AI Governance, Human-Centered AI.
        *   **Computing:** Neuromorphic computing, Energy-Efficient computing.
        *   **Immersion:** Metaverse, Spatial Computing.
*   **Deliverables:** Technology Portfolio Catalog, Hardware/Software specifications, Network diagrams.

#### **► The Architecture Roadmap**
After defining the Target Architectures (B, C, D), you perform a **Gap Analysis** (What do we have vs. What do we need?) and create a Roadmap to transition from Baseline (AS-IS) to Target (TO-BE).

---

### **Part 2: Practice Session Notes (Case Study: IKEA)**

*   **IKEA's Strategy:** Historically known for cost-efficiency ("flatpack furniture"). Their new strategy focuses on **Digital Transformation** and **Customer Experience**.
*   **Campaign: "Where Life Happens":**
    *   IKEA renamed products to match common Google searches about relationship problems (e.g., a daybed named "My Partner Snores").
    *   *Significance:* It aligns the **Product Model** directly with **Customer Needs/Emotions**.
*   **Innovation: IKEA Place App:**
    *   **Problem:** Customers hesitate to buy because they don't know if furniture will fit or look good in their home.
    *   **Solution:** An Augmented Reality (AR) app built on Apple's **ARKit**.
    *   **Technology (Phase D):** Uses LiDAR (on iPhone 12 Pro+) and AR tech.
    *   **Value (Business Arch):** "Try before you buy." It reduces product returns, increases sales confidence, and creates a superior User Experience (UX).
    *   *Lesson:* Technology (AR) was used specifically to solve a Business Problem (visualization).

---

### **Part 3: Assignment #04 - Answers**

*Note: This assignment covers concepts from Lesson 08 (Business Architecture) and links them to Lesson 09.*

**Question 1: Describe the concept of a business model in organization and its significance in enterprise architecture. How does it connect with Business Architecture?**

A **Business Model** defines how an organization creates, delivers, and captures value (e.g., using the Business Model Canvas). In Enterprise Architecture, it is the strategic starting point. It connects with **Business Architecture (Phase B)** because Phase B translates the high-level business model into concrete operational structures (capabilities, value streams, organization maps). Without a clear Business Model, the IT systems (Phases C & D) will be misaligned with the company's goals.

**Question 2: Why is business architecture (Phase B) important in TOGAF ADM? Please describe it using NVIDIA case.**

**Business Architecture (Phase B)** is critical because it ensures technology serves the business strategy, not the other way around.
*   **NVIDIA Case:** NVIDIA transitioned its Business Architecture from being a "Gaming Graphics Company" to an "AI & Data Center Computing Company." They identified a new market need (SIMD computing for AI). If they had not updated their Phase B (Vision & Strategy), they would not have prioritized the Phase C & D changes needed to build AI-specific chips (H100s) and software (CUDA), and would have missed the AI boom.

**Question 3: How is Starbucks using Machine Learning to learn customer behaviours? How does Starbucks improve its User Experience?**

Starbucks uses its "Deep Brew" AI engine to analyze data gathered from its mobile app and loyalty program.
*   **Learning Behavior:** The system tracks order history, location, weather, and time of day to understand individual customer preferences.
*   **Improving User Experience:** It offers hyper-personalized recommendations (e.g., suggesting a cold brew on a hot afternoon). This creates a seamless, "frictionless" digital experience that mirrors the personalized service of a barista, increasing customer retention and average spend.

**Question 4: Provide an example of how an EA roadmap can be used to prioritize projects, manage risks, and ensure alignment with business goals. (Toyota case)**

An **EA Roadmap** sequences projects to move a company from its current state to its future state.
*   **Toyota Case:** Their goal is to shift from "Automobile Manufacturer" to "Mobility Service Company."
*   **Alignment & Prioritization:** The roadmap prioritizes projects related to the **CASE** strategy (Connected, Autonomous, Shared, Electric). For example, developing the **Mobility Services Platform (MSPF)** is prioritized over traditional engine updates.
*   **Risk Management:** The roadmap manages the risk of obsolescence by gradually phasing in EV/Hydrogen technologies while phasing out combustion engines, ensuring the company remains relevant in a green future.