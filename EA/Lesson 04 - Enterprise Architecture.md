
### **Lesson #04 - Building Blocks, Visualization & Capability Planning**

This lesson goes deeper into the "how-to" of TOGAF, explaining the Architecture Development Method (ADM), how to visualize architecture for different people, and how to plan based on business capabilities.

---

### **Part 1: Lecture Notes (Vital for Midterm)**

#### **► Creating & Using Building Blocks: The TOGAF ADM**

The **Architecture Development Method (ADM)** is the heart of TOGAF. It is the step-by-step process for creating and managing your Enterprise Architecture. Think of it as the instruction manual for building your enterprise's future.

*   **The ADM Cycle:**
    *   **Preliminary Phase:** This is the setup phase. Before you start building, you prepare your tools and team. This includes setting up your architecture repository, defining principles, and establishing the architecture team's capabilities.
    *   **Phase A: Architecture Vision:** Defines the goal. This phase gets the business requirements, defines the scope of the project, and creates a high-level vision of the "current" vs. "future" architecture to secure stakeholder approval.
    *   **Phase B: Business Architecture:** Defines *what* the business needs to do. It focuses on business processes, functions, and capabilities, without worrying about technology yet.
    *   **Phase C: Information Systems Architecture:** Defines the data and applications. This phase looks at what data the business needs (**Data Architecture**) and what application systems will manage that data (**Application Architecture**).
    *   **Phase D: Technology Architecture:** Defines the underlying hardware and software. This is where you design the technology infrastructure (servers, networks, platforms) needed to run the applications.
    *   **Phase E: Opportunities and Solutions:** Figures out how to implement the plan. This phase consolidates the work from the previous phases and identifies the specific solutions and projects needed to achieve the vision.
    *   **Phase F: Migration Planning:** Creates the roadmap. This phase lays out a detailed plan for migrating from the current architecture to the future architecture, sequencing projects over time.
    *   **Phase G: Implementation Governance:** Makes sure the plan is followed correctly during implementation.
    *   **Phase H: Architecture Change Management:** Manages changes after the project is done. It sets up a process for handling any new architectural requirements or changes in the future.
    *   **Requirements Management (The Center):** This is not a phase but a continuous process that happens throughout the entire cycle. It involves identifying, storing, and managing all stakeholder requirements to ensure the final architecture meets their needs.

#### **► Visualizing Building Blocks: Views and Viewpoints**

An architecture is complex, and different people need to see different parts of it. TOGAF uses **Views** and **Viewpoints** to solve this.

*   **Stakeholder & Concern:** It all starts with a **stakeholder** (e.g., a CEO, an IT manager, a developer) who has a **concern** (a question or interest, like "What is the cost?" or "Which servers will be used?").
*   **Viewpoint:** A Viewpoint is the **template** or **perspective** used to address a stakeholder's concern. It defines what should be included in a diagram or document and how it should be presented.
    *   *Analogy:* Think of a viewpoint as choosing *where to stand* on a mountain to take a photo. You could choose a viewpoint from the top, the side, or the bottom. It is the "instruction set" for what kind of picture to take.
*   **View:** A View is the **actual result**—the diagram, model, or document you create using a specific viewpoint. It is what the stakeholder actually sees.
    *   *Analogy:* The view is the *actual photograph* you take from your chosen viewpoint on the mountain.

*   **The Key Difference:** A **Viewpoint** is the *definition* of how to look at something. A **View** is *what you see* after looking at it from that perspective.

#### **► Capability-Based Planning**

This is a modern, strategic way to plan that connects architecture directly to business value.

*   **Definition:** Instead of focusing on individual projects or technologies, Capability-Based Planning focuses on delivering strategic **business capabilities**.
*   **What is a Business Capability?** It's the ability for a company to do something to achieve an outcome. A true capability requires a combination of three things:
    1.  **People** (with the right skills and training).
    2.  **Process** (well-defined business processes).
    3.  **Technology** (the tools and systems to support the work).
*   **Why it's important:** You can't just deploy new technology and expect results. Without competent people and effective processes, the technology is useless.
*   **Examples of Building Capabilities:**
    *   **Apple:** Started with a "smart phone" capability. It then built new capabilities in services, content, and health, allowing it to enter new markets with Apple TV+ and Fitness+.
    *   **Microsoft:** Was an "OS developer." It built a world-class "cloud solution" capability and now its main profit comes from Azure.

---

### **Part 2: Practice Session Notes (Case Study: Toyota)**

*   **Toyota's Global Vision:** The core of Toyota's strategy is to transform from a traditional **"automobile company"** into a **"mobility company."** As former CEO Akio Toyoda said, the goal is to "lead the future mobility society, enriching lives around the world with the safest and most responsible ways of moving people."
*   **The CASE Strategy:** This vision is being executed through four key technology pillars:
    *   **C**onnected
    *   **A**utonomous
    *   **S**hared
    *   **E**lectric
*   **Toyota Connected:** This is the company division responsible for the "Connected" part of the strategy. Its goal is to use data and technology to create services that link people, vehicles, and society. By mastering predictive intelligence and processing **truly big data** (over 7.2 million data points per car per day), Toyota aims to create a driving experience that is safer, more convenient, and more fun.

---

### **Part 3: Assignment #02 - Answers**

Here are clear and concise answers to the assignment questions based on the provided lectures.

**Question 1: Please describe Toyota's Global Vision.**

Toyota's Global Vision is to transition from being an automobile company to a **"mobility company."** This means their focus is no longer just on manufacturing and selling cars, but on "leading the future mobility society" by providing the safest, most responsible, and innovative ways of moving people. This vision is built on the **CASE** strategy, which stands for **C**onnected, **A**utonomous, **S**hared, and **E**lectric technologies.

**Question 2: What is the difference between View and Viewpoint?**

A **Viewpoint** defines the perspective from which an architecture is viewed. It acts as a template or set of instructions, tailored to address the concerns of a specific stakeholder (like a CEO or an engineer). A **View** is the actual result or output created from that viewpoint—it is the specific diagram, document, or model that the stakeholder sees. In short, the viewpoint is the *template*, and the view is the *finished product*.

**Question 3: What is Enterprise Continuum?**

The **Enterprise Continuum** is a core concept in the TOGAF framework that acts as a "virtual repository" for classifying all of an organization's architecture and solution assets. It organizes reusable components (like LEGO blocks) on a spectrum from generic (e.g., industry standards) to specific (e.g., unique to the company). This allows architects to efficiently find, reuse, and adapt existing assets to build new solutions, saving time and ensuring consistency.

**Question 4: Please describe Digital Customer Experience with an example of BMW.**

A **Digital Customer Experience (DCE)** is the sum of all digital interactions a customer has with a brand. BMW provides an excellent example with its **CARASSO (Car as a Sensor)** connected-car platform. In this system:
1.  BMW vehicles use their sensors to collect real-time road data.
2.  This data is sent to the AWS cloud for processing.
3.  An updated, highly accurate "learning map" is generated and sent back to the car.

This creates a superior DCE by directly providing the driver with tangible benefits like more accurate speed limits, improved road safety information, and better-optimized routes, fundamentally enhancing their driving experience through technology.