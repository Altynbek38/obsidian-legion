
# **Defending Systems and Devices**

A good administrator protects the OS by removing unnecessary services and keeping patches up to date.  
Security updates should follow a **systematic plan**:

1. Monitor for new security info.
2. Evaluate updates.
3. Plan installations.
4. Apply patches with documentation.

Also, set a **baseline** — normal performance and configuration standards — to detect vulnerabilities or unusual behavior later.


# Do You Know Your Stuff?

| Protection Type          | What It Does                                                                    |
| ------------------------ | ------------------------------------------------------------------------------- |
| **Antivirus**            | Detects viruses → alerts user → quarantines or deletes them.                    |
| **Adware Protection**    | Blocks programs that show unwanted ads/popups.                                  |
| **Phishing Protection**  | Stops access to known fake (phishing) websites and warns about suspicious ones. |
| **Spyware Protection**   | Detects keyloggers and other spying tools that steal info.                      |
| **Trusted Source Check** | Warns users when running or downloading apps from unsafe or unknown sources.    |


# Points to Remember

| Concept                               | What It Means                                                               | Why It’s Dangerous                                                                   |
| ------------------------------------- | --------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| **Rogue Antivirus**                   | Fake antivirus popups that look like real Windows alerts                    | Clicking them can install real malware                                               |
| **Fileless Malware**                  | Runs in memory using legit tools (e.g., PowerShell); leaves no file on disk | Hard to detect; disappears after reboot but can cause serious damage while running   |
| **Malicious Scripts**                 | Created using scripting languages like Python, Bash, or VBA (macros)        | Scripts can automate attacks or download/install malware                             |
| **Unapproved/Non-Compliant Software** | Software installed without permission, intentionally or accidentally        | May violate company security policy or interfere with systems, even if not malicious |


# Patch Management
**Patches** are code updates that fix vulnerabilities to prevent malware attacks. A **service pack** is a collection of multiple patches and upgrades. Many attacks are successful because users fail to install the latest patches.

As a cybersecurity professional, it is best practice to test a patch before deploying it. **Patch management tools** allow administrators to manage updates locally, offering greater control.

**Benefits of a Centralized Patch Management Tool:**
- Administrators can approve or decline updates.
- Updates can be forced on a specific schedule.
- Reports can be generated on which systems need updates.
- Systems get verified updates from a local server, not the internet.
- Users cannot disable or avoid updates.

A **proactive approach** to patch management, which includes updating the OS and third-party applications (e.g., Adobe, Java), is essential for preventing ransomware and other threats.

# Endpoint Security
A **host-based firewall** is software on a device that filters incoming and outgoing network traffic by managing access through ports. It uses rules to block or allow connections, protecting the endpoint from unauthorized access. An example is the Windows Firewall.

A **Host-Based Intrusion Detection System (HIDS)** is software that monitors a device for suspicious activity by analyzing system calls, file access, and registry changes. It **detects** and logs potential threats locally but does not actively block them.

A **Host-Based Intrusion Prevention System (HIPS)** actively monitors a device for malicious activity and known attack patterns. Unlike HIDS, which only detects and alerts, HIPS is designed to **prevent** attacks by taking action, such as dropping malicious packets or terminating connections.

**Endpoint Detection and Response (EDR)** is an integrated solution that continuously monitors endpoints, collecting and analyzing data to detect and respond to advanced threats. Unlike traditional antivirus, which primarily blocks known malware, EDR can also identify and remediate threats that have already bypassed other defenses.

**Data Loss Prevention (DLP)** tools provide a centralized way to ensure that sensitive data is not lost, misused, or accessed by unauthorized users.

A **Next-Generation Firewall (NGFW)** is a network security device that integrates traditional firewall capabilities with more advanced functions, such as an application firewall, deep packet inspection (DPI), and an Intrusion Prevention System (IPS), to provide more comprehensive security.


# Encryption
**Encryption** is a method used to protect data by transforming it into an unreadable format using a complex algorithm. A special key is required to decrypt the information, returning it to its original, readable form.


# Host Encryption
**Full Disk Encryption (FDE)** is used to encrypt the entire contents of a drive. **BitLocker** is the FDE feature built into Microsoft Windows. For BitLocker to work, the **Trusted Platform Module (TPM)**—a specialized security chip on the motherboard—must be enabled in the BIOS to store encryption keys securely.

For removable drives, **BitLocker To Go** provides encryption without requiring a TPM, instead using a password for decryption. A **Self-Encrypting Drive (SED)** is a hardware-based solution where the drive automatically encrypts all data written to it. Additionally, **Windows Encrypting File System (EFS)** is a feature that allows users to encrypt specific files and folders.


# Boot Integrity
**Boot integrity** ensures that a system is trusted and has not been altered while the operating system loads. The process starts with firmware, such as the older **BIOS** or the modern **UEFI (Unified Extensible Firmware Interface)**, which is preferred for its advanced features like 64-bit support.

**Secure Boot** is a security standard that ensures a device boots using only trusted software. The firmware checks the digital signature of each piece of boot software, including the operating system. If the signatures are valid, the system boots.

