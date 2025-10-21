
### **Part 1: Fundamentals of Linear Regression**

#### **1.1 Objective of Regression**
Linear regression is a simple approach to **supervised learning**. Its primary goal is to model the relationship between a dependent variable (also called the **response** or **target**, denoted as `y`) and one or more independent variables (also called **predictors** or **features**, denoted as `x`).

The fundamental assumption is that the relationship between these variables is **linear**. We use a dataset, known as the **learning sample**, to "fit" or "train" a model. This trained model can then be used to predict the value of `y` for new, unseen values of `x`.

#### **1.2 The Univariate Linear Regression Model**
For a single predictor variable `x`, the relationship with the response `y` is defined by the following model:

*   **Formula:**
    `yᵢ = β₀ + β₁xᵢ + εᵢ`

*   **Explanation of Components:**
    *   `yᵢ`: The *i*-th observed value of the dependent variable.
    *   `xᵢ`: The *i*-th observed value of the independent variable.
    *   `β₀` (or `α`): The **intercept** of the regression line. This is the predicted value of `y` when `x` is zero.
    *   `β₁` (or `β`): The **slope** of the regression line. This represents the average increase (or decrease) in `y` for a one-unit increase in `x`.
    *   `εᵢ`: The **error term** (or unpredictable random disturbance). It represents the difference between the actual observed value `yᵢ` and the value predicted by the linear model. It captures all the factors that influence `y` but are not included in the model.

### **Part 2: Estimating the Model Parameters (Ordinary Least Squares)**

#### **2.1 The Goal: Minimizing Residuals**
The true values for `β₀` and `β₁` are unknown. We must estimate them from our sample data. These estimates are denoted by `β̂₀` and `β̂₁`.

The predicted value of `y` for a given `xᵢ` is given by the regression line:
*   **Prediction Formula:**
    `ŷᵢ = β̂₀ + β̂₁xᵢ`

The difference between the *observed value* (`yᵢ`) and the *predicted value* (`ŷᵢ`) is called the **residual**.
*   **Residual Formula:**
    `eᵢ = yᵢ - ŷᵢ`

To find the "best-fitting" line, we need to find the `β̂₀` and `β̂₁` that make the residuals as small as possible. The most common method is **Ordinary Least Squares (OLS)**, which minimizes the **Sum of Squared Residuals (SSR)**, also known as the **Residual Sum of Squares (RSS)**.

*   **Sum of Squared Residuals (SSR / RSS) Formula:**
    `SSR = Σ eᵢ² = Σ (yᵢ - ŷᵢ)² = Σ (yᵢ - β̂₀ - β̂₁xᵢ)²`

#### **2.2 The OLS Estimator Formulas**
By using calculus to find the minimum of the SSR function, we arrive at analytical formulas for `β̂₀` and `β̂₁`:

*   **Slope Estimator (`β̂₁`):**
    `β̂₁ = Σ(xᵢ - x̄)(yᵢ - ȳ) / Σ(xᵢ - x̄)²`

*   **Intercept Estimator (`β̂₀`):**
    `β̂₀ = ȳ - β̂₁x̄`

Where `x̄` is the sample mean of `x` and `ȳ` is the sample mean of `y`.

---

### **Part 3: Assessing the Accuracy of the Model**

After fitting the model, we must evaluate its accuracy. This is done in two ways: assessing the individual coefficients and assessing the overall model fit.

#### **3.1 Assessing the Coefficient Estimates**

*   **Standard Error (SE):** The standard error of an estimated coefficient measures the average amount that the estimate would vary from the actual value if we were to repeat the experiment with different samples. A smaller SE indicates a more precise estimate.
    *   **Formulas:**
        `SE(β̂₁)² = σ² / Σ(xᵢ - x̄)²`
        `SE(β̂₀)² = σ² [1/n + x̄² / Σ(xᵢ - x̄)²]`
        (where `σ²` is the variance of the error term `ε`)

*   **Confidence Intervals:** A 95% confidence interval is a range of values that will contain the true, unknown value of the coefficient with 95% probability. If the interval does not contain zero, we can be confident that the predictor is related to the response.
    *   **Formula (for β₁):** `β̂₁ ± 2 ⋅ SE(β̂₁)`

