[[24.1 Information Sources]]
[[24.2 Threat Intelligence Services]]
[[24.3 Threat Intelligence Summary]]

---

### **Module 24: Threat Intelligence - Exam Notes**

#### **1. Key Network Intelligence Communities**

You must know who provides the data and standards used in cybersecurity.

| Organization | Role / Key Contribution |
| :--- | :--- |
| **SANS** | **Training & Research.** Provides the "Internet Storm Center" and "Reading Room". |
| **MITRE** | **The Dictionary.** Maintains the **CVE** (Common Vulnerabilities and Exposures) list. |
| **FIRST** | **Coordination.** Forum of Incident Response and Security Teams. connects gov/commercial teams globally. |
| **(ISC)²** | **Certification.** International body governing certifications like **CISSP**. |
| **CIS** | **Benchmarks.** Center for Internet Security. Provides best-practice configuration guides. |

---

#### **2. Threat Intelligence Services**

These services analyze data to create **IOCs (Indicators of Compromise)** and update security devices automatically.

*   **Cisco Talos:** One of the largest commercial intel teams.
    *   Updates firewall rules/signatures in **real-time**.
    *   Maintains open-source rules for **Snort**, **ClamAV**, and **SpamCop**.
*   **FireEye:** Uses a "three-pronged" approach (Intel, Expertise, Technology). Known for the **Helix** platform (SIEM/SOAR).
*   **AIS (Automated Indicator Sharing):**
    *   Run by the **U.S. DHS (Dept of Homeland Security)**.
    *   **Free** service for real-time exchange between the **Government** and the **Private Sector**.

---

#### **3. Intelligence Sharing Standards (The "Big Three")**

To share threat data automatically between different systems, we need a common language.

| Acronym | Full Name | Function | Analogy |
| :--- | :--- | :--- | :--- |
| **STIX** | Structured Threat Information Expression | **The Payload.** Defines *what* the threat info looks like (File format/Structure). | The Letter inside the envelope. |
| **TAXII** | Trusted Automated Exchange of Indicator Information | **The Transport.** Defines *how* to send the info (Application Protocol over HTTPS). | The Mail Truck/Postal Service. |
| **CybOX** | Cyber Observable Expression | **The Schema.** Standardized way to describe events (IPs, Hashes). Now part of STIX. | The Language written in the letter. |

---

#### **4. Threat Intelligence Platforms (TIP)**

*   **Problem:** Too many data feeds with different formats.
*   **Solution (TIP):** A centralized system that **aggregates** data from multiple sources (Talos, FireEye, Open Source) into a single, readable format.
*   **Key Data Types:**
    1.  **IOCs:** Indicators of Compromise (File hashes, bad IPs).
    2.  **TTPs:** Tools, Techniques, and Procedures (How attackers work).
    3.  **Reputation:** Trust scores for domains/IPs.

#### **5. Honeypots**

*   **Definition:** A decoy system designed to **attract** attackers.
*   **Purpose:** To observe attacker behavior and gather intelligence without putting real assets at risk.
*   **Best Practice:** Deploy honeypots in the **Cloud** to isolate them completely from your production network.