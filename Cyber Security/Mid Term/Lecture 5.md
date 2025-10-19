
### **Lecture 5: Database Security - Key Notes**

#### **Part 1: Why Database Security is Critical**

*   **Core Function:** Databases are the primary way companies store their most valuable information (customer data, financial records, intellectual property).
*   **Primary Threat:** The biggest risk is **Information Leakage**, where sensitive, protected, or confidential data is released to an untrusted environment. A data breach is a type of information leakage.

---

#### **Part 2: The Most Common Database Vulnerabilities (The Problems)**

Most security incidents are caused by poor maintenance and common, preventable mistakes.

1.  **Excessive Permissions (Privilege Abuse):**
    *   **Problem:** Users or applications are given more access rights than they need to do their job (e.g., a simple user account that has administrator-level powers).
    *   **Principle to Follow:** The **Principle of Least Privilege** – only grant the absolute minimum permissions required.

2.  **Injection Attacks (SQL Injection is the most famous):**
    *   **Problem:** This is a major and very common attack. An attacker inserts malicious code (like SQL commands) into a data input field (like a search bar or login form).
    *   **Result:** The database is tricked into running the attacker's malicious command, which can be used to steal, delete, or modify all the data in the database.

3.  **Weak Protection of Data Carriers (Lack of Encryption):**
    *   **Problem:** The data itself is not protected.
    *   **Two States of Data:**
        *   **Data at Rest:** Data stored on a hard drive or in a backup. If the physical drive is stolen, the data can be read easily if not encrypted.
        *   **Data in Transit:** Data moving over a network. If not encrypted, it can be intercepted and read by an attacker ("eavesdropping").

4.  **Outdated Software & Poor Configuration:**
    *   **Problem:** Running old, unpatched versions of the database management system (DBMS) or using default, insecure configurations.
    *   **Why it's bad:** Old software has well-known vulnerabilities that hackers have created automated tools to find and exploit. Default settings often include default admin passwords (like "admin/admin").

5.  **Weak Authentication:**
    *   **Problem:** Using weak, default, or easily guessable passwords for database accounts.

---

#### **Part 3: Methods of Database Protection (The Solutions)**

A good defense is comprehensive and targets the known vulnerabilities.

1.  **Encryption:**
    *   **Solution for:** Weak Protection of Data.
    *   **Action:** Encrypt sensitive data both **at rest** (on the disk) and **in transit** (across the network). This makes the data unreadable even if it is stolen or intercepted.

2.  **Strong Access Control:**
    *   **Solution for:** Excessive Permissions.
    *   **Action:** Enforce the **Principle of Least Privilege**. Differentiate access rights so that users can only access the specific data they are authorized to see.

3.  **Strong Authentication & Password Management:**
    *   **Solution for:** Weak Authentication.
    *   **Action:** Enforce strong password policies. Do not use default or shared accounts.

4.  **Regular Auditing and Monitoring:**
    *   **Solution for:** Undetected malicious activity.
    *   **Action:** Keep detailed logs of who accessed the database, what they did, and when. Regularly review these logs for suspicious activity.

5.  **Keep Software Updated:**
    *   **Solution for:** Outdated Software.
    *   **Action:** Regularly apply security patches and updates to the database software and the server's operating system.

---

#### **Part 4: Database Security Testing (How We Check Our Defenses)**

Testing is mandatory to ensure that security controls are actually working.

*   **Types of Testing:**
    1.  **Vulnerability Scanning:** Using automated tools to scan the database for known vulnerabilities, missing patches, and weak configurations.
    2.  **Penetration Testing:** A simulated "ethical hack" where a security professional actively tries to break into the database to find vulnerabilities that an automated scanner might miss.
    3.  **Security Audit:** A systematic review of security configurations, access controls, and user permissions to ensure they comply with company policy and security best practices.
    4.  **Risk Assessment:** Identifying the most critical data and the most likely threats to that data, in order to prioritize security efforts.

***
**Key Takeaway for Your Midterm:**
1.  **SQL Injection** is one of the most dangerous and common database attacks.
2.  Always follow the **Principle of Least Privilege**.
3.  **Encrypt** sensitive data both at rest and in transit.
4.  **Patch and update** your database software regularly to protect against known vulnerabilities.