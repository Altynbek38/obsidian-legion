[[23.1 Security Assessments]]
[[23.2 Network Security Testing Techniques]]
[[23.3 Network Security Testing Tools]]
[[23.4 Penetration Testing]]
[[23.5 Network Security Testing Summary]]

---

### **Module 23: Endpoint Vulnerability Assessment - Exam Notes**

#### **1. Vulnerability Scanning**

*   **Vulnerability Scanner:** Automates the auditing of systems to find weaknesses (e.g., open ports, missing patches, default passwords).
*   **Scan Types:**
    *   **Intrusive:** Tries to **exploit** the vulnerability. *Risk:* Can crash the system.
    *   **Non-Intrusive:** Reports the issue without exploiting it. Safer.
    *   **Credentialed:** Uses a valid login. Gives deeper info, fewer errors.
    *   **Non-Credentialed:** Scans from the outside (Hacker's perspective).
*   **Accuracy:**
    *   **False Positive:** Reporting a bug that doesn't exist (Noise).
    *   **False Negative:** Failing to report a real bug (Dangerous).

---

#### **2. Security Automation: SIEM vs. SOAR**

*   **SIEM (Security Information and Event Management):**
    *   **Focus:** **Logs & Analysis.**
    *   **Functions:** Aggregation (combining logs), Correlation (linking events), and Forensic Analysis.
    *   *Goal:* "Find the needle in the haystack."
*   **SOAR (Security Orchestration, Automation, and Response):**
    *   **Focus:** **Action & Response.**
    *   **Functions:** Automated incident response without human intervention (e.g., automatically blocking an IP on the firewall).

---

#### **3. Critical Network Tools (The Toolbox)**

| Tool | Function |
| :--- | :--- |
| **Nmap / Zenmap** | **Network Mapper.** Port scanning, OS fingerprinting, Service discovery. (Zenmap is the GUI). |
| **Nessus** | **Vulnerability Scanner.** Checks for patches, misconfigurations, and compliance. |
| **Metasploit** | **Penetration Testing.** A framework for developing and executing exploit code. |
| **SuperScan** | **Port Scanner.** Windows-only tool for scanning TCP/UDP ports. |
| **Tripwire** | **Integrity Checker.** Monitors file changes and configuration compliance. |
| **Wireshark** | **Packet Sniffer.** Captures and analyzes network traffic (Promiscuous mode). |

---

#### **4. Penetration Testing (Ethical Hacking)**

*   **Penetration Test:** **Simulates** a cyberattack to measure the security posture. Unlike a vuln scan, it *exploits* weaknesses.
*   **The 4 Phases:**
    1.  **Planning:** Rules of Engagement (ROE).
    2.  **Discovery:** Reconnaissance (gathering intel).
    3.  **Attack:** Exploiting and gaining access/persistence.
    4.  **Reporting:** Documenting findings for the client.

**Testing Perspectives ( The "Boxes"):**

| Type | Knowledge Level | Simulates |
| :--- | :--- | :--- |
| **Black Box** | **Zero Knowledge** | An external attacker (Outsider). |
| **White Box** | **Full Knowledge** | An internal attacker or audit (Insider). |
| **Gray Box** | **Partial Knowledge** | An attacker with some info (e.g., compromised user). |

**The Teams:**
*   **Red Team:** Attackers (Offensive).
*   **Blue Team:** Defenders (Defensive).
*   **White Team:** Referees (Governance/Rules).

---

#### **5. Reconnaissance & OpSec**

*   **Operations Security (OpSec):** Risk management process that views operations from the adversary's perspective to protect sensitive data.
*   **Reconnaissance Types:**
    *   **Active Recon:** Touching the target (e.g., Ping, Nmap scan). Can be detected.
    *   **Passive Recon:** Gathering info *without* touching the target (e.g., WHOIS, OSINT, Social Media). Hard to detect.
*   **ST&E (Security Test and Evaluation):** Testing performed on a system **after** it is operational to ensure controls are working as intended.