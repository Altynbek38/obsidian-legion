
---
# Lecture 13: Decision Trees
`tags: #ML #classification #regression #trees`

> **Core Idea:** A Decision Tree is a non-parametric model that recursively partitions the feature space into a set of rectangular regions. It makes predictions by assigning a simple model (like the average value or the most common class) to each region. They are highly interpretable ("white box" models).

The standard algorithm is **CART** (Classification and Regression Trees).

**Tree Terminology:**
-   **Root:** The top node that contains all observations.
-   **Internal Nodes:** Points where the data is split based on a feature and a threshold.
-   **Leaves (Terminal Nodes):** The final regions at the bottom of the tree where predictions are made.

## 1. Regression Trees

Used when the target variable `y` is **quantitative** (continuous).

### How to Build a Regression Tree (Recursive Binary Splitting)

The tree is built using a greedy, top-down algorithm called **Recursive Binary Splitting**.

1.  **Partition the Space:** Divide the training data into `J` distinct regions, $R_1, R_2, ..., R_J$.
2.  **Predict:** For any observation that falls into a region $R_j$, the prediction $\hat{y}$ is the **average** of the training labels in that region.
    $$ \hat{y}_{R_j} = \frac{1}{|R_j|} \sum_{i \in R_j} y^{(i)} $$

### The Splitting Criterion: Minimizing RSS

The goal is to find regions that minimize the **Sum of Squared Residuals (SSR)**, which is the training error.
$$ SSR = \sum_{j=1}^{J} \sum_{i \in R_j} (y^{(i)} - \hat{y}_{R_j})^2 $$
Since searching all possible partitions is computationally impossible, the greedy approach works as follows:
-   At each node, consider every feature $x_j$ and every possible split point `s`.
-   Choose the feature `j` and split `s` that produces the greatest possible reduction in RSS. That is, the split that minimizes:
    $$ \sum_{i:x^{(i)} \in R_{left}(j,s)} (y^{(i)} - \hat{y}_{R_l})^2 + \sum_{i:x^{(i)} \in R_{right}(j,s)} (y^{(i)} - \hat{y}_{R_r})^2 $$
-   This process is repeated on the resulting child nodes until a stopping criterion is met (e.g., a minimum number of samples per leaf).

### Preventing Overfitting: Pruning

A fully grown tree (a "maximal tree") will be very deep, complex, and will severely overfit the training data. **Pruning** is the process of reducing the size of the tree to improve its performance on unseen data by reducing variance.

-   **Cost-Complexity Pruning:** The most common method.
-   **Goal:** Find a subtree `T` that minimizes a cost function that balances training error (SSR) and tree complexity (number of leaves).
    $$ \text{Cost}(T) = \sum_{j=1}^{|T|} \sum_{i:x^{(i)}\in R_j} (y^{(i)} - \hat{y}_{R_j})^2 + \alpha |T| $$
-   `|T|` is the number of leaves in the subtree `T`.
-   $\alpha$ is a **complexity hyperparameter** that penalizes larger trees. The optimal $\alpha$ is chosen using [[Cross-Validation]].

## 2. Classification Trees

Used when the target variable `y` is **qualitative** (categorical).

### Key Differences from Regression Trees
-   **Prediction:** The prediction for a leaf node is the **most common class** (the mode) of the training samples in that region.
-   **Splitting Criterion:** We can't use SSR. Instead, we use a measure of **node impurity**. The goal is to find splits that create the "purest" possible child nodes (i.e., nodes dominated by a single class).

### Splitting Criteria: Measuring Impurity

Let $\hat{p}_{jk}$ be the proportion of training observations in region $R_j$ that belong to class `k`.

-   **Gini Impurity:** Measures the total variance across classes. A small Gini index means a node is pure. This is the default in Scikit-Learn.
    $$ G_j = \sum_{k=1}^{K} \hat{p}_{jk}(1 - \hat{p}_{jk}) $$
-   **Cross-Entropy (Information Gain):** An alternative measure of impurity. It is more sensitive to small changes in class probabilities than Gini.
    $$ D_j = - \sum_{k=1}^{K} \hat{p}_{jk} \log(\hat{p}_{jk}) $$
-   **Classification Error Rate:** The proportion of training samples in a region that do not belong to the most common class. It is less sensitive for growing a tree but can be useful for pruning.
    $$ E_j = 1 - \max_{k}(\hat{p}_{jk}) $$

## 3. Variable Importance

Decision trees provide a natural way to measure the importance of each feature.
-   **Method:** The importance of a variable $x_j$ is the **total reduction in impurity** (e.g., Gini index or RSS) achieved by all splits on that variable, summed over the entire tree.
-   A high importance score means a variable was frequently used to make effective splits.

## 4. Pros and Cons of Decision Trees

### Pros
-   **Highly Interpretable:** Easy to explain and visualize ("white box" model).
-   **Mimics Human Decision-Making:** The structure is intuitive.
-   **Handles Categorical Data:** Can be used without creating dummy variables.
-   **No Feature Scaling Needed:** The splitting logic is unaffected by the scale of the features.
-   The basis for powerful ensemble methods like **[[Bagging]]**, **[[Random Forest]]**, and **[[Boosting]]**.

### Cons
-   **Prone to Overfitting:** A single deep tree has high variance. Requires careful pruning and hyperparameter tuning.
-   **Unstable:** Small changes in the training data can lead to a completely different tree structure.
-   **Greedy Algorithm:** May not find the globally optimal tree.
-   **Axis-Aligned Splits:** Can struggle to capture linear relationships or diagonal decision boundaries.