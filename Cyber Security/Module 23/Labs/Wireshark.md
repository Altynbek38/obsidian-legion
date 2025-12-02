
***

# Lab: Wireshark Traffic Analysis (Telnet vs. SSH)

**Objective:** Capture and compare unencrypted (Telnet) and encrypted (SSH) network traffic to understand security implications.

### 1. Wireshark Setup
*   **Launch:** Run with privileges to enable promiscuous mode:
    ```bash
    sudo wireshark
    ```
*   **Interface:** Select **Any** or **Loopback (lo)** (since traffic is local).
*   **Action:** Start Capture.

### 2. Telnet Analysis (Unencrypted)
*   **Generate Traffic:**
    ```bash
    telnet localhost
    # Login: cisco / Password: password
    ```
*   **Wireshark Filter:** `telnet`
*   **Inspection:**
    *   Use **Edit > Find Packet** $\rightarrow$ Search **String** for "login".
    *   Inspect the **Packet Details** (Telnet Data field).
    *   Follow the stream or arrow down through packets.
*   **Observation:** The username (`cisco`) and password (`password`) are sent in **Plain Text**. You can read every character captured in the TCP payload.

### 3. SSH Analysis (Encrypted)
*   **Generate Traffic:**
    ```bash
    ssh localhost
    # Login: cisco / Password: password
    ```
*   **Wireshark Filter:** `ssh`
*   **Inspection:**
    *   Select any packet with protocol **SSHv2**.
    *   Expand the **SSH Protocol** field in Packet Details.
*   **Observation:** The payload is marked as **"Encrypted packet"**. The data is obfuscated, and credentials cannot be read.

### Key Takeaway
*   **Telnet:** Sends data in clear text (Insecure).
*   **SSH:** Encrypts the entire session, including authentication (Secure).