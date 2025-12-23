
***

# Lecture 11: Specifics of Mobile Application Testing
#MobileTesting #NativeVsWeb #iOS #Android #ExamPrep

## 1. Mobile Application Types
Software designed specifically for mobile devices (smartphones, tablets).

| Feature | **Mobile Web App** | **Mobile Native App** | **Mobile Hybrid App** |
| :--- | :--- | :--- | :--- |
| **Definition** | Web apps utilizing mobile browsers. | Built for specific OS (iOS/Android). | Combination of web and native approaches. |
| **Development** | Easy to build (HTML/CSS/JS). | Complex languages; separate dev for each OS. | Faster dev time; cross-platform compatibility. |
| **Installation** | No installation required. | **Required** via App Stores. | Distributed via Stores (Native container). |
| **Performance** | Slower; relies on browser. | **Fastest**; optimized for hardware. | Good, but slower than native. |
| **Device Access**| Hard to interact with hardware. | **Full access** (Camera, GPS, etc.). | Access via APIs. |
| **Offline** | Limited/None. | **Yes**, can work offline. | Limited. |
| **Updates** | Centralized (Instant). | Users must update via Store. | Mixed. |

## 2. Testing Specifics by Quality Attribute

### A. Functional Testing
*   **Interruptions:** Ensure app handles incoming calls, SMS, and notifications correctly (goes to background/resumes).
*   **Multitasking:** Device works in multitasking mode.
*   **Memory:** App does not consume excessive memory or prevent other apps from running.

### B. Performance Testing
*   **Network:** Validate behavior under **different coverage levels** (Peak, Average, Minimum/Weak signal).
*   **Battery:** Evaluate battery consumption under load.
*   **Resources:** Monitor CPU utilization.

### C. Compatibility Testing
*   **Fragmentation:** Must test across various screen sizes, resolutions, and hardware configs.
*   **OS Versions:** Support for different Android/iOS versions.
*   **Third-party:** Verification of libraries and external services.

### D. Usability Testing
*   **UX:** Assess navigation, clarity, and satisfaction.
*   **Feedback:** Gather user feedback for improvements.
*   **Context:** Ensure text/buttons are visible outdoors/in different lighting.

### E. Reliability Testing
*   **Stability:** Ensure no crashes during prolonged use (**Long-running tests**).
*   **Stress:** Test behavior under heavy load.

### F. Security Testing
*   **Compliance:** Critical for apps handling payments/PII.
*   **Vulnerabilities:** Detect risks of data breaches or theft.

### G. Portability & Store Policies
*   **Installation:** Verify install, upgrade, and **clean uninstallation**.
*   **Policies:** Must adhere to **Google Play** and **Apple App Store** guidelines to be published.

***

# Practical Tips for Testing Different Applications
#WebTesting #DesktopTesting #MobileStrategies #ExamPrep

## 1. Web Application Testing
*   **Core Focus:** Functionality, UI, API, Security, Performance, Cross-browser.
*   **UI/Functionality:** Test forms, HTML/CSS (for SEO crawling), and ensure no broken links.
*   **Web API:** Test business logic directly by sending calls and validating responses (bypassing GUI).
*   **Network Throttling:** Intentionally slowing down internet speed (e.g., via browser dev tools) to emulate low bandwidth conditions (3G/Slow 4G).
*   **Security:** Refer to **OWASP Top 10** (Standard awareness document for critical security risks).
*   **Performance:** Goal is to eliminate bottlenecks, not just find bugs.
*   **Cross-browser:** Browsers render code differently. Test on Chrome, Safari, Firefox, Edge.

## 2. Desktop Application Testing
*   **Core Focus:** Installation, Performance, UI, Cross-platform.
*   **Installation Testing:**
    *   Verify installation of **dependencies** (drivers, libraries).
    *   Check install paths and **uninstallation** processes.
    *   Ensure the program actually runs after install.
*   **Performance:**
    *   **Resource Utilization:** Monitor CPU, RAM, Disk, and Network usage.
    *   **Memory Leaks:** Watch for crashes during long sessions.
*   **Platform:** Test on target OS architectures (32-bit vs 64-bit).

## 3. Mobile Application Testing (Practical View)

### Mobile Web
*   **Focus:** Browser compatibility (Chrome vs Safari on mobile).
*   **Network:** Test on EDGE, 3G, 4G, Wi-Fi.
*   **Screen:** Validate appearance on smaller screens compared to desktop.

### Mobile Native
*   **Single-platform affinity:** Works faster but requires specific testing for iOS vs Android.
*   **Features:**
    *   **Orientation:** Landscape vs Portrait modes.
    *   **Sensors:** Camera, Location (GPS), Accelerometer.
    *   **Background:** How the app behaves when saved in the background (Energy saving mode).
*   **Connectivity:** Behavior during offline mode or bandwidth switching.

### Mobile Hybrid
*   Combines approaches: Scalable and cost-effective but inherits pros/cons of both.
*   **Strategy:** Test cross-platform compatibility and device feature access via APIs.

## Key Takeaways
1.  **Context is King:** Testing a bank app (Security focus) is different from an online shop (Usability focus).
2.  **Tools:** Use specific tools for each platform (Network throttlers for Web, Emulators/Real devices for Mobile).
3.  **Validation:** Always validate Frontend (UI) and Backend (Logic/Data) for all application types.