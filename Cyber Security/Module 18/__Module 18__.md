[[18.1 Confidentiality]]
[[18.2 Obscuring Data]]
[[18.3 Integrity and Authenticity]]
[[18.4 Using Hashes]]
[[18.5 Public Key Cryptography]]
[[18.6 Authorities and the PKI Trust System]]
[[18.7 Applications and Impacts of Cryptography]]

---

### **Module 18: Cryptography and PKI - Exam Notes**

#### **1. The 4 Elements of Secure Communications**

| Element | What it Guarantees | How it's Achieved |
| :--- | :--- | :--- |
| **Confidentiality** | Only authorized users can read the data. | **Encryption** (AES, RSA) |
| **Integrity** | Data has not been altered. | **Hashing** (SHA-2, SHA-3) & **HMAC** |
| **Authentication**| The sender is who they claim to be. | **HMAC**, **Digital Signatures** |
| **Non-Repudiation** | The sender cannot deny sending the message. | **Digital Signatures** |

---
#### **2. Symmetric vs. Asymmetric Encryption**

| Feature | Symmetric Encryption | Asymmetric Encryption |
| :--- | :--- | :--- |
| **Keys** | **One single, shared key** for both encryption and decryption. | A **key pair**: a public key and a private key. |
| **Speed** | **Fast** and efficient. | **Slow** and computationally intensive. |
| **Best Use Case**| Encrypting **bulk data** (e.g., VPN traffic). | **Secure key exchange** and **digital signatures**. |
| **Algorithms**| **AES** (Secure), 3DES (Avoid), DES (Insecure/Legacy). | **RSA**, Diffie-Hellman (DH), ECC. |

---
#### **3. Practical Asymmetric Processes**

1.  **For Confidentiality (Secrecy):**
    *   Encrypt with the **recipient's PUBLIC key**.
    *   Decrypt with the **recipient's PRIVATE key**.

2.  **For Authentication (Digital Signature):**
    *   Sign (encrypt a hash) with the **sender's PRIVATE key**.
    *   Verify (decrypt the hash) with the **sender's PUBLIC key**.

---
#### **4. Diffie-Hellman (DH) Key Exchange**

*   **Purpose:** A special asymmetric algorithm used **only for secure key exchange**.
*   **How it Works:** Allows two parties to independently create an identical shared secret key over an insecure channel **without ever sending the key itself**.
*   **DH Groups:** Define the strength (bit length) of the key. Higher numbers are more secure (e.g., Group 14 = 2048-bit).

---
#### **5. Hashing, HMAC, and Salting**

*   **Hashing:**
    *   A **one-way function** that creates a unique, fixed-length "digital fingerprint" of data.
    *   **Purpose:** Verifies **integrity**.
    *   **Limitation:** Provides **NO authentication**; vulnerable to Man-in-the-Middle attacks.
    *   **Algorithms:** SHA-2 / SHA-3 (Secure), MD5 / SHA-1 (Insecure/Legacy).

*   **HMAC (Hash-based Message Authentication Code):**
    *   **How it Works:** `Hash(Message + a Secret Key)`
    *   **Purpose:** Solves hashing's limitation. Provides both **integrity AND authentication**. An attacker cannot create a valid HMAC without the secret key.

*   **Salting (for Passwords):**
    *   **Problem:** Simple hashing of passwords allows for pre-computation attacks (dictionary, rainbow tables).
    *   **Solution:** Add a unique, random string (**salt**) to each password **before** hashing. `Hash(Password + Salt)`.
    *   **Result:** Defeats pre-computation attacks by making every user's hash unique, even if they share the same password.

---
#### **6. Public Key Infrastructure (PKI)**

*   **Purpose:** A framework to manage and trust public keys at scale. It solves the problem of "How do I know this public key really belongs to you?"
*   **Key Components:**
    *   **Digital Certificate:** An electronic "ID card" (X.509 standard) that binds an identity to a public key.
    *   **Certificate Authority (CA):** A trusted third party that issues and signs digital certificates. Web browsers have a pre-installed list of trusted root CAs.
*   **Trust Models:**
    *   **Hierarchical:** A root CA signs certificates for intermediate CAs (most common model).
    *   **Cross-Certified:** A peer-to-peer "web of trust" between CAs.
*   **Certificate Revocation (How to invalidate a certificate):**
    *   **CRL (Certificate Revocation List):** An older method where the CA publishes a periodic list of bad certificates. (Slow, high latency).
    *   **OCSP (Online Certificate Status Protocol):** A modern method where a client makes a real-time query to check a single certificate's status. (Faster, better for privacy).

---
#### **7. Encryption's Impact on Security Monitoring**

*   **The "Encryption Blind Spot":** Widespread SSL/TLS encryption prevents firewalls and IPS from inspecting traffic content for threats.
*   **The Solution:** **SSL/TLS Decryption**. A dedicated appliance acts as a "man-in-the-middle" to decrypt traffic, send it to security devices for inspection, and then re-encrypt it.