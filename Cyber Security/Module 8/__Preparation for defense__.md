
### **Module 7: The Windows Operating System**

**Main Idea:** This module covers the fundamental architecture of the Windows operating system, its built-in security features, and the tools used to manage and secure it.

**Key Terms and Concepts:**

*   **Windows Registry:** A hierarchical database that stores low-level configuration settings for the operating system and for applications that opt to use the registry. It's a critical component for system administration and a target for malware.
*   **User Account Control (UAC):** A security feature that helps prevent unauthorized changes to the system. It prompts for permission when a task requires administrative-level access, separating standard user privileges from administrative privileges.
*   **Principle of Least Privilege (PoLP):** A foundational security concept where users and applications are only given the access and permissions absolutely necessary to perform their required tasks. This minimizes the potential damage from an error or security breach.
*   **NTFS (New Technology File System):** The standard file system for Windows. Its key security feature is the use of Access Control Lists (ACLs) to define permissions for individual users and groups on files and folders.
*   **BitLocker:** A full-disk encryption feature included with certain versions of Windows. It is designed to protect data by providing encryption for entire volumes.
*   **Event Viewer:** An administrative tool used to view event logs. Key logs for security include the **Security Log** (records events like successful and failed logon attempts), **System Log**, and **Application Log**.
*   **Local Security Policy:** A set of rules and settings that control the security configuration on a local computer. It includes policies for passwords (e.g., complexity, length, history), account lockout, and user rights assignment.

---

### **Module 8: Linux Overview**

**Main Idea:** This module introduces the Linux operating system, focusing on its structure, command-line interface (CLI), and fundamental security mechanisms that make it a popular choice in servers and security appliances.

**Key Terms and Concepts:**

*   **Kernel:** The core of the Linux OS. It manages the system's resources, and it's the bridge between the hardware and the software applications.
*   **Shell:** A program that takes commands from the user and gives them to the OS to perform. It's the primary interface for interacting with a Linux system (e.g., Bash, Zsh).
*   **Distribution (Distro):** A complete Linux operating system packaged with the Linux kernel, management tools, and other software. Examples include Ubuntu, Debian, CentOS, and the security-focused Kali Linux.
*   **File System Hierarchy Standard (FHS):** A standardized layout for directories in a Linux system. Key directories include `/etc` (configuration files), `/var` (variable data like logs), `/home` (user home directories), and `/bin` (essential user binaries).
*   **File Permissions (rwx):** The basic level of access control in Linux. Permissions are set for **read (r)**, **write (w)**, and **execute (x)** for three types of users: the **owner**, the **group**, and **others**.
*   **`sudo` (superuser do):** A command that allows a permitted user to execute a command as another user, most commonly the superuser (`root`). It enables administrative tasks without logging in as the root user, which is a security best practice.
*   **`root`:** The superuser account. This account has unlimited privileges to do anything on the system.

---

### **Module 9: System and Endpoint Protection**

**Main Idea:** This module focuses on the various threats that target endpoints (computers, servers, mobile devices) and the technologies and strategies used to protect them from compromise.

**Key Terms and Concepts:**

*   **Endpoint:** Any device connected to the network, such as a laptop, desktop, server, or smartphone.
*   **Malware:** A broad term for any malicious software. Types include:
    *   **Viruses:** Attach to clean files and spread to other clean files.
    *   **Worms:** Self-replicating malware that spreads across networks without human intervention.
    *   **Ransomware:** Encrypts a victim's files and demands a ransom to restore access.
    *   **Spyware:** Secretly gathers information about a user and sends it to a third party.
*   **Antivirus (AV) / Antimalware:** Software designed to detect, prevent, and remove malware. Traditional AV relies on **signature-based detection** (matching known malware patterns), while modern antimalware also uses **heuristics** and **behavioral analysis** to detect new threats.
*   **Host-based Intrusion Prevention System (HIPS):** Security software that monitors a single host (an endpoint) for suspicious activity by analyzing system calls, application logs, and other activities. It can block malicious behavior in real-time.
*   **Host-based Firewall:** Software running on an endpoint that controls network traffic flowing in and out of that specific device, allowing or blocking traffic based on a set of security rules.
*   **Data Loss Prevention (DLP):** A strategy and set of tools to ensure that sensitive data is not lost, misused, or accessed by unauthorized users. DLP software can identify and block the transmission of confidential information.

---

### **Module 10: Cybersecurity Principles, Practices, and Processes**

**Main Idea:** This module covers the foundational, high-level concepts and frameworks that guide all cybersecurity efforts.

**Key Terms and Concepts:**

*   **CIA Triad:** The three core principles of information security:
    *   **Confidentiality:** The principle of ensuring that data is only accessed by authorized individuals. (Encryption is a key tool).
    *   **Integrity:** The principle of ensuring that data is accurate, consistent, and has not been tampered with. (Hashing is a key tool).
    *   **Availability:** The principle of ensuring that systems and data are accessible to authorized users when needed. (Redundancy and backups are key tools).
