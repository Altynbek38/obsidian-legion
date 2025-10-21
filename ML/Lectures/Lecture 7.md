
### **Part 1: Properties of an Estimator**

In statistics, an estimator (in this case, our OLS coefficient `β̂`) is considered a random variable because its value depends on the specific random sample of data (`X` and `y`) that we happen to collect. To evaluate how good an estimator is, we look at two key properties: its bias and its variance.

#### **1.1 Bias of an Estimator**
*   **Definition:** Bias measures the accuracy of an estimator. It is the difference between the expected value (or average) of the estimator and the true value of the parameter it is trying to estimate.
*   **Formula:**
    `Bias(β̂) = E[β̂] - β`
*   **Interpretation:**
    *   **Unbiased Estimator:** If the bias is zero (`E[β̂] = β`), the estimator is unbiased. This means that if we were to repeat our sampling process many times, the average of all our estimates would be equal to the true parameter value. The estimator is correct on average.
    *   **Biased Estimator:** If the bias is not zero, the estimator will systematically overestimate or underestimate the true parameter value.
*   **Key Property of OLS:** Under a specific set of assumptions (covered in Part 3), the **OLS estimator is unbiased**.

#### **1.2 Variance of an Estimator**
*   **Definition:** Variance measures the precision or consistency of an estimator. It describes the spread of the estimator's values around its own expected value.
*   **Formula:**
    `Var(β̂) = E[(β̂ - E[β̂])²]`
*   **Interpretation:**
    *   **Small Variance:** A good estimator has a small variance, meaning that if we repeated the sampling process, our estimates would be tightly clustered together. The estimator is precise and reliable.
    *   **Large Variance:** A large variance indicates that the estimates are spread out and less reliable. The estimator is inefficient.
*   **Variance of the OLS Estimator:** Under the standard assumptions, the variance of `β̂` is given by:
    *   **Formula:** `Var(β̂) = σ²(X'X)⁻¹`
        (where `σ²` is the variance of the model's error term).

---

### **Part 2: The Gauss-Markov Theorem**

This is a central theorem in econometrics and statistics that tells us why OLS is such a powerful and popular method.

*   **Statement:** The Gauss-Markov theorem states that, under the set of OLS assumptions, the OLS estimator is the **Best Linear Unbiased Estimator (BLUE)**.

*   **Breaking down "BLUE":**
    *   **B (Best):** OLS has the lowest possible variance among the class of all linear unbiased estimators. This means it is the most **efficient** and precise estimator you can find in that class.
    *   **L (Linear):** The OLS estimator is a linear function of the dependent variable `y`.
    *   **U (Unbiased):** The expected value of the OLS estimator is the true value (`E[β̂] = β`). It is correct on average.
    *   **E (Estimator):** `β̂` is an estimator for the true parameter `β`.

**In short: If the OLS assumptions hold, you cannot find a better (more precise) linear and unbiased estimator than OLS.**

---

### **Part 3: The OLS Assumptions**

These are the "rules" or conditions that must be met for the Gauss-Markov theorem to hold true, ensuring that OLS is indeed the best linear unbiased estimator.

#### **1. Linearity in Parameters**
The model must be a linear function of the parameters (`β`). The predictor variables (`X`) can be transformed (e.g., squared), but the coefficients cannot be.
*   *Valid:* `y = β₀ + β₁X² + ε`
*   *Invalid:* `y = β₀ + β₁²X + ε`

#### **2. Random Sampling**
The data must be a random sample from the population of interest. This ensures the sample is representative and helps avoid **selection bias**, allowing the results to be generalized.

#### **3. No Perfect Collinearity**
No independent variable can be a perfect linear combination of any other independent variables.
*   **Why it's important:** If perfect collinearity exists, the `(X'X)` matrix is not invertible, and the OLS coefficients cannot be calculated. Essentially, the model cannot distinguish the individual impact of the perfectly correlated variables.
*   **Example:** Including both "number of lectures attended" and "hours spent in the lecture room" as predictors. These two variables would be almost perfectly correlated, making it impossible to estimate their separate effects.

#### **4. Independence of Errors**
The error terms (`εᵢ`) for each observation must be independent of (and uncorrelated with) the error terms of all other observations. `Cov(εᵢ, εⱼ) = 0`.
*   **Why it's important:** Correlated errors often arise from an **omitted variable** that influences multiple observations. This correlation leads to inefficient estimates with high variance.
*   **Example:** If some students in a sample study together, their shared study habits (an omitted variable) will cause their error terms to be correlated, as their performance will be more similar than that of random students.

#### **5. Homoskedasticity**
The variance of the error term (`ε`) must be constant for all values of the predictor variables (`X`).
*   **Formula:** `Var(ε | X) = σ²`
*   **Heteroskedasticity** (the opposite) occurs when the spread of the errors is different for different values of `X`. This makes the OLS estimator inefficient.

#### **6. Zero Conditional Mean**
The expected value of the error term must be zero, given any value of the independent variables. This means the predictors must not contain any information about the mean of the error term.
*   **Formula:** `E[ε | X] = 0`
*   **Why it's important:** This is the most critical assumption for ensuring that the OLS estimator is **unbiased**. If violated, it means there is a systematic relationship between the predictors and the errors, which biases the coefficient estimates.