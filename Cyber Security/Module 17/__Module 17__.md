[[17.1 Virtualization and Cloud Computing]]
[[17.2 The Domains of Cloud Security]]
[[17.3 Cloud Infrastructure Security]]
[[17.4 Cloud Application Security]]
[[17.5 Cloud Data Security]]
[[17.6 Protecting VMs]]

---

### **Module 17: Virtualization and Cloud Security - Exam Notes**

#### **1. Core Virtualization Concepts**

*   **Hypervisor:** The software that creates and manages Virtual Machines (VMs).
    *   **Type 1 (Bare-metal):** Runs directly on hardware (e.g., VMware ESXi, Hyper-V). More secure and efficient.
    *   **Type 2 (Hosted):** Runs as an application on a host OS (e.g., VirtualBox, VMware Workstation).
*   **Virtual Machine (VM):** A full, independent Guest OS running on a hypervisor. It is heavy, slow to boot, but has strong isolation.
*   **Container:** A lightweight alternative. Packages an application and its dependencies, but **shares the host OS kernel**. It is small, fast to boot, but has weaker isolation than a VM. (e.g., Docker).
*   **VDI (Virtual Desktop Infrastructure):** Centralized hosting of user desktops on servers, streamed to thin clients.

#### **2. Key Virtualization Security Risks**

*   **VM Escape:** A critical vulnerability where an attacker "breaks out" of a VM to access the host hypervisor, potentially compromising all other VMs on that host.
*   **VM Sprawl:** The uncontrolled creation of unmanaged, unpatched VMs.
    *   **Risks:** Creates security vulnerabilities ("zombie" servers) and wastes resources/money.
    *   **Mitigation:** Strict auditing, monitoring, and decommissioning policies.

---
#### **3. Cloud Service & Deployment Models**

**The 3 Service Models (XaaS):**

| Model | You Get... | You are Responsible For... |
| :--- | :--- | :--- |
| **IaaS** (Infrastructure) | Virtual Hardware (VMs, storage, network) | The OS, applications, and data. |
| **PaaS** (Platform) | A Development Platform | Your application code and data. |
| **SaaS** (Software) | A Ready-to-use Application | Your user data and access management. |

**The 4 Deployment Models:**

| Model | Description |
| :--- | :--- |
| **Public Cloud**| Shared infrastructure provided by a vendor (e.g., AWS, Azure). Pay-as-you-go, less control. |
| **Private Cloud**| Dedicated infrastructure for a single organization. Maximum control, highest cost. |
| **Hybrid Cloud** | A mix of public and private clouds, connected together. |
| **Community Cloud**| Shared infrastructure for a specific group of organizations with common needs (e.g., healthcare). |

---
#### **4. Edge & Fog Computing**

*   **Purpose:** To process data closer to where it is created, reducing latency for IoT and time-sensitive applications.
*   **Edge Computing:** Processing happens **on the device/sensor itself**. Lowest latency.
*   **Fog Computing:** Processing happens on a **local gateway or server** within the LAN, between the edge and the cloud.

---
#### **5. Top Cloud Security Threats**

*   **Misconfiguration:** The most common cause of breaches. Publicly exposed storage, overly permissive firewalls.
*   **Compromised Credentials:** Stolen user or high-privilege service accounts.
*   **Insecure APIs:** Public-facing APIs are a primary attack vector.
*   **Shared Responsibility Model Failure:** Misunderstanding who is responsible for what (CSP vs. Client). **You are ALWAYS responsible for your data.**
*   **Insider Threat** & **Data Breaches**.

---
#### **6. Secure Application Development & Coding**

*   **Lifecycle:** `Development -> Testing -> Staging -> Production`
    *   **Staging Environment:** Must be a replica of production to test security settings accurately.
*   **Input Validation:** The CRITICAL process of checking all user input to prevent attacks like SQL Injection. Validation rules check for `size`, `format`, `range`, `consistency`, etc.
*   **Integrity Checks:**
    *   **Hashing (Checksums):** Ensures data is unaltered. (e.g., MD5, SHA-256).
    *   **Code Signing:** A digital signature on software that proves authenticity (who made it) and integrity (it hasn't been changed).
*   **Other Secure Coding Techniques:**
    *   **Obfuscation/Camouflage:** Making code hard to reverse-engineer.
    *   **Stored Procedures:** Pre-compiled SQL to help prevent injection attacks.
    *   **Secure Cookies:** Using the `Secure` flag to ensure cookies are only sent over HTTPS.

---
#### **7. Data States & Encryption**

*   **The Three States of Data:**
    1.  **Data at Rest:** Stored on disk. Protect with **Full Disk Encryption, database encryption**.
    2.  **Data in Transit:** Moving over a network. Protect with **TLS/SSL (HTTPS), IPsec (VPNs)**.
    3.  **Data in Process:** Actively being used in RAM/CPU. Hardest to protect; requires a secure runtime environment.