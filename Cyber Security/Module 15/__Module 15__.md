[[15.1 Secure Networks with Firewalls]]
[[15.2 Firewalls in Network Design]]

---

### **Module 15: Firewall Technologies - Exam Notes**

#### **1. Firewall Fundamentals & Types**

*   **Firewall:** A system that enforces an access control policy between networks. Acts as a chokepoint.
*   **Defense in Depth:** The strategy of using multiple, overlapping security layers. A firewall is just one layer.
*   **Firewall Limitations:** Cannot stop insider threats, rogue APs, or traffic they can't inspect (e.g., encrypted traffic).

**Comparison of Firewall Types:**

| Firewall Type | Key Feature | OSI Layers |
| :--- | :--- | :--- |
| **Stateless (Packet Filtering)** | No memory of connections; inspects each packet in isolation. (Think: ACLs) | **L3 / L4** |
| **Stateful** | **Most common type.** Tracks active connections in a **state table**. Allows return traffic automatically. | **L3 / L4 / L5** |
| **Application Gateway (Proxy)**| Acts as an intermediary; client connects to proxy, proxy connects to server. | Up to **L7** |
| **Next-Gen (NGFW)** | Stateful firewall + integrated services like **IPS** and **Application Control**. | Up to **L7** |

---
#### **2. Common Firewall Architectures**

| Architecture | Description | Core Rules |
| :--- | :--- | :--- |
| **Private / Public** | The classic 2-interface model separating a trusted "inside" from an untrusted "outside." | • Inside -> Outside = Allowed.<br> • Outside -> Inside = Blocked. |
| **DMZ (Demilitarized Zone)**| A 3-interface model creating a "buffer zone" for public-facing servers (web, email, DNS). | • Public can access DMZ.<br> • Public cannot access Inside.<br> • **CRITICAL:** **DMZ cannot initiate connections to Inside.** |

---
#### **3. Zone-Based Policy Firewall (ZPF) - Core Concepts**

*   **ZPF:** The modern Cisco IOS firewall model. Policies are applied **between zones**, not on individual interfaces.
*   **Zone:** A logical group of one or more interfaces with a similar security posture.
*   **C3PL Framework (The 3 building blocks):**
    1.  **Class-Map:** **Identifies** the traffic (e.g., `match protocol http`).
    2.  **Policy-Map:** Defines the **action** for that traffic (`inspect`, `drop`, `pass`).
    3.  **Service-Policy:** **Applies** the `policy-map` to a `zone-pair`.

*   **The Three Actions:**
    | Action | Description | Result |
    | :--- | :--- | :--- |
    | **`inspect`** | **Stateful inspection.** | Creates a session; **automatically allows return traffic**. |
    | **`drop`** | Denies the traffic. | Silently discards packets. |
    | **`pass`** | **Stateless permit.** | Allows traffic in one direction only; does **not** allow return traffic. |

---
#### **4. ZPF - The Golden Rules of Traffic Flow**

1.  Traffic between interfaces in the **SAME zone** is **PERMITTED** by default.
2.  Traffic between interfaces in **DIFFERENT zones** is **DROPPED** by default (unless a policy explicitly permits it).
3.  Traffic to/from the **SELF-ZONE** (the router itself) is **PERMITTED** by default (unless a policy explicitly blocks it).
4.  Traffic between a **zone member** and a **non-zone member** interface is **DROPPED**.

---
#### **5. ZPF Configuration Steps (The 5-Step Process)**

1.  **Create the Zones:**
    `zone security [ZONE-NAME]`
    *   *Example: `zone security INSIDE`, `zone security OUTSIDE`*

2.  **Define a Class-Map to identify traffic:**
    `class-map type inspect [CLASS-NAME]`
    `match protocol [protocol]`
    *   *Example: `class-map type inspect HTTP-CLASS`, `match protocol http`*

3.  **Define a Policy-Map to set the action:**
    `policy-map type inspect [POLICY-NAME]`
    `class type inspect [CLASS-NAME]`
    `inspect` (or `drop` / `pass`)
    *   *Example: `policy-map type inspect IN-TO-OUT-POLICY`, `class type inspect HTTP-CLASS`, `inspect`*

4.  **Create a Zone-Pair and Apply the Policy:**
    `zone-pair security [PAIR-NAME] source [SOURCE-ZONE] destination [DEST-ZONE]`
    `service-policy type inspect [POLICY-NAME]`
    *   *Example: `zone-pair security IN-OUT-PAIR source INSIDE destination OUTSIDE`, `service-policy type inspect IN-TO-OUT-POLICY`*

5.  **Assign Interfaces to Zones:**
    `interface [interface-name]`
    `zone-member security [ZONE-NAME]`
    *   *Example: `interface g0/0/1`, `zone-member security INSIDE`*

---
#### **6. ZPF Verification**

*   **`show policy-map type inspect zone-pair sessions`**: The most useful command. Shows active sessions, packet counters for matches, and drops.
*   **`show zone-pair security`**: Shows the configured zone-pairs and their applied policies.
*   **`show zone security`**: Shows the zones and which interfaces are assigned to them.