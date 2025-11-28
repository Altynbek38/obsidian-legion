[[27.1 Evidence Handling and Attack Attribution]]
[[27.2 The Cyber Kill Chain]]
[[27.3 The Diamond Model of Intrusion Analysis]]
[[27.4 Incident Response]]
[[27.5 Disaster Recovery]]
[[27.6. Digital Forensics and Incident Analysis and Response Summary]]

---

### **Module 27: Digital Forensics & Incident Response - Exam Notes**

#### **1. Digital Forensics & Evidence**

*   **Digital Forensics:** The recovery and investigation of material found in digital devices.
*   **NIST Forensic Process (4 Phases):**
    1.  **Collection:** Identifying and acquiring data. *Critical: Do not alter the data.*
    2.  **Examination:** Assessing and extracting relevant info (decrypting, filtering).
    3.  **Analysis:** Drawing conclusions and correlating data.
    4.  **Reporting:** Presenting impartial findings.
*   **Evidence Volatility (Order of Collection):**
    *   **RFC 3227 Rule:** Collect from **Most Volatile** (disappears first) to **Least Volatile**.
    1.  **RAM / Cache / Registers** (Lost instantly on power off).
    2.  **Temporary Files / Swap Space**.
    3.  **Hard Disks / SSDs** (Data at rest).
    4.  **Logs / Archival Media** (Backups).
*   **Chain of Custody:** The paper trail documenting exactly **who** handled evidence, **when**, and **where**. Essential for legal admissibility.

---

#### **2. The Cyber Kill Chain (Lockheed Martin)**

A framework identifying the 7 steps of an intrusion. **Goal:** Detect and "break the chain" as early as possible.

1.  **Reconnaissance:** Researching and selecting targets (Harvesting emails, port scanning).
2.  **Weaponization:** Creating a payload (Malware + Exploit).
3.  **Delivery:** Sending the weapon (Phishing email, USB, Bad URL).
4.  **Exploitation:** Triggering the code to exploit a vulnerability.
5.  **Installation:** Installing a backdoor for persistence.
6.  **Command & Control (C2):** Establishing remote communication (Beaconing).
7.  **Actions on Objectives:** The endgame (Data theft, Encryption/Ransomware, Destruction).

---

#### **3. The Diamond Model of Intrusion Analysis**

Focuses on the relationships between four core features of an event.

*   **The 4 Corners:**
    1.  **Adversary:** The attacker.
    2.  **Capability:** The tool/malware used.
    3.  **Infrastructure:** The network path (IPs, Domains).
    4.  **Victim:** The target.
*   **Concept:** "The **Adversary** uses **Infrastructure** to deploy a **Capability** against a **Victim**."
*   **Pivoting:** Using one known point (e.g., a Victim IP) to discover others (e.g., the C2 Infrastructure).

---

#### **4. Incident Response (IR)**

*   **Standard:** **NIST 800-61r2**.
*   **The NIST IR Life Cycle:**
    1.  **Preparation:** Training, Policy, Jump Kits (Tools).
    2.  **Detection & Analysis:** Scoping the incident.
        *   **Precursor:** A sign an incident *might* happen (e.g., Log of a scanner).
        *   **Indicator:** A sign an incident *has* happened (e.g., Antivirus alert).
    3.  **Containment, Eradication, & Recovery:** Stopping the spread, removing the threat, and restoring data from clean backups.
    4.  **Post-Incident Activity:** The **"Lessons Learned"** meeting. Critical for improving future security.

---

#### **5. Disaster Recovery (DR) & Business Continuity (BC)**

*   **Disaster Recovery Plan (DRP):** Focuses on restoring **IT Systems** and data after a disaster.
*   **Business Continuity Plan (BCP):** Focuses on keeping the **Business Operations** running (people, processes) during a disaster.

**Business Impact Analysis (BIA) Metrics:**
*   **RTO (Recovery Time Objective):** The maximum acceptable **downtime** (Time).
*   **RPO (Recovery Point Objective):** The maximum acceptable **data loss** (Time/Backups).
*   **MTTR (Mean Time To Repair):** Average time to fix a failed component.
*   **MTBF (Mean Time Between Failures):** Reliability metric.

**Testing Methods:**
*   **Tabletop:** Discussion-only simulation.
*   **Functional:** Testing specific parts (e.g., backup restore).
*   **Operational:** Full-scale simulation (pulling the plug).