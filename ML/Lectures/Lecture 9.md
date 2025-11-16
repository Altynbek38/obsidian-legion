Here are the notes from the lecture on "Introduction to Machine Learning, Week 9":

### Introduction to Machine Learning as an Optimization Problem

Machine learning algorithms can be viewed as optimization programs that aim to minimize a cost function. A common algorithm for this is the **gradient descent algorithm**.

There are three main versions of gradient descent:
*   **Vanilla (or Batch) Gradient Descent**
*   **Stochastic Gradient Descent (SGD)**
*   **Mini-Batch Gradient Descent**

### Linear Regression and Ordinary Least Squares (OLS)

A general model is represented as `y = f(X) + ε`, where `y` is the target variable, `X` is the set of predictors, and `ε` is the error term. In linear regression, this is simplified to `y = Xβ + ε`.

The goal is to find the coefficients `β` that minimize an objective function. With Ordinary Least Squares (OLS), there's an analytical solution: `β̂ = (XᵀX)⁻¹Xᵀy`.

### Time Complexity of OLS

The time complexity of OLS is a measure of the time it takes for the algorithm to run as a function of the input size.

*   **For large datasets (n >> m):** The dominant term is `O(nm²)`, coming from the matrix multiplication `XᵀX`. The computational cost increases significantly with more samples.
*   **For high dimensionality (m >> n):** The dominant term is `O(m³)`, which comes from the matrix inversion of `XᵀX`. A high number of features makes it computationally expensive.

Due to these complexities, especially with large-scale or high-dimensional data, numerical optimization techniques like gradient descent are often preferred over analytical solutions. Numerical solutions are also more flexible and applicable to non-linear models.

### Vanilla Gradient Descent

The process of vanilla gradient descent involves:

1.  **Initialization:** Start at a random point on the function.
2.  **Determine Direction:** Compute the derivative (slope) of the function at that point.
    *   If the slope is **positive**, move to the left.
    *   If the slope is **negative**, move to the right.
3.  **Determine Step Size (Learning Rate):** Decide how far to move.
    *   A **small learning rate** may lead to getting stuck in a local minimum.
    *   A **large learning rate** risks overshooting the minimum and bouncing around it.
4.  **Iterate:** Repeat the process until a stopping criterion is met, such as reaching a maximum number of iterations or the improvement becoming too small (tolerance).

### Gradient Descent in Higher Dimensions

For a function with multiple variables, like `f(x₁, x₂) = x₁² + x₂²`, the direction of steepest ascent is found by computing the **gradient**, which is a vector of partial derivatives.

The update rule for the parameters `θ` at each step `t` is:
`θ⁽ᵗ⁺¹⁾ = θ⁽ᵗ⁾ - η · ∇L(θ⁽ᵗ⁾)`
where:
*   `η` is the learning rate.
*   `∇L(θ⁽ᵗ⁾)` is the gradient of the loss function.

### Variants of Gradient Descent

The main difference between the variants lies in how much data is used to compute the gradient for each parameter update.

*   **Vanilla (Batch) Gradient Descent:** Uses the **entire dataset** to compute the gradient in each iteration.
*   **Stochastic Gradient Descent (SGD):** Updates the parameters using **one randomly chosen data sample** at a time. The dataset is shuffled at the beginning of each epoch.
*   **Mini-Batch Gradient Descent:** Updates the parameters using a **small, random batch of data** (e.g., 32 or 64 samples) at a time. The dataset is also shuffled, and then partitioned into mini-batches.

### Implementation in Scikit-learn

*   **OLS:** `sklearn.linear_model.LinearRegression`
*   **Gradient Descent:** `sklearn.linear_model.SGDRegressor`
    *   **Vanilla GD:** `shuffle=False`
    *   **Stochastic GD (SGD):** `shuffle=True` (this is the default)
    *   **Mini-Batch GD:** Implemented by iterating through mini-batches and using the `partial_fit` method.