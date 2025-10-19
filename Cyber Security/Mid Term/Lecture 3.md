
### **Lecture 3: Web & Network Attacks - Key Notes**

#### **Part 1: Denial of Service (DoS) & Distributed Denial of Service (DDoS) Attacks**

*   **Denial of Service (DoS):** An attack designed to make a system or service **unavailable** to legitimate users. It prevents them from accessing resources.

*   **Distributed Denial of Service (DDoS):** A more powerful type of DoS attack where the attack traffic comes from **many different sources** simultaneously.
    *   This makes it much harder to block because there isn't a single attacker to stop.

*   **How DDoS Attacks Work (The Role of Botnets):**
    1.  **Botnet:** A network of compromised computers or IoT devices (called "bots" or "zombies") that are controlled by a single attacker via a Command and Control (C&C) center.
    2.  **The Attack:** The attacker commands the entire botnet to send massive amounts of traffic or requests to a single target (e.g., a website or server).
    3.  **The Result:** The target is overwhelmed by the flood of traffic and either crashes or becomes too slow to serve legitimate users.

*   **Consequences of a DDoS Attack:**
    *   **Financial Loss:** The service is down, so no business can be done.
    *   **Loss of Reputation:** Customers lose trust in the service's reliability.
    *   **Data Loss:** Can sometimes be a side effect or a distraction for another type of attack.

---

#### **Part 2: Main Types of DDoS Attacks (Categorized by Network Layer)**

DDoS attacks can target different layers of the network model.

##### **1. Application Layer (L7) Attacks**
*   **Goal:** To exhaust the resources of the application itself (e.g., the web server). These attacks often mimic legitimate user traffic, making them hard to detect.
*   **Types:**
    *   **HTTP Flood:** Flooding the server with a huge number of HTTP GET or POST requests, forcing it to process them all and run out of resources.
    *   **HTTPS Flood:** Similar to an HTTP flood, but uses encrypted (SSL/TLS) traffic, which is even more resource-intensive for the server to handle and harder for security tools to inspect.
    *   **"Slow and Low" Attacks:** These are clever, low-volume attacks that are very effective.
        *   **SlowLoris:** An attacker opens many connections to a web server but keeps them open by sending incomplete requests very slowly. This ties up all the server's connection slots, so no one else can connect.
        *   **RUDY (Are You Dead Yet?):** An attack that targets web forms. It sends POST requests but submits the data extremely slowly, one byte at a time, to keep the connection open and exhaust server resources.

##### **2. Transport Layer (L4) Attacks**
*   **Goal:** To exhaust the connection state tables of servers, firewalls, and load balancers.
*   **Type:**
    *   **SYN Flood:** This attack exploits the TCP "three-way handshake" (SYN, SYN-ACK, ACK).
        1.  The attacker sends a huge number of SYN packets (the first step of a connection) to the server, often from fake IP addresses.
        2.  The server responds with a SYN-ACK for each one and waits for the final ACK.
        3.  The attacker never sends the final ACK, leaving the server with many "half-open" connections. This fills up the server's connection table, and it can't accept any new, legitimate connections.

##### **3. Network Layer (L3) Attacks**
*   **Goal:** To consume all the available network bandwidth, creating a traffic jam so that legitimate traffic cannot get through. These are also known as "volumetric" attacks.
*   **Types:**
    *   **UDP Flood:** Flooding the target with a large volume of User Datagram Protocol (UDP) packets. The server tries to process them all, gets overwhelmed, and can't respond to legitimate traffic.
    *   **ICMP Flood (Ping Flood):** Overwhelming the target with ICMP Echo Request packets (pings). The server's network gets saturated trying to respond to every ping.

---

#### **Part 3: DNS Flood Attacks**

*   **What is DNS?** The Domain Name System (DNS) is the "phone book of the internet." It translates human-readable domain names (like `www.google.com`) into machine-readable IP addresses.
*   **The Attack:** A DNS Flood sends a massive number of DNS queries to a domain's DNS server.
*   **The Result:** The DNS server gets overwhelmed and cannot respond to legitimate queries. If the phone book is unavailable, users can't find the IP address for the website, so they can't access it, even if the website's server is working perfectly fine.

***
**Key Takeaway for Your Midterm:**
DDoS is a major cybercrime focused on making services **unavailable**. Attacks can be either **volumetric** (brute-force traffic floods like UDP/ICMP floods) or **application-focused** (smarter, subtle attacks like SlowLoris or HTTP floods) that target specific software weaknesses.