*   **Risk:** The potential for loss, damage, or destruction of an asset as a result of a threat exploiting a vulnerability. It is often expressed as **Risk = Threat x Vulnerability**.
*   **Threat:** Any circumstance or event with the potential to adversely impact organizational operations, assets, or individuals.
*   **Vulnerability:** A weakness in a system, process, or its controls that could be exploited by a threat actor.
*   **Countermeasure (or Control):** An action, device, procedure, or technique that reduces a threat, a vulnerability, or an attack by eliminating or preventing it, by minimizing the harm it can cause, or by discovering and reporting it.

---

### **Module 11: Understanding Defense**

**Main Idea:** This module moves from individual controls to broader defensive strategies, organizational structures, and the importance of policies and compliance.

**Key Terms and Concepts:**

*   **Defense-in-Depth:** A security strategy that involves layering multiple, independent security controls to protect an asset. The failure of a single control does not lead to a complete compromise. For example, using a firewall, an IPS, and host-based antimalware together.
*   **Security Operations Center (SOC):** A centralized team, location, and facility responsible for continuously monitoring an organization's security posture, as well as detecting, analyzing, and responding to cybersecurity incidents.
*   **Security Policies:** High-level documents that define an organization's security goals and assign responsibilities. They are mandatory.
*   **Security Standards:** Mandatory rules that provide specific details on how to implement policies. For example, a policy might state "all servers must be secured," while a standard would specify "all servers must use a 14-character complex password."
*   **Security Guidelines:** Recommendations and best practices. They are not mandatory but are strongly advised.
*   **Procedures:** Detailed, step-by-step instructions for performing a specific task, such as how to report a security incident.
*   **Compliance:** The act of adhering to relevant external laws, regulations, and industry standards (e.g., GDPR, HIPAA, PCI DSS).

---

### **Module 12: System and Network Defense**

**Main Idea:** This module focuses on the practical techniques used to secure computer systems and network infrastructure to reduce the likelihood of a successful attack.

**Key Terms and Concepts:**

*   **Hardening:** The process of securing a system by reducing its attack surface. This includes disabling unnecessary services, changing default credentials, applying security patches, and configuring security settings.
*   **Attack Surface:** The total number of exposure points or "vectors" through which an attacker can attempt to enter or extract data from a system or network.
*   **Network Segmentation:** The practice of dividing a network into smaller, isolated subnetworks. This contains breaches, preventing an attacker from moving freely across the entire network.
*   **Demilitarized Zone (DMZ):** A perimeter network segment that is isolated from the secure internal network. It is used to host public-facing services like web and email servers, acting as a buffer zone.
*   **Intrusion Detection System (IDS):** A device or software application that monitors network or system activities for malicious activities or policy violations. An IDS only detects and alerts.
*   **Intrusion Prevention System (IPS):** An advanced version of an IDS that can also take action to block or prevent the detected malicious activity.
*   **Virtual Private Network (VPN):** Creates an encrypted "tunnel" over a public network (like the internet) to provide secure, remote access to a private network.

---

### **Module 13: Access Control**

**Main Idea:** This module details the methods and models used to control who can access specific resources and what actions they are permitted to perform.

**Key Terms and Concepts:**

*   **Access Control:** The process of granting or denying specific requests to obtain and use information and related information processing services.
*   **IAAA (The Four Components of Access Control):**
    *   **Identification:** The act of claiming an identity (e.g., providing a username).
    *   **Authentication:** The process of proving an identity (e.g., providing a password, using a fingerprint).
    *   **Authorization:** The process of determining if an authenticated user has the right to perform a specific action or access a resource.
    *   **Accountability:** The ability to trace an action to a specific user (achieved through logging and auditing).
*   **Multi-Factor Authentication (MFA):** A security method that requires the user to provide two or more verification factors to gain access. The factors are typically: something you **know** (password), something you **have** (token, phone), and something you **are** (biometric).
*   **Access Control Models:**
    *   **Discretionary Access Control (DAC):** The owner of the resource specifies who is allowed access. This is the model used by Windows and Linux file systems.
    *   **Mandatory Access Control (MAC):** Access is determined by a central authority based on security classifications (labels) of objects and subjects. It is highly structured and common in military/government environments.
    *   **Role-Based Access Control (RBAC):** Access rights are assigned to roles rather than individual users. Users are then assigned to roles, inheriting the permissions of that role (e.g., "Accountant," "System Admin"). This is the most common model in organizations.
*   **RADIUS (Remote Authentication Dial-In User Service):** A networking protocol that provides centralized Authentication, Authorization, and Accounting (AAA) for users connecting to and using a network service. It is commonly used for Wi-Fi and VPN access.
*   **TACACS+ (Terminal Access Controller Access-Control System Plus):** A Cisco-proprietary protocol that also provides AAA services. A key difference from RADIUS is that it separates the AAA functions, offering more flexibility and control, particularly for device administration.