
### **Lecture 4: Wireless & Cloud Security - Key Notes**

#### **Part 1: Fundamentals of Wireless (Wi-Fi) Security**

*   **The Core Principle:** Since absolute security is impossible, the main goal is to make an attack as difficult and costly for the attacker as possible.

*   **Two Main Categories of Security Measures:**
    1.  **Direct Protection:** Technologies specifically designed for security (e.g., encryption, MAC filtering).
    2.  **Indirect Protection:** Technologies designed for performance that also happen to improve security (e.g., Wi-Fi 6 speed improvements).

#### **Part 2: Basic Wi-Fi Security Techniques**

1.  **Hiding the SSID (Network Name):**
    *   **What it does:** Stops your Wi-Fi network name from being publicly broadcasted. To connect, you must know the exact name, password, and encryption type.
    *   **Limitation:** This is **security by obscurity**. It doesn't truly hide the network. The **BSSID** (the access point's hardware address) is still broadcast, and scanners can still detect the network. It's a minor deterrent, not real security.

2.  **MAC Address Filtering:**
    *   **What it does:** Creates an "allow list" (or "block list") of devices based on their unique Media Access Control (MAC) address. Only devices on the allow list can connect to the network.
    *   **Limitation:** A determined attacker can easily **spoof** (impersonate) the MAC address of an allowed device. This is best used for an internal network and is not a strong primary defense.

3.  **Rogue AP Hunting:**
    *   **Rogue Access Point (AP):** An unauthorized access point connected to a network, often set up by an attacker to create an "evil twin" network. Unsuspecting users connect to it, allowing the attacker to steal passwords and other data.
    *   **Defense:** Many modern network systems have built-in radio scanning to detect and block unauthorized rogue APs.

#### **Part 3: Wi-Fi Encryption Protocols (CRITICAL KNOWLEDGE)**

This is the most important part of Wi-Fi security. It's the evolution of how we scramble wireless traffic to prevent eavesdropping.

*   **WEP (Wired Equivalent Privacy):**
    *   **Status:** Obsolete and **highly insecure**. It can be cracked in minutes. **NEVER use it.**
    *   It was the first attempt at Wi-Fi security but had major cryptographic flaws.

*   **WPA (Wi-Fi Protected Access):**
    *   **Status:** Outdated and also considered insecure.
    *   It was an improvement over WEP but has known vulnerabilities. Avoid if possible.

*   **WPA2 (Wi-Fi Protected Access 2):**
    *   **Status:** The **current minimum standard** for security. It is strong and widely used.
    *   **Two Main Versions:**
        *   **WPA2-PSK (Pre-Shared Key) / Personal:** Uses a single password for all users. Easy to set up, making it common for homes and small businesses. **Weakness:** If the password is leaked, the entire network is compromised.
        *   **WPA2-Enterprise:** **Much more secure**. Each user has their own unique login credentials (username and password), managed by a central server (like RADIUS). Used in corporate environments.

*   **WPA3 (Wi-Fi Protected Access 3):**
    *   **Status:** The **latest and most secure** standard.
    *   It offers stronger encryption and protection against common attacks, even if a user has a weak password. It is backward-compatible with WPA2.

#### **Part 4: Modern Wi-Fi Technologies & Security Enhancements**

*   **Network Design for Security:**
    *   Instead of one powerful AP in the center, use **multiple, lower-power APs** distributed throughout the area.
    *   **Benefit:** This contains the Wi-Fi signal within your building's perimeter, making it much harder for an attacker in the parking lot to eavesdrop on your traffic.

*   **Seamless Roaming:**
    *   Allows mobile devices to automatically and smoothly switch between the strongest APs as a user moves around, ensuring a constant, stable connection.

*   **Wi-Fi 6 (802.11ax):**
    *   **Primary Goal:** Higher speed and efficiency, especially in environments with many connected devices (like smart homes).
    *   **Security Benefit:** The higher speed makes it easier to implement strong security measures, like a separate VPN for each user, without a significant performance drop.
    *   It uses technologies like **OFDMA** to manage traffic more efficiently, which also improves security.

***
**Key Takeaway for Your Midterm:**
1.  **Always use WPA2 or WPA3 encryption.** Never use WEP or WPA.
2.  **WPA2-Enterprise** is far more secure than WPA2-Personal (PSK) because it uses individual logins.
3.  Basic techniques like hiding the SSID and MAC filtering are weak defenses and should not be relied upon as your primary security. Strong encryption is the key.
4.  Good network design (using multiple, low-power APs) can physically contain your wireless signal, making it harder for outsiders to attack.