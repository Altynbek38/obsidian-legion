
### **Lecture 1: Cyber Security Fundamentals - Key Notes**

#### **Part 1: Introduction to Information Security (InfoSec)**

*   **What is Information Security?**
    *   It is the **protection of information** and its supporting infrastructure (like computers and networks) from any accidental or intentional harm.
    *   The goal is to prevent damage to the owners or users of the information.

*   **Why is InfoSec a Problem?**
    *   Information plays an increasingly critical role in modern society (the "information society").
    *   We rely on automated systems to process massive amounts of data, which creates vulnerabilities.
    *   Damage to information can lead to significant material and financial costs (e.g., a competitor stealing a product design).

*   **Key Concepts:**
    *   InfoSec tasks are different depending on the user. An administrator of a large network has different security needs than a person with a standalone home computer.
    *   Information Security is a **broad concept**, going far beyond just preventing hacking or "unauthorized access."

---

#### **Part 2: The Core Components of Information Security (The CIA Triad)**

Information security is achieved by ensuring three core components: **Confidentiality**, **Integrity**, and **Availability**.

1.  **Availability**
    *   **Definition:** A guarantee that information and services are accessible to authorized users when they need them.
    *   **Importance:** Lack of availability can halt business operations (e.g., banking services go down, airline ticket systems fail).
    *   **Time Factor:** Information is often time-sensitive. A weather forecast for yesterday is useless.

2.  **Integrity**
    *   **Definition:** A guarantee that information is authentic and has not been altered in an unauthorized way during storage or transmission. It exists in its original, correct form.
    *   **Types:**
        *   **Static Integrity:** The data itself is unchanged (e.g., a file's content is the same).
        *   **Dynamic Integrity:** Actions on the data are performed correctly (e.g., a bank transfer moves the correct amount from the correct source to the correct destination).

3.  **Confidentiality**
    *   **Definition:** A guarantee that information is only accessible to authorized individuals. It's about secrecy and privacy.
    *   **Examples:** Passwords, employee records, production technology, state secrets.

*   **How the CIA Components are Interrelated:**
    *   A failure in one component can cause failures in the others.
    *   **Example:** An attacker steals a password (**violates Confidentiality**). They can then use it to delete data (**violates Availability**) or change data (**violates Integrity**).

---

#### **Part 3: The System & Levels of Information Security**

*   **Three Levels of Information Security:** A comprehensive security system is built on three levels:
    1.  **Legislative-Legal Level:** Laws and regulations that define the rules for information protection.
    2.  **Administrative (Organizational) Level:** Policies, procedures, and controls implemented by an organization (e.g., employee security training, access control policies).
    3.  **Software and Hardware Level (Technical Level):** The technology used to protect systems (firewalls, antivirus, encryption).

*   **Main Tasks of Information Security (Broadly):**
    *   Protecting state secrets and confidential government information.
    *   Protecting citizens' rights to own and manage their information.
    *   Protecting citizens' rights to privacy (correspondence, personal data).
    *   Protecting technical systems from accidental or intentional harm.

---

#### **Part 4: Information Security Legislation in Kazakhstan (Summary)**

*   **Core Idea:** Information security is considered an integral part of **National Security**.
*   **Main Goals of the Law:**
    *   Prevent information dependence on other countries.
    *   Protect against information blockades or foreign influence.
    *   Ensure stable operation of communication networks, especially during emergencies.
    *   Protect state secrets and prevent leaks.
*   **State Secrets vs. Official Secrets:**
    *   **State Secret:** Information (military, economic, political) whose disclosure could damage the **national security** of Kazakhstan.
    *   **Official Secret:** Information whose disclosure could damage the interests of **state bodies or organizations**.

---

#### **Part 5: Security in Computing Networks**

*   **Key Security Services (The Goals):**
    1.  **Authentication:** Verifying the identity of a user or system (proving you are who you say you are).
    2.  **Access Control:** Preventing unauthorized use of resources (ensuring users can only access what they are allowed to).
    3.  **Data Confidentiality:** Protecting data from being read by unauthorized parties.
    4.  **Data Integrity:** Ensuring data is not altered during transmission.
    5.  **Non-repudiation:** Providing proof that an action was taken by a specific user, so they cannot deny it later (e.g., proof of sending/receiving an email).

*   **Key Security Mechanisms (The Tools):**
    *   **Encryption:** Scrambling data so it's unreadable without the proper key. (Used for Confidentiality).
    *   **Digital Signature:** An electronic signature that proves the identity of the sender and the integrity of the data. (Used for Authentication, Integrity, Non-repudiation).
    *   **Access Control Mechanisms:** Lists and rules that define who can access what.
    *   **Traffic Padding:** Adding extra data to a network flow to confuse traffic analysis. (Used for Confidentiality).

*   **Security Administration:**
    *   The management of all security services and mechanisms.
    *   This includes managing cryptographic keys, setting access control lists, monitoring for events, and keeping the security policy up to date.

***
**To Prepare for Your Midterm:**
1.  Memorize the definitions of **Information Security**, **Confidentiality**, **Integrity**, and **Availability**.
2.  Understand the **CIA Triad** and be ready to give an example of how they are interrelated.
3.  Know the **three levels** of InfoSec (Legal, Administrative, Technical).
4.  Be able to list the main **Security Services** (Authentication, Access Control, etc.).