**Measured Boot** provides even stronger validation. It measures each component during startup, from the firmware to the drivers, and stores these measurements in the **TPM chip**. This creates a log that can be checked remotely to verify the client's boot state, identifying untrusted applications and allowing antimalware to load earlier.


# Apple System Security Features
Apple provides robust endpoint protection through a combination of hardware and software security features.

**Security-Focused Hardware**
The **Secure Enclave** is a dedicated "system on a chip" that includes a special CPU, boot ROM, and a hardware-based AES encryption engine to handle sensitive operations securely and separately from the main processor.

**Encrypted Storage**  
Features like **FileVault** and Apple Data Protection use the hardware AES engine to encrypt and decrypt files on the fly. This keeps the encryption keys isolated from the OS and applications, enhancing security.

**Secure Boot**  
The **Boot ROM** is firmware that protects low-level hardware and ensures that only genuine, unaltered Apple operating system software is allowed to run during startup.

**Secure Biometric Data**  
Biometric data (for Touch ID and Face ID) is processed directly within the secure hardware, keeping it completely segregated from the main operating system and protecting it from malware.

**Find My Mac**  
This feature helps locate a lost or stolen Mac. It also allows the owner to remotely lock the device or erase its storage to protect sensitive data.

**XProtect**  
**XProtect** is Apple's built-in, signature-based antimalware technology that scans for and prevents the execution of known malware. It will alert the user and offer to remove detected threats.

**Malware Removal Tool (MRT)**  
The **MRT** works alongside XProtect to detect and remove existing malware infections from a system. It receives automatic updates from Apple and runs checks during startup and user login.

**Gatekeeper**  
**Gatekeeper** is a security feature that ensures only authentic, digitally-signed software from Apple-notarized developers can be installed, preventing users from running potentially malicious applications.


# Physical Protection of Devices
**Computer Equipment**  
To physically protect computer equipment, use **cable locks** to secure devices, keep telecommunication rooms locked, and use **security cages** (like Faraday cages) to block electromagnetic fields and prevent unauthorized access.

**Door Locks**  
A standard keyed lock is common but easily forced. A **deadbolt** provides better security. **Cipher locks**, which use a code sequence, offer more control by allowing programmable access times and logging entry records, eliminating the risk of lost or stolen keys.

**Radio Frequency Identification (RFID) Systems**  
**RFID** uses radio waves to identify and track objects via tags attached to them. These tags contain a small integrated circuit and antenna. RFID is used to automate asset tracking and can also wirelessly lock, unlock, or configure electronic devices.



# **Antimalware Protection**

# Endpoint Threats
An **endpoint** is any host on a network, including traditional computers, servers, IoT devices (like cameras and controllers), and remote devices connecting via VPN. Each endpoint represents a potential entry point for malware to access the network. Malware remains a major challenge due to the rising frequency and cost of attacks like ransomware, high volumes of malicious spam, and the ability of malware to rapidly change its features to evade detection.


# Endpoint Security
Network security involves protecting against both external and internal threats. While external attacks (like DoS and data breaches) are handled by perimeter devices such as **Next-Generation Firewalls (NGFWs)**, **Intrusion Prevention Systems (IPS)**, and VPNs, many attacks originate from inside the network.

Securing the internal LAN is critical because a compromised internal host can become a starting point for an attacker to access sensitive servers and data. Internal security focuses on two key areas:

- **Endpoints:** Devices like laptops, desktops, and servers, which are vulnerable to malware.
- **Network Infrastructure:** Devices like switches and routers, which are vulnerable to LAN-based attacks (e.g., spoofing, MAC table overflow).


# Host-Based Malware Protection
As network perimeters expand with remote access (VPNs) and mobile devices connecting from unsecured networks, host-based security tools are essential for protection.

**Antivirus/Antimalware Software**  
This is software installed on a host to detect and mitigate malware. It uses three main detection methods:

- **Signature-based:** Matches characteristics of known malware.
- **Heuristics-based:** Identifies general features shared by malware types.
- **Behavior-based:** Analyzes suspicious actions.

This protection can be **agent-based** (running on each machine) or **agentless** (scanning from a central system), which is common in virtual environments to save resources.

**Host-based Firewall**  
This software runs on a single host to restrict incoming and outgoing network connections. It can prevent a host from becoming infected and stop an already infected host from spreading malware to others. Examples include Windows Defender Firewall and Linux iptables.

**Host-based Security Suites**  
These are all-in-one packages that combine multiple security tools like antivirus, a firewall, HIPS, and anti-phishing. They provide a **layered defense** and offer crucial **logging (telemetry)** functionality that sends data to a central location for analysis by cybersecurity teams. Independent labs like **AV-TEST** provide reviews of these products.


# Network-Based Malware Protection
In a modern "borderless network," security is enhanced by using network-based devices that scan traffic for all endpoints. These devices provide multiple layers of scanning and can share threat information to make better security decisions. Key network-level protection technologies include:

