---
tags: #cybersecurity #fundamentals #application_security #mobile_security #lecture_notes
deck: CyberSec_Course
topic: Client and Application Security
lecture: 9
---

# Lecture 9: Client and Application Security

## 1. The Need for Client-Side Protection
Modern web applications rely heavily on the user's browser (the client) to execute code.
*   **The Problem**: Websites load an average of 30+ **third-party scripts** at runtime.
*   **The Risk**: Organizations lose visibility and control over code behavior once it loads on the user's device.
*   **The Consequence**: Increased opportunity for attacks as sensitive data (e.g., credit cards) traverses the network.

## 2. Types of Client-Side Attacks
The goal is usually to steal sensitive info (credit card numbers, PII) or hijack sessions.
*   **[[Web Skimming]] (e.g., Magecart)**: Attackers inject malicious code into payment forms to collect data before it is sent to the legitimate server.
*   **Customer Hijacking**: Diverting a user to a different, malicious page.

### Frameworks for Protection
To identify and mitigate these vulnerabilities, rely on standard frameworks:
*   **[[OWASP]]** (Open Web Application Security Project)
*   **[[NIST]] Cybersecurity Framework**
*   **Regulatory Requirements**

---

## 3. Cross-Site Scripting ([[XSS]])
The most common application-level web attack.
*   **Definition**: An **injection** technique where an attacker gets a malicious script to run on a *legitimate* target website.
*   **Mechanism**: The website accepts untrusted input without validation and serves it to other users.
*   **The Flow**:
    1.  Attacker injects script into a vulnerable site (e.g., a comment section).
    2.  Victim visits the site.
    3.  Malicious script executes in the Victim's browser.
    4.  Script sends Victim's data (like [[Cookies]] or session tokens) to the Attacker.

---

## 4. Securing Web Applications
Defense requires a layered approach:
1.  **Protocol Compliance**: Checking data against standards.
2.  **Traffic Control**: Using [[Neural Networks]] or AI to detect anomalies.
3.  **Signature Analysis**: Identifying known malicious patterns.
4.  **Injection Protection**: Specific defenses against **[[SQL Injection]]** and **[[XSS]]**.
5.  **Real-time Monitoring**: Gaining visibility into third-party scripts running on the client.

---

## 5. Mobile Device Security
Mobile threats are categorized by how the attacker accesses the device.

### A. Attack Vectors
1.  **Physical Access**: Stealing the device itself.
2.  **Malicious Applications**:
    *   **Official Stores** (Google Play/App Store): Rare, but "clickbait" apps (e.g., "Virus Cleaner 2019") can be malicious.
    *   **Unofficial Stores**: Sideloading APKs (Android) or using configuration profiles (iOS).
    *   **USB**: Installing apps via connection to a PC.
3.  **Communication Channel ([[Man-in-the-Middle]])**:
    *   Interception of traffic between the app and the server.
    *   **Spoofing**: Altering server responses (phishing) or client requests (changing transaction amounts).
4.  **Remote Attacks**:
    *   Exploiting URL handlers (e.g., `http://` links opening a vulnerable app instead of a browser).
    *   **Android Instant Apps**: Triggering downloads via links to exploit installation vulnerabilities.

### B. Defense Strategies

#### For Users (How to protect yourself)
*   **Physical**: Do not leave devices unattended; use Biometrics/Passcodes.
*   **OS Integrity**: Do not **Root** (Android) or **Jailbreak** (iOS); this elevates privileges for attackers.
*   **Updates**: Install OS and App updates immediately.
*   **Authentication**: Use [[MFA]] (2-Factor Authentication) wherever possible.

#### For Developers
*   **[[SDL]] (Security Development Lifecycle)**: Implement security practices during the design and coding phases.
*   **Testing**: Test against specific intruder patterns and scenarios.