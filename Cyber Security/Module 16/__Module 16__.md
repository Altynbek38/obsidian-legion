[[16.1 ZPF Overview]]
[[16.2 ZPF Operation]]
[[16.3 Configure a ZPF]]

---

### **Module 16: Zone-Based Policy Firewalls (ZPF) - Exam Notes**

#### **1. Core ZPF Concepts**

*   **ZPF:** The modern Cisco IOS firewall model. Policies are applied **between zones**, not on individual interfaces. It replaces the "Classic Firewall" (`ip inspect`) model.
*   **Zone:** A logical group of one or more interfaces with a similar security posture (e.g., INSIDE, OUTSIDE, DMZ).
*   **C3PL Framework (The 3 building blocks):**
    1.  **Class-Map:** **Identifies** the "interesting" traffic (e.g., `match protocol http`).
    2.  **Policy-Map:** Defines the **action** to take on that traffic (`inspect`, `drop`, `pass`).
    3.  **Service-Policy:** **Applies** the `policy-map` to a specific **zone-pair**.

*   **The Three Actions:**
    | Action | Description | Result |
    | :--- | :--- | :--- |
    | **`inspect`** | **Stateful inspection.** The most common and secure action. | Creates a session; **automatically allows return traffic**. |
    | **`drop`** | Explicitly denies the traffic. | Silently discards packets. This is the default action for the `class-default`. |
    | **`pass`** | **Stateless permit.** Forwards traffic in one direction only. | Does **not** track state or automatically allow return traffic. Rarely used. |

---
#### **2. The Golden Rules of ZPF Traffic Flow**

1.  Traffic between interfaces in the **SAME zone** is **PERMITTED** by default.
2.  Traffic between interfaces in **DIFFERENT zones** is **DROPPED** by default (unless a policy on a zone-pair explicitly permits it).
3.  Traffic to/from the **SELF-ZONE** (the router itself) is **PERMITTED** by default (unless a policy targeting the `self` zone explicitly blocks it).
4.  Traffic between a **zone member** and a **non-zone member** interface is **DROPPED**. This prevents traffic from "leaking" out of the firewall policy.

---
#### **3. ZPF Configuration Steps (The 5-Step Process)**

1.  **Create the Zones:**
    `zone security [ZONE-NAME]`
    *   *Example: `zone security INSIDE`, `zone security OUTSIDE`*

2.  **Define a Class-Map to identify traffic:**
    `class-map type inspect match-any [CLASS-NAME]`
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
#### **4. ZPF Verification Commands**

*   **`show policy-map type inspect zone-pair sessions`**: The most important command. Shows active stateful sessions, packet counters for matches, and drop statistics.
*   **`show zone-pair security`**: Shows the configured zone-pairs and which policies are applied to them.
*   **`show zone security`**: Shows the created zones and which interfaces are assigned to each one.
*   **`show class-map type inspect`**: Displays the configuration of the class-maps.
*   **`show policy-map type inspect`**: Displays the configuration of the policy-maps.