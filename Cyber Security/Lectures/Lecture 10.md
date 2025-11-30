---
tags: #cybersecurity #mobile_security #pentesting #ethical_hacking #lecture_notes
deck: CyberSec_Course
topic: Mobile Security & Penetration Testing
lecture: 10
---

# Lecture 10: Mobile Security & Penetration Testing

## Part 1: Mobile Device Security

Mobile attacks generally fall into five specific scenarios.

### 1. Attack Scenarios & Defenses

#### A. Physical Access
*   **Threat**: Theft, loss, or connecting to malicious hardware (e.g., fake chargers/USB connections).
*   **Defense**:
    *   Never leave devices unattended.
    *   Enable **Biometrics** or strong passcodes.
    *   **Do not** elevate privileges ([[Rooting]] on Android or [[Jailbreaking]] on iOS).
    *   Disable lock screen notifications.

#### B. Malicious Applications
*   **Threat**: Apps from untrusted sources or malicious apps hiding in official stores (e.g., fake "Virus Cleaners").
*   **Defense**:
    *   Avoid third-party app stores.
    *   Check app permissions and developer reputation even on Google Play/App Store.
    *   Keep OS and apps updated to patch known vulnerabilities.

#### C. Communication Channel ([[Man-in-the-Middle]])
*   **Threat**: Intercepting traffic via untrusted Wi-Fi, proxies, or VPNs.
*   **Defense**:
    *   Avoid banking on public Wi-Fi.
    *   Do not install third-party certificates.
    *   *Indicator*: If secure apps (like banking) fail to connect, the network may be compromised.

#### D. Remote Attacks
*   **Threat**: Exploits delivered via servers or URLs (e.g., clicking a link that triggers a malicious payload).
*   **Defense**: **Patch Management** (Timely OS and App updates).

#### E. Server-Side Attacks
*   **Threat**: Attacking the backend API rather than the phone itself.
*   **Defense**:
    *   **Users**: Use complex passwords and [[2FA]] (Two-Factor Authentication).
    *   **Developers**: Implement [[SDL]] (Security Development Lifecycle) and test against intruder patterns.

---

## Part 2: Penetration Testing

### 1. Definition
**Penetration Testing** (Pentest/Ethical Hacking) is the practice of simulating cyberattacks on a computer system, network, or web application to identify vulnerabilities before malicious actors do.

### 2. Pentest vs. Vulnerability Assessment
| Feature | [[Vulnerability Assessment]] | [[Penetration Testing]] |
| :--- | :--- | :--- |
| **Goal** | Find and list loopholes/weaknesses. | Exploit loopholes to break in/prove risk. |
| **Method** | Automated scanning using tools. | Manual & Automated real-time simulation. |
| **Outcome** | A list of potential vulnerabilities. | Proof of exploit (system compromise). |
| **Focus** | Breadth (find everything). | Depth (can I get to the "crown jewels"?). |

### 3. Causes of Vulnerabilities
*   **Design Flaws**: Errors in the architectural phase.
*   **Configuration**: Incorrect setup of hardware/software.
*   **Human Error**: Mistakes in deployment or maintenance.
*   **Complexity**: Systems too complex to monitor effectively.
*   **Lack of Training**: Staff unaware of security protocols.

### 4. Testing Approaches
1.  **Manual Testing**: Consistent standard approach.
    *   *Workflow*: Planning -> Intelligence -> Vulnerability Analysis -> Exploitation -> Post-exploitation -> Reporting.
2.  **Automated Testing**: Using software tools to scan and exploit.
    *   *Common Tools*: [[Nmap]] (Scanning), [[Metasploit]] (Exploitation), [[Wireshark]] (Packet Analysis), [[Nessus]] (Vuln Scanning), THC Hydra (Brute force).
3.  **Combination**: Using both manual logic and automated speed.

### 5. Testing Perspectives ("The Boxes")
*   **[[White Box Testing]]**: Tester has full knowledge of the system (code, network map).
*   **[[Black Box Testing]]**: Tester has zero knowledge (simulates an external hacker).
*   **[[Gray Box Testing]]**: Partial knowledge (simulates an insider or compromised user).

### 6. Limitations
*   **Time/Cost**: Can be expensive and time-constrained.
*   **Scope**: Limited by the contract; legitimate vulnerabilities might be "out of scope."
*   **Risk**: Aggressive testing can crash systems or corrupt data ("System Destruction").