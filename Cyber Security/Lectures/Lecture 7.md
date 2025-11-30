
### **Lecture 7: Administering a Secure Network - Key Notes**

#### **Part 1: The Core Functions of Network Administration (The FCAPS Model)**

Network administration is the ongoing process of keeping a network reliable, efficient, and secure. According to international standards, this is broken down into five core functions, often remembered by the acronym **FCAPS**.

1.  **Failure Management:**
    *   **Goal:** To detect, isolate, and correct network faults.
    *   **In Practice:** This is **troubleshooting**. When something breaks (e.g., a server is offline, a user can't connect to the Wi-Fi), the administrator finds the cause and fixes it.

2.  **Configuration Management:**
    *   **Goal:** To manage and document the settings of all network devices.
    *   **In Practice:** Setting up new devices, assigning IP addresses, configuring routing protocols, and keeping detailed records of every device's configuration.

3.  **Accounting Management (or Administration):**
    *   **Goal:** To track the usage of network resources.
    *   **In Practice:** Monitoring which users or applications are using the most bandwidth. This helps with billing, capacity planning, and enforcing usage policies.

4.  **Performance Management:**
    *   **Goal:** To ensure the network is running efficiently and to plan for future needs.
    *   **In Practice:** Monitoring network speed, identifying bottlenecks, and collecting long-term data to decide when it's time to upgrade hardware or increase bandwidth.

5.  **Security Management:**
    *   **Goal:** To protect the network and its data from unauthorized access and threats. This is the primary focus of this course.
    *   **In Practice:** Controlling access with user accounts and passwords, implementing firewalls, ensuring data integrity, and responding to security incidents.

---

#### **Part 2: A Practical 5-Step Guide to Securing a Network**

This is a continuous, iterative process, not a one-time setup.

*   **Step 1: Know Your Network (Asset Management)**
    *   **Principle:** You can't protect what you don't know you have.
    *   **Action:** Create and maintain a complete, up-to-date **inventory** of every single device on your network (servers, laptops, IoT devices, virtual machines, etc.).

*   **Step 2: Find and Fix Weaknesses (Vulnerability Management)**
    *   **Principle:** Proactively find and close security holes before attackers can exploit them.
    *   **Action:** Regularly perform **vulnerability scans** and **patch management**. This means keeping all operating systems and applications updated with the latest security patches.

*   **Step 3: Strengthen Defenses (Layered Security / Defense-in-Depth)**
    *   **Principle:** Use multiple layers of security controls, so if one fails, others are still in place.
    *   **Key Actions:**
        *   **Firewalls:** Use them everywhere; don't disable them.
        *   **Network Segmentation:** Divide the network into smaller, isolated zones. A breach in one zone can't easily spread to others.
        *   **Principle of Least Privilege:** Give users and systems only the minimum level of access they need to do their job.
        *   **VPNs:** Use them to encrypt and secure remote access.
        *   **Centralized Logging:** Collect all logs in one place for easy monitoring and analysis.

*   **Step 4: Automate Your Response**
    *   **Principle:** Manual security is too slow. Automate repetitive tasks to improve efficiency and speed of response.
    *   **Action:** Use scripts and security tools to automatically block malicious IP addresses, terminate suspicious connections, and alert administrators to potential threats.

*   **Step 5: Continuously Monitor, Audit, and Iterate**
    *   **Principle:** Security is a never-ending process.
    *   **Action:**
        *   **Continuous Monitoring:** Actively watch network traffic and device logs for signs of attack.
        *   **Regular Audits:** Periodically check device configurations and access lists to make sure they are still secure.
        *   **Penetration Testing:** Hire ethical hackers to perform simulated attacks to find weaknesses you might have missed.

---

#### **Part 3: Network Administrator vs. Network Engineer**

These two roles are often confused but have distinct responsibilities.

*   **Network Administrator (The "How" - Day-to-Day Operations)**
    *   **Focus:** **Maintaining** the existing network.
    *   **Tasks:** Troubleshooting user issues, monitoring network performance, applying patches, managing user accounts, and ensuring the network is secure and operational *in real-time*. They are the mechanics who keep the car running.

*   **Network Engineer (The "What" and "Why" - Big Picture Strategy)**
    *   **Focus:** **Designing and building** the network.
    *   **Tasks:** Designing the network architecture, planning for future growth, researching and implementing new technologies, and making strategic decisions about the network's lifecycle. They are the architects who design the building.

***
**Key Takeaway for Your Midterm:**
1.  Remember the **FCAPS** model for the five core functions of network administration.
2.  Securing a network is an **iterative 5-step process**: Inventory -> Vulnerability Management -> Layered Defense -> Automation -> Continuous Monitoring.
3.  The **Administrator maintains** the network day-to-day, while the **Engineer designs and builds** it.