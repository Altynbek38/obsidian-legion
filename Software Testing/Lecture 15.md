
***

# Lecture 15: Basics of Automation Testing, VCS, CI/CD
#AutomationTesting #VCS #CICD #Gherkin #DataDriven #VisualTesting #ExamPrep

## 1. What is Automation Testing?
Using software tools to execute tests against a software application. It can automate manual processes and run scenarios quickly and repeatedly.

## 2. What Tests Can Be Automated?
Generally, tests that are:
*   **Repetitive:** Run frequently (e.g., regression).
*   **Time-consuming:** Manual execution takes too long.
*   **Complex calculations:** Prone to human error.
*   **Data-intensive:** Require testing with many data sets.

### Levels suitable for automation:
*   **Unit Tests:** Modules tested separately.
*   **Integration/API Tests:** Checking interfaces and server responses.
*   **GUI Tests:** Automating user interactions (can be more brittle).

### Ideal vs. Reality (Testing Pyramid)
*   **Ideal:** More automated Unit tests, fewer API/Integration tests, minimal GUI tests.
*   **Reality (Anti-pattern):** Often the reverse, with too much focus on slow, brittle GUI tests.

## 3. Automation Approaches

### A. Gherkin
*   A **readable language** for describing business behavior in `Given-When-Then` format.
*   Used in **Behavior-Driven Development (BDD)** frameworks (like Cucumber) to bridge the gap between business and technical teams.
*   **Example:**
  ```gherkin
    Feature: Login functionality
      Scenario: Successful login
        Given the user is on the login page
        When the user enters valid credentials
        And clicks the "Login" button
        Then the user should be logged in successfully
```
    
### B. Data-Driven Tests
*   The **same test script** is executed multiple times with **different input data**.
*   Data is often stored externally (e.g., Excel, CSV, JSON files).
*   **Benefit:** Efficiently tests various input combinations without rewriting scripts.

### C. Visual Testing
*   Compares the application's current view (UI) with a stored **reference image** (or baseline).
*   Identifies visual discrepancies that functional tests might miss.
*   Tools can highlight differences between the current state and the expected visual state.

## 4. Manual vs. Automated Testing

| Parameter | Manual Testing | Automated Testing |
| :--- | :--- | :--- |
| **Accuracy** | Can be prone to human error. | Highly accurate. |
| **Time** | Time-consuming. | Faster; operates on tools. |
| **Investment** | Lower initial (hiring testers). | Higher initial (tools, scripting). |
| **Skills** | No programming needed. | Requires programming skills. |
| **UI Interaction** | Testers might notice UI flaws. | Explicitly defined verifications. |
| **Regression** | Very time-consuming. | Much easier with tools. |

### Advantages of Automation:
*   Run tests 24/7.
*   Higher test coverage.
*   Reusability of scripts.
*   Automate complex scenarios.
*   Immediate feedback.

### Disadvantages of Automation:
*   Significant time and skills needed for setup.
*   Debugging and maintenance efforts.
*   Not suitable for all test types (e.g., exploratory).

### When to Automate?
*   **Long-term projects** (1+ year).
*   Tests involving large amounts of data or complex calculations.
*   Regression tests.
*   *Note:* Initial investment is high, but long-term savings are significant.

## 5. Automated Testing Process
1.  **Define Scope & Select Tools:** Determine what to automate and choose the right tools.
2.  **Plan, Design & Develop:** Create the automation framework and scripts.
3.  **Test Execution:** Run the automated scripts.
4.  **Maintenance:** Update scripts as the application evolves.

## 6. What Can Be Automated?
*   **Functional Tests:** Web, Mobile, Desktop applications.
*   **Non-Functional Tests:**
    *   **A/B Testing:** Comparing two versions of a feature.
    *   **Load/Performance:** Simulating users to test system performance.
    *   **Security Testing:** Identifying vulnerabilities.

## 7. Tools & Technologies
*   **Automation Testing Tools:** Katalon Studio, Selenium, Appium, TestComplete, Cypress.io.
*   **Version Control Systems (VCS):**
    *   Software for tracking and managing changes to code.
    *   Essential for collaboration, history, and reverting changes.
    *   Examples: **Git** (most popular), SVN, Mercurial.
    *   *xkcd Comic:* "Version Con-What?" humorously highlights the importance of VCS.
*   **Build:**
    *   *Verb:* Process of generating executable files.
    *   *Noun:* The executable files themselves, or their version identifier (e.g., 1.0, 1.4.1549).
*   **CI/CD (Continuous Integration/Continuous Delivery/Deployment):**
    *   **Pipeline:** Automates the build, test, and deploy process.
    *   **CI:** Developers frequently merge code changes into a central repository, after which automated builds and tests run.
    *   **CD:** Extends CI to automate the release of code to production.
    *   **Stages:** Get Source $\rightarrow$ Build $\rightarrow$ Unit Tests $\rightarrow$ Smoke Test $\rightarrow$ Deploy (QA) $\rightarrow$ Auto-Regression Test $\rightarrow$ Deploy (Production).
    *   **Tools:** Jenkins, Bamboo, GitLab CI, CruiseControl.

## Key Takeaways
1.  Automation increases **effectiveness, coverage, and speed**.
2.  It's an **investment** for the long term.
3.  **VCS (like Git)** is crucial for managing code and collaboration.
4.  **CI/CD pipelines** automate the entire release process for faster, more efficient delivery.