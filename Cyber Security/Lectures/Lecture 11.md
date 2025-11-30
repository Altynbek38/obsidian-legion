---
tags: #cybersecurity #IAM #authentication #access_control #lecture_notes
deck: CyberSec_Course
topic: Authentication and Account Management
lecture: 11
---

# Lecture 11: Authentication and Account Management

## 1. The AAA Framework
The security process is a specific sequence of three steps:

1.  **[[Identification]] ("Who are you?")**
    *   The procedure of recognizing a subject by an identifier.
    *   *Examples*: Username, Email, Phone Number, Passport ID.
2.  **[[Authentication]] ("Prove it.")**
    *   The procedure of verifying the claimed identity.
    *   *The 3 Main Factors*:
        1.  **Knowledge** (What you know): Passwords, PINs, Patterns.
        2.  **Possession** (What you have): Smart cards, USB keys, Phones.
        3.  **Inherence** (What you are): [[Biometrics]] (Fingerprint, Retina, Face ID, Voice).
3.  **[[Authorization]] ("What can you do?")**
    *   Granting access to specific resources *after* successful authentication.
    *   *Examples*: Opening a locked door, accessing an inbox, transferring funds.

---

## 2. Identity and Access Management ([[IAM]])
IAM ensures the right users have access to the right resources.

### Role-Based Access Control ([[RBAC]])
*   Instead of assigning permissions to every individual user, permissions are assigned to **Roles** (e.g., "Admin", "User", "Auditor").
*   Users are then mapped to these roles.

### Best Practices
*   **Verify Sessions**: Prevent [[Session Hijacking]] by validating tokens.
*   **Continuous Check**: Perform access checks on *every* request, not just the initial login.
*   **Centralized Errors**: Centralize error handling logic to avoid leaking system info.
*   **Least Privilege**: Ensure only legitimate users can log in and access only what they need.

---

## 3. Attacks on Access Control
Attackers exploit human error or system flaws to bypass auth.

### Social Engineering
Manipulating humans to give up access.
*   **[[Phishing]]/Spoofing**: Sending fake emails (e.g., from a bank) to steal credentials.
*   **[[Pretexting]]**: Impersonating someone (e.g., IT support) and creating a scenario to ask for sensitive info.

### Technical Attacks
*   **Password Cracking/Mining**: Using dictionaries or brute-force tools to guess passwords.

---

## 4. Broken Access Control Types
When permissions are not enforced correctly, three types of breaches occur:

### A. Vertical Access Control (Privilege Escalation)
*   **Scenario**: A standard user accesses functions reserved for an Administrator.
*   *Direction*: Up the hierarchy (User $\to$ Admin).

### B. Horizontal Access Control
*   **Scenario**: A user accesses data belonging to another user with the *same* privilege level.
*   *Example*: User A changing a URL ID to view User B's profile.
*   *Direction*: Sideways (User A $\to$ User B).

### C. Context-Sensitive Access Control
*   **Scenario**: Bypassing business logic restrictions.
*   *Example*: A user completes a payment, then modifies the shopping cart contents *after* payment but before delivery to get free items.