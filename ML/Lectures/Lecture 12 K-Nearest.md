Of course. Here is a clear and well-structured summary of the lecture on k-Nearest Neighbors, formatted for your Obsidian notebook.

---
# Lecture: k-Nearest Neighbors (k-NN)
`tags: #ML #classification #regression #nonparametric #lazy_learning`

> **Core Idea:** k-NN is a simple, non-parametric algorithm that predicts the label of a new data point by looking at the labels of its **'k' closest neighbors** in the training data. It is a "lazy learner" because it does no work during training; it simply stores the dataset.

## 1. The k-NN Algorithm

The process for predicting a new, unseen sample `x` is as follows:

1.  **Choose a hyperparameter `k`:** The number of neighbors to consider.
2.  **Calculate Distances:** Compute the distance from the new point `x` to every point `x_i` in the training dataset. The most common distance metric is the **Euclidean distance**.
    $$ \rho(x, x_i) = ||x - x_i|| $$
3.  **Find Nearest Neighbors:** Identify the `k` training data points that have the smallest distances to `x`.
4.  **Make a Prediction:**
    -   **For Classification:** The predicted label $\hat{y}$ is the **majority class** (the most common label) among the `k` neighbors.
        $$ \hat{y} = \arg\max_{y \in \mathcal{Y}} \sum_{i=1}^{k} \mathbb{I}(y = y_{(i)}) $$
        Where $y_{(i)}$ is the label of the i-th nearest neighbor and $\mathbb{I}$ is the indicator function.
    -   **For Regression:** The predicted value $\hat{y}$ is the **average** of the values of the `k` neighbors.
        $$ \hat{y} = \frac{1}{k} \sum_{i=1}^{k} y_{(i)} $$

### Voronoi Tessellation (for k=1)
When `k=1`, the decision boundary forms a **Voronoi tessellation**. This means the feature space is divided into regions, where each region consists of all points closer to one specific training point than any other. This results in a complex, jagged decision boundary.

## 2. The Role of the Hyperparameter `k`

The choice of `k` controls the model's complexity and the bias-variance trade-off.

-   **Small `k` (e.g., k=1):**
    -   The model is highly flexible and sensitive to noise.
    -   **Low Bias, High Variance.**
    -   Prone to **[[Overfitting]]**. The training error can be very low (for k=1, training error is 0), but the test error is often high.

-   **Large `k`:**
    -   The model is less flexible and the decision boundary becomes smoother.
    -   **High Bias, Low Variance.**
    -   Prone to **[[Underfitting]]** if `k` is too large, as it will average out important local patterns.

> **Goal:** Find a "sweet spot" for `k` that minimizes the test error, balancing between overfitting and underfitting. This is typically done using [[Cross-Validation]].

## 3. The Curse of Dimensionality

k-NN's performance suffers significantly as the number of features (dimensions) increases. This is known as the **[[Curse of Dimensionality]]**.

-   **Core Problem:** As dimensions (`d`) increase, the volume of the feature space grows exponentially.
-   **Consequences:**
    1.  **Data becomes sparse:** To maintain the same density of data points, you need an exponentially larger dataset.
    2.  **Distances become less meaningful:** In high-dimensional space, the distance to the nearest neighbor can become similar to the distance to the farthest neighbor. The concept of a "local neighborhood" breaks down.
    -   **Example:** To capture 10% of the data (`p=0.1`) in a `d`-dimensional hypercube, the required edge length is $e_d(p) = p^{1/d}$.
        -   In 2D: $e_2(0.1) = 0.1^{1/2} \approx 0.32$ (32% of the range)
        -   In 10D: $e_{10}(0.1) = 0.1^{1/10} \approx 0.80$ (80% of the range)
        -   This shows that in high dimensions, a "small" local neighborhood covers a vast portion of the feature space.

## 4. Practical Considerations for k-NN

-   **Pros:**
    -   Simple to understand and implement.
    -   Non-parametric: Makes no strong assumptions about the underlying data distribution.
    -   Can create complex, non-linear decision boundaries.

-   **Cons:**
    -   **Computationally expensive at prediction time:** Must compute distances to *all* training points for each new prediction.
    -   **Highly sensitive to the curse of dimensionality.**
    -   **Requires Feature Scaling:** Features with larger scales can dominate the distance metric. It is crucial to normalize or standardize data before applying k-NN.