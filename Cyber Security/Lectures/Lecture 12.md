---
tags: #cybersecurity #risk_management #access_control #mitigation #lecture_notes
deck: CyberSec_Course
topic: Access Management & Risk Mitigation
lecture: 12
---

# Lecture 12: Access Management & Risk Mitigation

## 1. The Risk Management Process
Risk management is the foundational element of security architecture. It follows a specific flow:

`[[Assets]] -> [[Vulnerabilities]] -> [[Threats]] -> [[Risks]] -> Controls`

### Key Definitions
*   **[[Asset]]**: Anything of value. Includes **Personnel**, **Facilities**, **Processes**, and **Information**.
*   **[[Vulnerability]]**: A weakness in the **Confidentiality**, **Integrity**, or **Availability** (CIA) of an asset.
*   **[[Threat]]**: The potential for a vulnerability to be exploited (can be Natural, Man-made, Accidental, or Deliberate).
*   **[[Risk]]**: The intersection of assets, threats, and vulnerabilities.

> **Challenges**: Risks are often mismanaged by **underestimating** the vulnerability or simply **missing** a threat scenario entirely.

---

## 2. Risk Analysis & Treatment 
We analyze risk based on **Probability** vs. **Impact** (High/Medium/Low).

### The 4 Risk Treatment Strategies
Once a risk is identified, you must decide how to handle it:
1.  **Avoid**: Discontinue the activity that causes the risk.
2.  **Mitigate**: Implement controls to reduce probability or impact.
3.  **Share (Transfer)**: Move the risk to a third party (e.g., Insurance).
4.  **Retain (Accept)**: Accept the risk as it falls within appetite.

---

## 3. Cybersecurity Controls
Controls are the tactics used to mitigate risk. They generally serve four purposes:
1.  Reduce Probability.
2.  Reduce Impact.
3.  Detect Occurrences.
4.  Collect Evidence.

### Types of Controls
| Control Type | Function | Strength | Cost/Impact |
| :--- | :--- | :--- | :--- |
| **Preventive** | **Block** incidents before they happen. | Good at blocking. | High operational impact & implementation cost. |
| **Detective** | **Alert** on incidents as they happen. | Good at detecting. | High cost to operate (monitoring). |
| **Forensic** | Document incidents for analysis. | Good for investigation. | Medium cost. |
| **Audit** | Collect evidence of activity. | Good for compliance. | Low cost, but often **neglected**. |

---

## 4. Best Practices for Access Control
To reduce the risk of unauthorized access and data compromise, implement these 8 practices:

1.  **[[Principle of Least Privilege]]**: Users only get the access necessary for their job.
2.  **Strong Password Policy**: Enforce complexity and rotation.
3.  **[[MFA]] (Multi-Factor Authentication)**: Require more than just a password.
4.  **Monitor Activity**: Log user actions to detect anomalies.
5.  **Secure Infrastructure**: Harden the underlying IT systems.
6.  **[[UBA]] (User Behavior Analytics)**: Use analytics to find suspicious behavior patterns.
7.  **Prompt Response**: React immediately to security alerts.
8.  **Security Awareness Training**: Educate users to reduce human error.