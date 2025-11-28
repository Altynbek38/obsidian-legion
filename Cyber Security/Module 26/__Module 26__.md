[[26.1 Risk Management]]
[[26.2 Risk Assessment]]
[[26.3 Security Controls]]
[[26.4. Risk Management and Security Controls Summary]]

---

### **Module 26: Risk Management & Security Controls - Exam Notes**

#### **1. Risk Management Basics**

*   **Definition of Risk:** The probability of loss due to a threat (malicious act or unexpected event).
*   **The Golden Rule:** The cost of a countermeasure (security control) should **NEVER** exceed the value of the asset being protected.
*   **Risk Levels:**
    *   **Negligence:** No action taken. High liability.
    *   **Due Care:** Taking reasonable steps to lower risk (Doing the right thing).
    *   **Due Diligence:** Continuous monitoring and verifying that the risks are managed (Doing it right).

---

#### **2. Risk Assessment Methodologies**

**Threat Sources:**
*   **Adversarial:** Hackers, Nation States, Insiders (Malicious intent).
*   **Accidental:** User error (No malice).
*   **Structural:** Hardware failure, software bugs.
*   **Environmental:** Fire, Flood, Earthquakes.

**Analysis Types:**

1.  **Quantitative Analysis (The Math):** Uses hard numbers and financial values.
    *   **Asset Value (AV):** What the asset is worth.
    *   **Exposure Factor (EF):** % of loss if a threat occurs.
    *   **SLE (Single Loss Expectancy):** Cost of *one* incident. (`AV x EF`)
    *   **ARO (Annualized Rate of Occurrence):** How many times per year it happens.
    *   **ALE (Annual Loss Expectancy):** Total yearly cost. **(`SLE x ARO`)**. *Used for budgeting.*

2.  **Qualitative Analysis (The Opinion):** Uses subjective ratings (High/Medium/Low).
    *   **Risk Matrix (Heat Map):** Plots **Likelihood** vs. **Impact**.

---

#### **3. Risk Response Strategies**

How an organization handles identified risks:

| Strategy | Action | Example |
| :--- | :--- | :--- |
| **Avoidance** | **Stop** the activity causing the risk. | Discontinuing a legacy service that cannot be secured. |
| **Reduction** | **Mitigate** the risk with controls. | Installing firewalls, patching, training staff. |
| **Sharing** | **Transfer** the risk to a 3rd party. | Buying **Insurance** or outsourcing to a vendor. |
| **Retention** | **Accept** the risk. | Acknowledging the risk and doing nothing (usually because the cost to fix is too high). |

---

#### **4. Security Controls (The "How")**

**Implementation Categories:**
*   **Administrative:** Policies, procedures, laws (Controls *People*).
*   **Technical:** Hardware, software, firewalls (Controls *Data/Systems*).
*   **Physical:** Fences, locks, guards, lighting (Controls *Access*).

**Functional Categories (The Goal):**

| Control Type | Function | Example |
| :--- | :--- | :--- |
| **Preventive** | Stops the attack **before** it happens. | Firewalls, Biometrics, Encryption. |
| **Deterrent** | **Discourages** the attacker psychologically. | Warning signs, visible cameras, lighting. |
| **Detective** | **Identifies** an active or past attack. | CCTV recording, Log analysis, IDS. |
| **Corrective** | **Restores** systems after an attack. | Antivirus (cleaning), Backups (restoring). |
| **Compensative** | **Substitute** for a primary control. | Using a guarded gate because a fence is broken. |