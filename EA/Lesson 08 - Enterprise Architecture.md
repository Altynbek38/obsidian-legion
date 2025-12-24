### **Lesson #08 - Business Architecture (Phase B) & Business Scenarios**

This lesson focuses on **Phase B** of the TOGAF ADM, explaining why Business Architecture must come *before* technology, and introduces techniques like Business Scenarios to identify requirements.

---

### **Part 1: Lecture Notes (Vital for Exam)**

#### **► Phase B: Business Architecture (The Foundation)**
**Business Architecture** is the first architecture activity that must be undertaken (after the Vision). It defines *how* the enterprise needs to operate to achieve its goals.

*   **Why it comes first:** You cannot build the right IT systems (Data, Application, Technology) if you don't understand the business organization and processes first.
    *   *Hierarchy:* **Business Architecture** sits on top of Data, Application, and Technology.
    *   *Steve Jobs Rule:* "You’ve got to start with the **customer experience** and work backwards to the **technology**. You can’t start with the technology and try to figure out where you’re going to sell it."

*   **Objectives of Phase B:**
    1.  Describe the **Baseline** (AS-IS) Business Architecture.
    2.  Develop the **Target** (TO-BE) Business Architecture.
    3.  Perform **Gap Analysis** (Difference between Baseline and Target).
    4.  Create the **Roadmap** components to close those gaps.

#### **► Business Scenario Technique**
This is a method used to identify and understand business requirements. It helps derive the architecture directly from high-level business needs.

*   **SMART Criteria:** A good business scenario must be **SMART**:
    *   **S**pecific (defines what needs to be done).
    *   **M**easurable (clear metrics for success).
    *   **A**ctionable (segments the problem and provides a basis for solution).
    *   **R**ealistic (solvable within constraints).
    *   **T**ime-bound (clear deadline/expiration).

#### **► Modeling Concepts**
*   **ArchiMate:** An open, independent modeling language for Enterprise Architecture. It is different from UML (software) or BPMN (process) because it covers the *entire* enterprise scope unambiguously.
*   **View vs. Viewpoint (Review):**
    *   **View:** What you see (the diagram itself).
    *   **Viewpoint:** Where you look from (the perspective/template defining what to look for).
*   **Business Model:** Describes the rationale of how an organization creates, delivers, and captures value. It usually includes:
    *   **Market Model:** Customers and Segments.
    *   **Product/Service Model:** Value Proposition.
    *   **Operating Model:** Capabilities, Processes, and Resources.

---

### **Part 2: Practice Session Notes (Case Study: Walmart)**

*   **Walmart's Core Philosophy:** Sam Walton (Founder) said: *"We got big by replacing inventory with information."* This summarizes their EA strategy—using data to manage physical goods efficiently.

*   **Key Technological Capabilities:**
    1.  **Intelligent Optimization (Big Data):**
        *   Walmart processes **2.5 petabytes** of data hourly.
        *   Uses **predictive analytics** to optimize inventory (knowing what to stock before people buy it), saving transportation and handling costs.
    2.  **End-to-End Transparency (RFID):**
        *   Uses **RFID tags** (Radio Frequency Identification) to track pallets and merchandise across the supply chain.
        *   Uses **Smart Tags** on shelves so employees know exactly when to restock items.
    3.  **Partnerships:**
        *   Partnered with **Google** (Google Assistant) to enable voice shopping, competing with Amazon's Alexa.

---

### **Part 3: Assignment #04 - Answers**

Here are the ideas you need to answer the assignment questions based on the lecture logic.

**Question 1: Describe the concept of a business model in organization and its significance in enterprise architecture. How does it connect with Business Architecture?**

A **Business Model** describes the rationale of how an organization creates, delivers, and captures value. In Enterprise Architecture, it serves as the "blueprint" for the business strategy. It connects with **Business Architecture (Phase B)** because Phase B translates this high-level model into specific organizational structures, value streams, and capabilities. Without a clear Business Model, the architecture would have no direction, leading to misaligned IT systems.

**Question 2: Why is business architecture (Phase B) important in TOGAF ADM? Please describe it using NVIDIA case.**

**Business Architecture (Phase B)** is crucial because it ensures technology supports the strategic direction of the company. It prevents "building technology for technology's sake."
*   **NVIDIA Case:** Initially, NVIDIA was just a graphics card company (leader in gaming). However, their Business Architecture shifted to focus on **AI and Datacenters**. By recognizing the market shift towards SIMD (Single Instruction, Multiple Data) processing for AI, they adjusted their business goals. If they had not updated their Business Architecture to target the AI market, they would have remained a niche gaming company instead of becoming a market leader surpassing Intel.

**Question 3: How is Starbucks using Machine Learning to learn customer behaviours? How does Starbucks improve its User Experience?**

*(Note: Based on standard EA case studies referenced in this course context)*
Starbucks uses an AI engine (often called **Deep Brew**) to analyze data from their mobile app and loyalty program.
*   **Learning Behavior:** It tracks purchase history, time of day, weather, and location to understand individual preferences.
*   **Improving User Experience:** It provides hyper-personalized recommendations on the app (e.g., suggesting a cold drink on a hot day or a usual order). This reduces friction for the customer and increases sales, embodying the principle of "starting with customer experience."

**Question 4: Provide an example of how an EA roadmap can be used to prioritize projects, manage risks, and ensure alignment with business goals (Toyota case).**

An **EA Roadmap** lays out the sequence of projects needed to move from the Baseline to the Target Architecture.
*   **Toyota Example:** Toyota's goal is to transition from an "Automobile Company" to a "Mobility Company" (Vision).
*   **Prioritization:** The roadmap prioritizes projects related to **CASE** (Connected, Autonomous, Shared, Electric) over traditional manufacturing improvements.
*   **Alignment:** It ensures every IT project (like developing hydrogen fuel cells or software operating systems for cars) directly supports the strategic goal of "Mobility for All," ensuring resources aren't wasted on projects that don't fit the future vision.