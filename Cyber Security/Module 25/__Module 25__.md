[[25.1 Network and Server Profiling]]
[[25.2 Common Vulnerability Scoring System (CVSS)]]
[[25.3 Secure Device Management]]
[[25.4 Endpoint Vulnerability Assessment Summary]]

---

### **Module 25: Endpoint Vulnerability Assessment - Exam Notes**

#### **1. Profiling & Baselining**

*   **Baselining:** The process of establishing a statistical reference point for "normal" behavior. Deviations from this baseline indicate a potential anomaly or attack.
*   **Network Profiling Elements:**
    *   **Session Duration:** Time between start and end of a flow.
    *   **Total Throughput:** Amount of data transferred.
    *   **Ports Used:** TCP/UDP ports allowed.
    *   **Critical Asset Address Space:** IP addresses of high-value targets.
*   **Server Profiling:** Establishing the accepted state for a specific server (e.g., Allowed listening ports, logged-in users, running processes/software).

**Anomaly Detection Methods:**
*   **Big Data Analytics:** Using statistical/machine learning on large datasets.
*   **Rule-Based:** Analyzing traffic based on pre-defined signatures (like Snort rules).

---

#### **2. CVSS (Common Vulnerability Scoring System)**

A vendor-neutral framework to rate the severity of vulnerabilities on a scale of **0 to 10**.

**The Three Metric Groups:**
1.  **Base Group:** Qualities that are **constant** over time and across environments. (The core score).
2.  **Temporal Group:** Qualities that change over time (e.g., is there a patch available yet? Is exploit code mature?).
3.  **Environmental Group:** Qualities specific to **your** organization's environment.

**Base Metrics (The Vector String):**
*   **Exploitability:**
    *   **Attack Vector (AV):** Physical vs. Remote (Network is worst).
    *   **Attack Complexity (AC):** How hard is it to hack?
    *   **Privileges Required (PR):** Do you need to be Admin or Guest?
    *   **User Interaction (UI):** Does the victim need to click a link?
    *   **Scope (S):** Does the attack jump to other components? (Change of Authority).
*   **Impact (CIA Triad):** Confidentiality, Integrity, Availability.

**Severity Scale:**
*   **Low:** 0.1 – 3.9
*   **Medium:** 4.0 – 6.9
*   **High:** 7.0 – 8.9
*   **Critical:** 9.0 – 10.0
> **Rule of Thumb:** Any vulnerability score **> 3.9** should be addressed.

---

#### **3. Risk Management Strategies**

The process of identifying and responding to risks.
**Formula:** `Risk = Threat x Vulnerability x Asset Value`

**The 4 Risk Responses:**

| Response      | Action                 | Example                                                       |
| :------------ | :--------------------- | :------------------------------------------------------------ |
| **Avoidance** | **Stop** the activity. | Shutting down a risky server; stopping a specific service.    |
| **Reduction** | **Mitigate** the risk. | Installing firewalls, patching software, using encryption.    |
| **Sharing**   | **Transfer** the risk. | Buying cybersecurity **insurance** or outsourcing.            |
| **Retention** | **Accept** the risk.   | Doing nothing because the cost of the fix > cost of the loss. |

---

#### **4. Device & Vulnerability Management**

**Vulnerability Management Cycle:**
`Discover -> Prioritize -> Assess -> Report -> Remediate -> Verify`

**Management Types:**
*   **Asset Management:** You cannot protect what you don't know you have. Tracks physical and logical assets.
*   **MDM (Mobile Device Management):** Securing devices that leave the premises (BYOD). Features: Remote wipe, encryption, sandboxing.
*   **Configuration Management:** Using "Golden Images" or baselines to ensure all systems are configured securely and consistently.

**Patch Management Techniques:**
*   **Agent-Based:** Software installed on the host pulls updates (Good for mobile/roaming).
*   **Agentless:** Server scans the network and pushes updates (Good for LAN).
*   **Passive Monitoring:** Watching traffic to identify outdated software versions.