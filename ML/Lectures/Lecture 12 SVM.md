
---

# Lecture: Support Vector Machines (SVM)
`tags: #ML #classification #SVM #kernels`

> **Core Idea:** SVMs are a powerful class of supervised learning models for classification that find the optimal **hyperplane** to separate data points into different classes.

**Two main strategies:**
1.  For linearly separable data, find the hyperplane that maximizes the **margin** (the gap) between the classes.
2.  If data isn't perfectly separable, we can either:
    -   **Soften the margin:** Allow some points to be misclassified (Support Vector Classifier).
    -   **Enrich the feature space:** Map data to a higher dimension where it becomes separable (The Kernel Trick).

## 1. The Hyperplane

A hyperplane is a flat subspace of dimension `p-1` in a `p`-dimensional space.

-   **In 2D:** A line.
-   **In 3D:** A flat plane.

-   **General Equation:** The decision boundary is defined where the function $f(X)$ equals zero.
    $$ f(X) = \beta_0 + \beta_1 X_1 + \beta_2 X_2 + \dots + \beta_p X_p = 0 $$
-   **Classification Rule:**
    -   Points where $f(X) > 0$ are on one side of the hyperplane.
    -   Points where $f(X) < 0$ are on the other side.
-   If we set class labels $Y_i$ to be `+1` or `-1`, a separating hyperplane is one where **$Y_i \cdot f(X_i) > 0$** for all points `i`.

## 2. Maximal Margin Classifier ("Hard Margin" SVM)

> **Goal:** Among all possible separating hyperplanes, find the one that creates the largest possible margin between the two classes.

This is a constrained optimization problem.

-   **Objective:**
    $$ \underset{\beta_0, \beta_1, \dots, \beta_p}{\text{maximize}} \quad M $$
-   **Subject to the constraints:**
    1.  $y_i(\beta_0 + \beta_1 x_{i1} + \dots + \beta_p x_{ip}) \ge M$ for all points $i=1, \dots, N$.
    2.  $\sum_{j=1}^{p} \beta_j^2 = 1$ (This normalizes the parameter vector).

-   **Support Vectors:** The data points that lie exactly on the edge of the margin are called **support vectors**. They are the critical points that "support" or define the hyperplane.
-   **Limitation:** This only works if the data is **perfectly linearly separable** and is very sensitive to outliers.

## 3. Support Vector Classifier ("Soft Margin" SVM)

This is an extension of the maximal margin classifier that allows for some misclassifications, making it more robust to noisy data and non-separable cases.

-   **Idea:** Allow some data points to be inside the margin or on the wrong side of the hyperplane, but apply a penalty.

-   **Modified Optimization Problem:**
    $$ \underset{\beta_0, \dots, \beta_p, \epsilon_1, \dots, \epsilon_n}{\text{maximize}} \quad M $$
-   **Subject to:**
    1.  $y_i(\beta_0 + \dots + \beta_p x_{ip}) \ge M(1 - \epsilon_i)$
    2.  $\epsilon_i \ge 0$
    3.  $\sum_{i=1}^{n} \epsilon_i \le C$
    4.  $\sum_{j=1}^{p} \beta_j^2 = 1$

-   $\epsilon_i$ are **slack variables**: they measure how much a point `i` violates the margin.
-   $C$ is a **regularization hyperparameter**: It controls the bias-variance trade-off.
    -   **Small `C`:** A wider margin, more tolerant of margin violations (higher bias, lower variance).
    -   **Large `C`:** A narrower margin, less tolerant of violations (lower bias, higher variance).

## 4. SVM for Non-Linear Boundaries: The Kernel Trick

What if a linear boundary is insufficient? We can create non-linear decision boundaries by mapping the data into a higher-dimensional space.

-   **Feature Expansion:** Manually add polynomial or interaction terms (e.g., $X_1^2, X_2^2, X_1X_2$) to the feature set. Then, fit a linear SVM in this new, higher-dimensional space. This creates a non-linear boundary in the original space.
-   **Problem:** Explicitly creating these features can be computationally explosive.

### The Kernel Trick

> **Key Insight:** The SVM algorithm only depends on the **inner products** of the data points, not their individual coordinates.
> $$ \langle x_i, x_{i'} \rangle = \sum_{j=1}^{p} x_{ij} x_{i'j} $$

-   The decision function can be rewritten in terms of these inner products:
    $$ f(x) = \beta_0 + \sum_{i \in S} \alpha_i \langle x, x_i \rangle $$
    -   `S` is the set of indices of the **support vectors**.

-   A **Kernel** is a function $K(x_i, x_{i'})$ that efficiently computes the inner product between two points as if they were projected into a higher-dimensional space, *without ever performing the projection*.

-   **Final SVM Decision Function with Kernels:**
    $$ f(x) = \beta_0 + \sum_{i \in S} \hat{\alpha}_i K(x, x_i) $$

### Common Kernels

-   **Polynomial Kernel:** Creates a polynomial decision boundary of degree `d`.
    $$ K(x_i, x_{i'}) = \left( 1 + \sum_{j=1}^{p} x_{ij}x_{i'j} \right)^d $$
-   **Radial Basis Function (RBF) Kernel:** A popular, powerful default kernel. Creates complex local boundaries. Corresponds to an infinite-dimensional feature space.
    $$ K(x_i, x_{i'}) = \exp\left(-\gamma \sum_{j=1}^{p} (x_{ij} - x_{i'j})^2\right) $$

## 5. Multi-Class SVM

SVM is inherently a binary classifier. To handle K > 2 classes, two main strategies are used:

-   **One-vs-All (OVA / OvR):** Train `K` different SVM classifiers. Each one is trained to separate one class from the rest.
-   **One-vs-One (OVO):** Train $\binom{K}{2}$ classifiers, one for every pair of classes. A new point is classified by a "voting" scheme among all classifiers. Often preferred for SVMs.

## 6. SVM vs. Logistic Regression

-   **Loss Function:** The SVM optimization can be rephrased as minimizing a **Hinge Loss** function plus a penalty term. Logistic Regression minimizes a **Log Loss**. They are conceptually very similar.
    $$ \underset{\beta}{\text{minimize}} \left\{ \sum_{i=1}^{n} \max[0, 1 - y_i f(x_i)] + \lambda \sum_{j=1}^{p} \beta_j^2 \right\} $$
-   **When to use which?**
    -   **SVM:** Excellent when classes are nearly separable or for complex non-linear problems (with kernels).
    -   **[[Logistic Regression]]:** Simpler, faster to train, and provides direct **probability estimates**, which SVMs do not.