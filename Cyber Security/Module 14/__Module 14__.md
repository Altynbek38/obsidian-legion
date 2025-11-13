[[14.1 Introduction to Access Control Lists]]
[[14.2 Wildcard Masking]]
[[14.3 Configure ACLs]]
[[14.4 Named Standard IPv4 ACL Syntax]]
[[14.5 Implement ACLs]]
[[14.6 Mitigate Attacks with ACLs]]
[[14.7 IPv6 ACLs]]

---

### **Module 14: Access Control Lists (ACLs) - Exam Notes**

#### **1. Core ACL Concepts**

*   **ACL:** A sequence of `permit` or `deny` statements (ACEs) that filter network traffic.
*   **Packet Filtering:** The process of inspecting packet headers and deciding to forward or drop them based on ACL rules.
*   **Processing Logic:**
    *   Processed **sequentially** from top to bottom.
    *   Once a packet matches a rule, the action is taken and **no more rules are checked**.
*   **Implicit Deny:** Every ACL ends with an invisible `deny any` statement. If a packet doesn't match any rule, it is dropped.
    *   **Golden Rule:** An ACL must have at least one `permit` statement to allow any traffic.

---
#### **2. Inbound vs. Outbound ACLs**

| Direction | When it's Processed | Best Use Case |
| :--- | :--- | :--- |
| **Inbound** | As packets **enter** an interface, **before** routing. | More efficient; drops unwanted traffic early, saving CPU. |
| **Outbound** | As packets **exit** an interface, **after** routing. | Filtering traffic from multiple sources that leave through one interface. |

---
#### **3. ACL Types: Standard vs. Extended**

| Feature | Standard ACL | Extended ACL |
| :--- | :--- | :--- |
| **Filtering Criteria** | **Source IPv4 Address ONLY** | Source/Destination IP, Protocol (TCP/UDP), Port numbers. |
| **Numbered Range** | 1-99, 1300-1999 | 100-199, 2000-2699 |
| **Control Level** | Basic, less granular. | Very specific and granular. |

---
#### **4. Wildcard Masks**

*   **Purpose:** To specify which bits of an IP address to check. It's the **inverse** of a subnet mask.
*   **The Rules:**
    *   `0` = **Match** the corresponding bit.
    *   `1` = **Ignore** the corresponding bit.
*   **Shortcut Calculation:** `255.255.255.255 - [Subnet Mask] = [Wildcard Mask]`
*   **Keywords (Essential):**
    *   `host [ip_address]`: Replaces `[ip_address] 0.0.0.0`. Matches a single host.
    *   `any`: Replaces `0.0.0.0 255.255.255.255`. Matches any IP address.

---
#### **5. Configuration: Numbered vs. Named ACLs**

| Method | Description | Key Advantage |
| :--- | :--- | :--- |
| **Numbered** | The old method. Uses a number to identify the ACL. | Simple for very basic lists. |
| **Named** | **Preferred Method.** Uses a descriptive name. Enters a sub-configuration mode. | **Allows editing**: You can delete and insert individual lines (ACEs) using sequence numbers. |

---
#### **6. Key Configuration & Verification Commands**

*   **Create Numbered ACL:**
    `R1(config)# access-list [number] {permit | deny} ...`
*   **Create Named ACL:**
    `R1(config)# ip access-list {standard | extended} [NAME]`
*   **Apply to Interface:**
    `R1(config-if)# ip access-group [number | NAME] {in | out}`
*   **Apply to VTY Lines (Telnet/SSH):**
    `R1(config-line)# access-class [number | NAME] in`
*   **Verify Configuration:**
    `show access-lists` (Shows rules with sequence numbers and hit counters)
    `show running-config | section access-list`
*   **Modify Named ACL:**
    1.  `R1(config)# ip access-list extended [NAME]`
    2.  `R1(config-ext-nacl)# no [sequence_number]` (to delete)
    3.  `R1(config-ext-nacl)# [sequence_number] permit ...` (to insert)

---
#### **7. Best Practices & "The Golden Rules"**

1.  **Rule Order:** Place **most specific** rules at the top of the list, and **most general** rules at the bottom.
2.  **`established` Keyword (for Extended ACLs):** A basic stateful firewall feature. Permits return TCP traffic for connections initiated from inside your network. Crucial for security.
    `permit tcp any any established`
3.  **Placement Strategy (CRITICAL):**
    *   **Standard ACLs:** Place as close to the **DESTINATION** as possible.
        *   *Reason:* To avoid accidentally filtering traffic to other legitimate destinations.
    *   **Extended ACLs:** Place as close to the **SOURCE** as possible.
        *   *Reason:* To drop unwanted traffic early and save network bandwidth.

---
#### **8. IPv6 ACLs**

*   **Named Only:** There are no numbered IPv6 ACLs.
*   **No Wildcard Masks:** Use prefix-length (e.g., `/64`) instead.
*   **Application Command:** `ipv6 traffic-filter [NAME] {in | out}`
*   **Implicit Rules:**
    *   `deny ipv6 any any` (Same as IPv4).
    *   **`permit icmp any any nd-na`** (Neighbor Advertisement).
    *   **`permit icmp any any nd-ns`** (Neighbor Solicitation).
    *   **Important:** These two implicit permits are required for IPv6 Neighbor Discovery (like ARP) to work. Do not block them unless you have a specific reason.