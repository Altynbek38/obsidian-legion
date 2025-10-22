
### **Lesson #07 - Views, Viewpoints, ArchiMate, and the Starbucks Case Study**

This lesson focuses on how architects communicate their plans to different people, the specific language used for modeling, and how a non-tech company like Starbucks built a world-class digital platform.

---

### **Part 1: Lecture Notes (Vital for Midterm)**

#### **► Vision: Business Vision vs. Architecture Vision**

It's crucial to understand the difference between two types of vision:

*   **Business Vision:** This is the high-level, forward-looking goal of the company. It's created by the CEO and focuses on **what** the company wants to achieve and how it will serve its customers. *(Example: Toyota's vision to become a mobility company).*
*   **Architecture Vision (TOGAF Phase A):** This is the vision created by the Enterprise Architect. Its purpose is to define **how** to construct the enterprise (the combination of people, processes, and technology) to support and enable the Business Vision.

The main output of Phase A is the **Architecture Vision document**, which leads to a **Statement of Architecture Work** that defines the time, cost, and effort for the project.

#### **► Communicating Architecture: Views, Viewpoints, and Concerns**

An architecture must be communicated effectively to many different people. TOGAF provides a formal system for this:

1.  **Stakeholder:** Anyone in the organization who has an interest in the outcome of the architecture (e.g., CEO, project manager, developer).
2.  **Concern:** The key interests or questions a stakeholder has. It's an area of interest, not a formal requirement. *(Examples: "Will this be secure?" "How will this improve sales?" "What is the performance impact?")*. Concerns are the starting point and are later broken down into formal, SMART requirements.
3.  **Viewpoint:** The perspective or template used to address a stakeholder's concerns. It defines *how* to construct a view, including what information and modeling techniques to use. Viewpoints are generic and reusable.
4.  **View:** The actual representation (diagram, model, or document) of the architecture created from a specific viewpoint. It is *what the stakeholder sees* and is always specific to the architecture being designed.

*   **Simple Analogy:**
    *   **A View is what you see.**
    *   **A Viewpoint is where you are looking from.**

#### **► ArchiMate® EA Modeling Language**

If TOGAF is the "how-to" guide for creating an architecture, ArchiMate is the "pen and paper" used to draw it.

*   **What is it?** ArchiMate is an open and independent graphical language for modeling Enterprise Architectures. It is a technical standard from The Open Group, just like TOGAF.
*   **Purpose:** It provides a common, unambiguous set of symbols and rules to describe, analyze, and visualize every part of an enterprise.
*   **Key Difference:** Unlike other modeling languages like UML (for software) or BPMN (for business processes), ArchiMate is designed to model the *entire enterprise* and show the relationships between business, application, and technology layers.

#### **► The Architecture Development (AD) Iteration**

This is the most common iterative cycle within the TOGAF ADM, focusing on Phases B, C, and D.

*   **The Goal:** To develop the three core architecture layers:
    1.  **Business Architecture**
    2.  **Information Systems Architecture (Data & Application)**
    3.  **Technology Architecture**
*   **Five Key Things to Address in Each Iteration:**
    1.  **Views, Viewpoints & Stakeholders:** Who are we talking to?
    2.  **Reference Models:** What existing models can we use?
    3.  **AS-IS Environment:** Where are we now?
    4.  **TO-BE Environment:** Where are we going?
    5.  **GAP Analysis:** What is the difference between AS-IS and TO-BE?

---

### **Part 2: Practice Session Notes (Case Study: Starbucks' Digital Strategy)**

Starbucks is a coffee company, but its success is now driven by its world-class technology platform. This case study shows how they built a digital architecture to enhance the customer experience and drive loyalty.

*   **The Challenge:** Traditional retailers face declining sales as customers move online. To stay competitive, Starbucks needed to create a unique and convenient digital experience that would keep customers coming back.

*   **The Solution: The "Digital Flywheel" Program**
    *   This is the core of Starbucks' digital strategy, built on a unified commerce system and cloud architecture. The flywheel is designed to create a self-reinforcing cycle of customer engagement.
    *   **The Four Pillars of the Flywheel:**
        1.  **Rewards:** A compelling loyalty program (Starbucks® Rewards) that gives customers a reason to engage.
        2.  **Payment:** Easy and seamless ways to pay, primarily through the mobile app's digital wallet.
        3.  **Ordering:** The "Mobile Order & Pay" feature, which is the fastest and most convenient way to order.
        4.  **Personalization:** Using data and AI to tailor offers, communications, and recommendations to individual customers.

*   **The Power of Personalization:**
    *   Starbucks' Personalization Engine is the key to the flywheel's success. It evolved from sending 30 handcrafted email variants per week to sending **400,000 hyper-personalized variants per week**.
    *   The system uses **Artificial Intelligence (AI)** to analyze customer data (order history, location, time of day, weather) to make real-time, 1:1 personalized offers and recommendations.

*   **The Architectural Philosophy:** As stated by the CTO, "Tech has to amplify that human connection, not get in the way of it." The goal was not to build shiny tech, but to build tech that enhances the unique Starbucks experience. The result is a best-in-class User Experience (UX) based on AI.