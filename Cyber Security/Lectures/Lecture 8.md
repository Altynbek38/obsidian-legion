---
tags: #cybersecurity #wireless_security #wifi #networking #lecture_notes
deck: CyberSec_Course
topic: Wireless Network Security
lecture: 8
---

# Lecture 8: Wireless Network Security

## 1. General Security Philosophy
There is no "absolute protection." The goal of wireless security is to make the attack **unprofitable** (where the effort required exceeds the value of the result).

Defensive technologies fall into two categories:
1.  **Direct Protection**: Encryption, MAC filtering.
2.  **Indirect Protection**: Technologies designed for speed that also hinder attackers (e.g., Wi-Fi 6 features).

---

## 2. Basic Defense Mechanisms

### A. SSID Hiding
*   **Method**: Stop broadcasting the Network Name ([[SSID]]).
*   **Reality**: This is "Security by Obscurity." It does not hide the network traffic or the **BSSID** (hardware ID), which scanners can still detect. It only stops casual users, not determined attackers.

### B. MAC Filtering
*   **Method**: Using an Access Control List (ACL) to allow specific devices based on their physical address.
*   **Weakness**: Susceptible to **[[MAC Spoofing]]** (attackers copying a legitimate MAC address).
*   **Best Practice**: Use mainly for internal perimeters or combine with a separate **Guest Network** for visitors.

### C. Encryption Evolution
*   **WEP**: Deprecated and highly insecure.
*   **WPA2-PSK (Pre-Shared Key)**: Uses a single password for everyone. Risky; if one device is compromised, the whole network is at risk.
*   **WPA2-Enterprise**: The corporate standard. Uses **dynamic keys** for each user and an authentication server (usually [[RADIUS]]).
*   **[[Enhanced Open]]**: A protocol for open networks (like coffee shops) that provides encryption without requiring a password, protecting against passive eavesdropping.

---

## 3. Physical & Architectural Security

### Signal Containment (Coverage)
*   **Old Approach**: One high-power Access Point (AP) in the center.
    *   *Risk*: Signal "bleeds" outside the building, allowing attackers to sniff traffic from the parking lot.
*   **Secure Approach**: Many lower-power APs distributed throughout.
    *   *Benefit*: Keeps the signal contained within the physical perimeter.

### Roaming & Steering
*   **Client Steering**: Forces devices to switch to the strongest signal and prioritizes the **5GHz** band (which has shorter range but higher speed) over 2.4GHz.
*   **Seamless Roaming**: Allows devices to switch APs instantly without dropping the connection.

---

## 4. Threats: Rogue Access Points
*   **[[Rogue AP]]**: An unauthorized access point set up by an attacker (often called an "Evil Twin").
*   **Goal**: To lure users into connecting to it to perform [[Man-in-the-Middle]] attacks and steal credentials.
*   **Defense**: Corporate APs often have "Radio Scanning" features to detect and alert admins about rogue devices nearby.

---

## 5. Wi-Fi 6 (802.11ax)
The newest standard improving speed and security.

*   **Performance**: Speeds up to ~11 Gb/s.
*   **Security Implication**: The high speed allows for heavy security layers (like always-on [[VPN]]s) without noticeable lag for the user.
*   **Key Technologies**:
    *   **[[BSS Coloring]]**: "Tags" packets so APs ignore traffic from neighboring networks (reduces interference and "alien" traffic processing).
    *   **[[OFDMA]]**: Allows multiple signals to be sent simultaneously on one channel. Improves efficiency and security through better channel utilization.