- **Advanced Malware Protection (AMP):** A network-level solution that provides protection against viruses and malware for all connected endpoints.
- **Email Security Appliance (ESA):** A device that filters spam and malicious emails before they ever reach an endpoint.
- **Web Security Appliance (WSA):** A device that filters web traffic, blocks access to dangerous websites, and enforces acceptable use policies.
- **Network Admission Control (NAC):** A system that permits only authorized and compliant devices to connect to the network, ensuring they meet security standards first.

These technologies work together to provide more comprehensive protection than host-based solutions can alone.



# **Host-Based Intrusion Prevention**

# Host-Based Firewalls

A **host-based firewall** is a software program that controls network traffic entering or leaving a single computer. It uses predefined policies (profiles) or custom rules based on addresses, protocols, and ports to filter packets. These firewalls can alert users to suspicious behavior and log events, including connection details (IPs, ports, date/time).

A **distributed firewall** is a centrally managed system that combines the features of host-based firewalls, allowing an administrator to push rules to multiple hosts.

Examples of host-based firewalls include:
- **Windows Defender Firewall:** Uses a profile-based approach (Public, Private, Domain) to apply different rule sets depending on the network's trust level.
- **iptables:** A command-line utility for Linux that allows administrators to configure the kernel's Netfilter firewall rules.
- **nftables:** The modern successor to iptables in Linux, using a virtual machine in the kernel to inspect packets.
- **TCP Wrappers:** A rule-based access control and logging system for Linux.  


# Host-Based Intrusion Detection System (HIDS)
A **Host-Based Intrusion Detection System (HIDS)** is a comprehensive, agent-based security application designed to protect a host from known and unknown malware. It combines the functionalities of antimalware and firewall software to both **detect** threats and **prevent** them from executing. HIDS performs detailed monitoring of system configurations and application activity, with capabilities including log analysis, file integrity checking, policy enforcement, rootkit detection, and alerting. These systems often use a central management server to oversee the protected endpoints.


# HIDS Operation
A HIDS functions as both a detection and prevention system. It uses proactive and reactive strategies to protect a host. For **known threats**, it uses **signature-based** detection to identify and block malware. However, this method is ineffective against new **zero-day** threats and **polymorphic** malware that constantly changes.

To combat unknown threats, a HIDS uses two main strategies:
- **Anomaly-based detection:** The HIDS creates a baseline of normal system behavior and flags any significant deviations as potential intrusions. While effective, this can lead to a high number of false positives.
- **Policy-based detection:** The HIDS enforces a set of predefined rules that describe acceptable system behavior. If a process violates a policy, the HIDS takes action, such as shutting down the process and sending an alert.


# HIDS Products
Many HIDS products are available, most of which use software agents on the host that report to a centralized management server. This allows for integration with network security monitoring and threat intelligence. Examples of HIDS products include **Cisco AMP for Endpoints**, **AlienVault USM**, and **Tripwire**.

A popular open-source example is **OSSEC**. It uses a central manager server and agents installed on hosts (Windows, Linux, Mac). OSSEC monitors system logs, performs file integrity checking, detects rootkits, and can be configured to run automated responses to threats.


# Attack Surface
An **attack surface** is the total sum of the vulnerabilities in a system that are accessible to an attacker. This includes everything from open ports and running software to network protocols and even users. The attack surface is constantly expanding due to trends like the **Internet of Things (IoT)**, **Bring Your Own Device (BYOD)**, and cloud computing.

The SANS Institute identifies three main components of an attack surface:
- **Network Attack Surface:** Exploits vulnerabilities in network protocols, including wired, wireless, and IoT-specific protocols.
- **Software Attack Surface:** Exploits vulnerabilities in web, cloud, or host-based applications.
- **Human Attack Surface:** Exploits weaknesses in user behavior through methods like social engineering, insider threats, and human error.


# Application Blocklisting and Allowlisting
One way to decrease the attack surface is by using **blocklists** and **allowlists**. A **blocklist** (blacklist) specifies which applications or websites are prohibited. An **allowlist** (whitelist) is a more restrictive approach, specifying only the programs or sites that are permitted to run and blocking all others.

Allow lists are created in accordance with an organization's **security baseline**, which defines an accepted level of risk. These lists can be managed manually (e.g., via Windows Local Group Policy Editor) or obtained from security intelligence services like **Cisco Talos** or **The Spamhaus Project** and distributed to firewalls and other security systems.


# System-Based Sandboxing

**Sandboxing** is a technique that allows suspicious files to be executed and analyzed in a safe, isolated environment without risk to the host system. This is especially useful for understanding new or **polymorphic malware** that evades signature-based detection. By observing the malware's behavior (e.g., network connections, file changes), security teams can create new signatures and detection rules.

Security systems like Cisco AMP can automatically send suspicious files to a sandbox (e.g., Cisco Threat Grid) for analysis. The resulting intelligence is then used to block the threat and identify other infected systems.

Popular sandboxing tools include:

- **Cuckoo Sandbox:** A free, open-source sandbox for local analysis.
- **Online Sandboxes:** Public services like VirusTotal and **ANY.RUN** allow users to upload files for analysis. ANY.RUN provides highly detailed, interactive reports including screenshots, network activity, Indicators of Compromise (IOCs), and mapping to the MITRE ATT&CK framework.