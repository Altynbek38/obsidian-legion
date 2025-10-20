
### **Part 1: Introduction to Univariate Linear Regression**

#### **1.1 Objective and Context**
The primary goal is to "fit," "train," or "estimate" a model using a given dataset (the **learning sample**). This model will allow us to predict a target variable `y` based on a new, unseen explanatory variable `x`.

For example, we can use a dataset of house prices and sizes to build a model that predicts the price of a new house given its size.

#### **1.2 The Univariate Regression Model**
We assume a linear relationship exists between the input `x` and the output `y`. This relationship is defined by the following theoretical model:

*   **Formula:**
    `yᵢ = α + βxᵢ + εᵢ`

*   **Explanation of Components:**
    *   `yᵢ`: The dependent variable (the value we want to predict, e.g., Price).
    *   `xᵢ`: The independent variable (the predictor, e.g., Size).
    *   `α` (alpha): The **intercept**, which is the value of `y` when `x` is zero.
    *   `β` (beta): The **slope**, which tells us how much `y` increases (or decreases) for every one-unit increase in `x`.
    *   `εᵢ` (epsilon): The **error term**, which represents the unpredictable random disturbance. It captures all the factors that influence `y` but are not accounted for by `x`.

### **Part 2: Finding the Best Fit - Ordinary Least Squares (OLS)**

#### **2.1 The Goal: Minimizing Errors**
The true parameters `α` and `β` are unknown. Our goal is to find their estimates, denoted as `â` and `β̂`, that create the "best-fitting" line through our data. This means we want the predicted values (`ŷ`) to be as close as possible to the actual observed values (`y`).

*   **Prediction Formula:** `ŷ = â + β̂x`

To quantify the difference between the actual and predicted values, we use **residuals**.

*   **Residual Definition:** A residual (`εᵢ`) is the error for a single observation.
    *   **Formula:** `εᵢ = yᵢ - ŷᵢ`

The method used to find the best `â` and `β̂` is to minimize the total error across all data points. Specifically, we minimize the **Sum of Squared Residuals (SSR)**.

*   **Sum of Squared Residuals (SSR) Formula:**
    `SSR = Σ εᵢ² = Σ (yᵢ - ŷᵢ)² = Σ (yᵢ - â - β̂xᵢ)²`

#### **2.2 The OLS Solution for Univariate Regression**
**Ordinary Least Squares (OLS)** is the process of finding the parameter estimates (`â`, `β̂`) that minimize the SSR. For univariate regression, there is an analytical solution derived from calculus:

*   **Slope Estimator (`β̂`):**
    `β̂ = Σ(xᵢ - x̄)(yᵢ - ȳ) / Σ(xᵢ - x̄)²`

*   **Intercept Estimator (`â`):**
    `â = ȳ - β̂x̄`

Where `x̄` is the sample mean of `x` and `ȳ` is the sample mean of `y`.

### **Part 3: Extending to Multi-linear Regression (MLR)**

#### **3.1 The Multi-linear Model**
Often, we want to estimate `y` using more than one explanatory variable. This is called **multi-linear regression**.

*   **Formula:**
    `y = β₀ + β₁x₁ + β₂x₂ + ... + βₖxₖ + ε`
    *   `β₀` is the intercept.
    *   `β₁` through `βₖ` are the coefficients for each of the `k` predictor variables.

#### **3.2 MLR in Matrix Form**
To handle multiple predictors efficiently, we redefine the linear regression model using matrices.

*   **Matrix Formula:** `y = Xβ + ε`

This single equation represents the entire system of linear equations, where:
*   `y` is a vector of the observed target values.
*   `X` is the **design matrix**, where each row is an observation and each column is a predictor (with an initial column of ones for the intercept).
*   `β` is the vector of coefficients (`β₀`, `β₁`, etc.).
*   `ε` is the vector of error terms.

#### **3.3 The OLS Solution for Multi-linear Regression**
Just as with the simple case, the goal is to find the vector of coefficients `β̂` that minimizes the SSR. Using matrix algebra, the OLS solution is:

*   **OLS Estimator for MLR (`β̂`):**
    `β̂ = (X'X)⁻¹X'y`
    *   This formula allows us to solve for all the model's coefficients simultaneously.