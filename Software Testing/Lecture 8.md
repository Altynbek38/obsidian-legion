
***

# Lecture 8: Client-Server Architecture & API Testing
#SoftwareTesting #Architecture #API #OSIModel #REST #SOAP #ExamPrep

## 1. Client-Server Architecture
A computing model where the **Server** hosts, delivers, and manages resources, and the **Client** requests them.
*   **Key Characteristics:** Centralized control, easy resource sharing, scalable.

### Definitions
*   **User:** The person interacting with the software.
*   **Client:** Software/Device that initiates requests (e.g., Browser, Mobile App).
*   **Server:** Specialized hardware/software that provides services/resources (e.g., Database, Web Server).

### Architecture Types
*   **1-Tier (Monolith):** User Interface, Business Logic, and Database all on a single device (e.g., MS Office installed on a PC).
*   **2-Tier:** Logic split into two.
    *   *Fat Client / Thin Server:* Logic stored on the client.
    *   *Thin Client / Fat Server:* Logic handled by the server.
*   **3-Tier:** Logic split into three layers:
    1.  **Presentation Layer** (Client/UI).
    2.  **Application Layer** (Business Logic).
    3.  **Database Layer** (Data Storage).
*   **Peer-to-Peer (P2P):** Decentralized. Each node acts as both client and server (e.g., BitTorrent, Blockchain). Robust but harder to manage.

## 2. Modern Web Architecture Components
*   **DNS:** Translates domain names to IP addresses.
*   **Load Balancer:** Distributes traffic across servers.
*   **CDN (Content Delivery Network):** Delivers static content fast based on user location.
*   **Web App Servers:** Handles logic/requests.
*   **Database:** Stores data.

## 3. The OSI Model (7 Layers of Communication)
Standard model for network communication. **"Please Do Not Throw Sausage Pizza Away"** (Physical to Application).

| # | Layer | Function | Protocols/Devices |
| :--- | :--- | :--- | :--- |
| **7** | **Application** | User interface; interacts with software. | HTTP, DNS, FTP, SMTP |
| **6** | **Presentation** | Data translation, encryption, compression. | SSL, IMAP, JPEG |
| **5** | **Session** | Establishes, manages, and terminates connections. | API's, Sockets |
| **4** | **Transport** | End-to-end reliability, error checking, flow control. | **TCP**, **UDP** |
| **3** | **Network** | Routing and forwarding data packets (IP Addressing). | **IP**, ICMP, Routers |
| **2** | **Data Link** | Reliable transmission between connected nodes (MAC). | Ethernet, Switch, Bridge |
| **1** | **Physical** | Physical connection and transmission of raw bits. | Cables, Hubs, Wi-Fi |

## 4. API (Application Programming Interface)
A set of rules allowing different software entities to communicate.
*   **Role:** Acts as a messenger that takes a request from the client, tells the server what to do, and delivers the response.

### SOAP vs. REST
Two major API architectural styles.

| Feature | **SOAP (Simple Object Access Protocol)** | **REST (Representational State Transfer)** |
| :--- | :--- | :--- |
| **Type** | A **Protocol**. | An **Architectural Pattern**. |
| **Format** | Only uses **XML**. | Uses **JSON** (most common), XML, HTML, Plain text. |
| **Flexibility** | Rigid, strict standards. | Flexible, lightweight. |
| **Usage** | Enterprise apps, high security needs. | Web services, mobile apps, public APIs. |
| **Market Share**| ~22% | ~69% |

## 5. Benefits of API Testing
Testing at the API level (Integration layer) allows for:
*   **Earlier Validation:** Find bugs before the UI is built.
*   **Faster Resolution:** Easier to pinpoint the root cause than in UI testing.
*   **Speed:** API tests run much faster than GUI tests.
*   **Security:** Verify data access controls directly.