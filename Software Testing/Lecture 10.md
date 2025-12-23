
***

# Lecture 10: Specifics of Desktop Application Testing
#DesktopTesting #InstallationTesting #Performance #ExamPrep

## 1. What is a Desktop Application?
A software program that runs locally on a computer device (unlike web apps that run in a browser).
*   **Platform:** Runs on specific Operating Systems (Windows, macOS, Linux).
*   **Requirement:** Requires **installation**.
*   **Resources:** Has access to full local computer resources (CPU, Memory, Storage) for better performance.
*   **Hardware:** Can directly interact with connected peripherals (Printers, Webcams, Scanners).
*   **Variety:** Ranges from simple (Calculator) to complex (Video Rendering, Engineering software).

## 2. Testing Types for Desktop Apps

### A. Functional Testing
*   **Goal:** Verify the application performs calculations, processes data, and executes tasks accurately according to requirements.
*   **Scope:** Test individual features and end-to-end workflows.

### B. Performance Testing
*   **Resource Utilization:** Critical check of how much CPU, Memory, and Disk space is consumed.
*   **Local Execution:** Since logic runs locally, ensure the machine doesn't freeze during heavy tasks.
*   **Hardware Access:** Verify efficient interaction with drivers and peripherals.

### C. Compatibility Testing
*   **Target Environments:** Testing on different OS versions (e.g., Windows 10 vs. 11, macOS) and Architectures (32-bit vs. 64-bit).
*   **Device Testing:** Ensuring consistent functionality with external hardware (Bluetooth devices, printers).

### D. Usability Testing
*   Evaluating ease of navigation, learnability, and UI attractiveness.
*   **Key Aspect:** Desktop apps often have complex menus and shortcuts that must be intuitive.

### E. Reliability Testing
*   **Goal:** Ensure no crashes during prolonged use.
*   **Long-Running Tests:** Leaving the app running for days to check for **memory leaks**.
*   **Stress/Load:** Heavy usage of local resources.

### F. Security Testing
*   **Permissions:** Testing functionality with **User** vs. **Admin** privileges.
*   **Local Data:** ensuring local storage/files are encrypted.
*   **Input:** Validation and sanitization of data entered.

### G. Maintainability Testing
*   **Modularity:** Can one component be changed without breaking others?
*   **Reusability:** Can assets be used in other systems?
*   **Modifiability:** Ease of updating the software.

### H. Portability Testing (Crucial for Desktop)
Since the app lives on the user's machine, the lifecycle of the app files is critical:
1.  **Install:** Must succeed without errors on supported environments.
2.  **Upgrade:** Updating from Version 1.0 $\rightarrow$ 2.0 without data loss.
3.  **Clean Uninstallation:** Removing all files, folders, and **registry entries**.
4.  **Recovery Point:** System restoration capabilities.

## 3. Key Differences: Desktop vs. Web
| Feature | **Desktop App** | **Web App** |
| :--- | :--- | :--- |
| **Connectivity** | **Can operate Offline.** | Usually requires Internet. |
| **Resources** | Uses local machine power. | Uses Server power (mostly). |
| **Maintenance** | Users must update manually. | Updates happen on server (instant). |
| **Access** | specific machine installation. | Any browser/device. |

## Key Takeaways
1.  **Installation & Configuration:** This is a unique and critical test phase for desktop apps (Install/Uninstall/Update).
2.  **Offline Capability:** Desktop apps should work without internet (unless strictly cloud-based).
3.  **Hardware Dependency:** Testing must account for various hardware specs (RAM, CPU) and peripherals.