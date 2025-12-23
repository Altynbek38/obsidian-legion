
***

# Lecture 9: Specifics of Web Application Testing
#WebTesting #QualityAttributes #ClientServer #ExamPrep

## 1. Web Application Overview
*   **Definition:** Software that utilizes web browsers and technologies to perform tasks over the Internet.
*   **Architecture:** Follows a **Client-Server** model.
*   **Testing Scope:** Must verify three components:
    1.  **Client** (Front-end/Browser).
    2.  **Server** (Back-end/Database).
    3.  **Communication** (API).

## 2. Product Quality Priorities
Testing activities are prioritized based on the impact on quality:

| Priority | Focus Area | Description |
| :--- | :--- | :--- |
| **I Priority** | **Functional Testing** | Verifies software meets requirements and performs intended tasks correctly. |
| **II Priority** | **Non-Functional Testing** | Performance, Compatibility, Usability, Reliability, Security, Maintainability, Portability. |
| **III Priority** | **Exploratory Testing** | Personal experience-based testing, comparing with similar applications. |

---

## 3. Testing Types Breakdown (Client vs. Server)

### A. Functional Testing
*Degree to which the system provides correct results and covers user objectives.*

*   **Client Side:**
    *   Navigation, Forms, Data Interaction.
    *   Validation messages.
    *   Localization & Internationalization.
*   **Server Side:**
    *   **API Testing:** Sending requests/validating responses.
    *   **Database:** Data retrieval, insertion, updates, deletion.

### B. Performance Testing
*Relative to time behavior and resource utilization.*

*   **Client Side:**
    *   Load time & Page speed.
    *   **Resource Optimization:** Memory/CPU usage on the user's device.
    *   Caching behavior.
*   **Server Side:**
    *   **Load Testing:** Simulating heavy concurrent user loads.
    *   Identifying bottlenecks in response times.

### C. Compatibility Testing
*Ability to exchange info and perform functions in shared environments.*

*   **Client Side:**
    *   **Browser:** Chrome, Firefox, Safari, Edge.
    *   **Cross-Device:** Mobile vs. Desktop screens.
    *   **Cross-Platform:** Windows, macOS, iOS, Android.
*   **Server Side:**
    *   Testing on different server environments, platforms, and configurations.

### D. Usability Testing
*User satisfaction, effectiveness, and efficiency.*

*   **Focus:** Primarily **Client Side**.
*   **UX Testing:** Appropriateness, recognizability, and aesthetics.
*   **Accessibility:** Ensuring usage for people with disabilities (Screen readers, contrast).

### E. Reliability Testing
*Performance under specified conditions for a duration (Availability, Fault Tolerance).*

*   **Client Side:**
    *   **Offline Functionality:** Handling network drops/low connection.
*   **Server Side:**
    *   **Availability:** Endpoints must be reachable.
    *   **Failover/Recovery:** Recovering gracefully from hardware/software crashes.

### F. Security Testing
*Protection of information (Confidentiality, Integrity, Authenticity).*

*   **Client Side:**
    *   Authentication/Authorization flows.
    *   Vulnerabilities: XSS (Cross-Site Scripting), CSRF (Cross-Site Request Forgery).
*   **Server Side:**
    *   **SQL Injection** prevention.
    *   Secure authentication logic.

### G. Maintainability Testing
*Effectiveness of modifying/improving the system (Modularity, Scalability).*

*   **Both Sides:**
    *   Clean, readable code.
    *   **Modularity:** Breaking down components.
    *   **Error Handling/Logging:** Proper logs for debugging.
    *   **Scalability:** Design must adapt to increased load.

### H. Portability Testing
*Transferability from one environment to another.*

*   **Server Side Focus:**
    *   **Install/Upgrade:** Success without errors.
    *   **Clean Uninstallation:** Removing all files/registry entries.
    *   **Recovery Point:** Restoring system state after uninstalling.

## Key Takeaways
1.  **Context Matters:** Testing a banking app is different from testing an online shop (Security vs. Usability priorities).
2.  **Dual Validation:** Always verify logic on both **Frontend** (UX/Speed) and **Backend** (Logic/Data integrity).
3.  **Quality Model:** Use the 8 quality characteristics (Functional + 7 Non-functional) to guide your test strategy.