*   **Hypothesis Testing:** This is a formal way to test if a relationship exists between `x` and `y`.
    *   **Null Hypothesis (H₀):** There is no relationship. (`β₁ = 0`)
    *   **Alternative Hypothesis (Hₐ):** There is a relationship. (`β₁ ≠ 0`)
    *   To test this, we calculate a **t-statistic**. A larger t-statistic suggests the coefficient is unlikely to be zero.
        *   **t-statistic Formula:** `t = (β̂₁ - 0) / SE(β̂₁)`
    *   The **p-value** is the probability of observing a t-statistic as large as we did, assuming the null hypothesis is true. A small p-value (typically < 0.05) provides strong evidence to reject the null hypothesis and conclude that the predictor is statistically significant.

#### **3.2 Assessing Overall Model Fit**

*   **Residual Standard Error (RSE):** The RSE is an estimate of the standard deviation of the error term `ε`. It represents the average amount that the response `y` will deviate from the true regression line.
    *   **RSE Formula:** `RSE = √[SSR / (n - 2)]`

*   **R-squared (R²):** The R² statistic measures the proportion of the total variance in the response `y` that is explained by the model. It ranges from 0 to 1. An R² of 0.61 means that 61% of the variability in `y` can be explained by `x`.
    *   **R² Formula:** `R² = (TSS - SSR) / TSS = 1 - SSR / TSS`
        (where `TSS = Σ(yᵢ - ȳ)²` is the Total Sum of Squares)

---

### **Part 4: Multiple Linear Regression (MLR)**

#### **4.1 The MLR Model**
MLR extends the model to include multiple predictors (`p` predictors).

*   **Formula:** `y = β₀ + β₁x₁ + β₂x₂ + ... + βₚxₚ + ε`

*   **Interpretation:** The coefficient `βⱼ` is interpreted as the average effect on `y` of a one-unit increase in `xⱼ`, **holding all other predictors fixed**. This is a crucial distinction from simple linear regression.

#### **4.2 MLR in Matrix Form**
The MLR model can be written more compactly using matrix notation.

*   **Formula:** `y = Xβ + ε`

*   **OLS Estimator for MLR:** The formula to find the vector of estimated coefficients (`β̂`) that minimizes the SSR is:
    *   **Formula:** `β̂ = (X'X)⁻¹X'y`

#### **4.3 Assessing the MLR Model**

*   **F-statistic:** In MLR, we use the F-statistic to test the overall significance of the model. It tests the null hypothesis that *all* regression coefficients are zero (`β₁ = β₂ = ... = βₚ = 0`). A high F-statistic (and a corresponding low p-value) indicates that at least one predictor is useful.
    *   **F-statistic Formula:** `F = [(TSS - SSR)/p] / [SSR / (n - p - 1)]`

*   **Variable Selection:** Since not all predictors may be useful, we use automated approaches to select the best subset of variables.
    *   **Forward Selection:** Start with no predictors, and add them one by one if they improve the model.
    *   **Backward Selection:** Start with all predictors, and remove the least significant ones one by one.

---

### **Part 5: Advanced Topics and Considerations**

#### **5.1 Handling Qualitative Predictors**
To include a non-numerical predictor (e.g., "ethnicity"), we create **dummy variables**. For a qualitative predictor with *k* categories, we create *k-1* dummy variables that take a value of 0 or 1. The category without a dummy variable is called the **baseline**.

#### **5.2 Interaction Effects**
The standard model assumes an **additive effect**, meaning the effect of one predictor on `y` is independent of other predictors. An **interaction effect** (or synergy) occurs when the effect of one predictor depends on the level of another.

*   **Model with Interaction:**
    `y = β₀ + β₁x₁ + β₂x₂ + β₃(x₁x₂) + ε`
*   Here, the effect of `x₁` on `y` is now `(β₁ + β₃x₂)`—it changes with the value of `x₂`.
*   **Hierarchy Principle:** If you include an interaction term in a model, you should also include the main effects (`x₁` and `x₂`), even if their p-values are not significant.

#### **5.3 Non-linear Relationships**
If the data shows a curved relationship, we can use **polynomial regression** by adding polynomial terms of the predictors to the model.

*   **Example (Quadratic Model):**
    `y = β₀ + β₁x + β₂x² + ε`