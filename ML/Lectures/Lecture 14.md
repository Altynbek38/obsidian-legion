
---
# Lecture 13: Ensemble Methods - Bagging & Random Forest
`tags: #ML #ensemble #bagging #random_forest #bootstrapping`

> **Core Idea:** Ensemble methods combine multiple simple models (called "weak learners") to produce a single, more powerful and robust model. The main weakness of a single [[Decision Tree]]—high variance—can be significantly reduced using these techniques.

## 1. The Foundation: Bootstrapping

> **Bootstrapping** is a resampling technique used to estimate the uncertainty (like the standard error or confidence interval) of a statistic when we only have one sample of data.

It answers the question: "How much would my result change if I could draw another sample from the population?"

### How it Works
1.  **Sample with Replacement:** From your original dataset of size `n`, create a new "bootstrap sample" of the same size `n` by drawing observations *with replacement*. This means some original data points may appear multiple times, while others may not appear at all.
2.  **Repeat:** Generate a large number (`B`) of these independent bootstrap samples.
3.  **Calculate Statistic:** For each of the `B` bootstrap samples, calculate the statistic of interest (e.g., the mean, a regression coefficient).
4.  **Estimate Uncertainty:** The distribution of these `B` statistics gives you an estimate of the sampling distribution of your statistic, from which you can calculate its variability.

## 2. Bagging (Bootstrap Aggregating)

> **Bagging** is an ensemble method that applies the [[Bootstrapping]] technique to machine learning models, primarily to reduce variance.
> **Bagging = Bootstrap + Aggregating**

### The Bagging Algorithm
1.  **Bootstrap:** Generate `B` independent bootstrap samples from the original training data.
2.  **Train:** Train a separate model (typically a deep, unpruned [[Decision Tree]]) on each of the `B` bootstrap samples. This results in `B` different models.
3.  **Aggregate:** For a new data point, make a prediction using all `B` models and combine the results.
    -   **For Regression:** The final prediction is the **average** of the predictions from all `B` trees.
    -   **For Classification:** The final prediction is the **majority vote** (the most common class) from all `B` trees.

### Why Bagging Works
-   Single decision trees are **low-bias, high-variance** models.
-   Averaging a set of independent (or nearly independent) observations reduces variance.
-   By training trees on different bootstrap samples, we create models that are different enough that averaging their outputs significantly reduces the overall variance of the final prediction, leading to better accuracy and stability.
-   The main downside is the **loss of interpretability**; you can no longer visualize a single tree.

## 3. Random Forest: Improving on Bagging

> **Random Forest** is an extension of bagging that further improves performance by **decorrelating** the trees in the ensemble.
> **Random Forest = Bagging + Feature Subsampling**

### The Problem with Bagging
If the dataset has one very strong predictor, most or all of the bagged trees will use that feature for their top split. This causes the trees to be structurally similar and their predictions to be **highly correlated**. Averaging highly correlated results does not reduce variance effectively.

### The Random Forest Algorithm
The algorithm is the same as Bagging, with one key difference:
1.  Generate `B` bootstrap samples.
2.  Train a decision tree on each sample.
3.  **At each split in the tree**, instead of considering all `P` features, **randomly select a subset of `m` features** and only consider those for the split.
4.  Aggregate the predictions as in bagging.

-   **Hyperparameter `m`:** The number of features to consider at each split. A common heuristic is $m \approx \sqrt{P}$.
-   Note: If $m=P$, Random Forest is identical to Bagging.

### Why Random Forest Works Better
-   By restricting the choice of features at each split, Random Forest prevents strong predictors from dominating every tree.
-   This forces other, weaker predictors to be chosen, resulting in a wider variety of tree structures.
-   This process **decorrelates** the trees, meaning their errors are less likely to be the same. When their uncorrelated predictions are averaged, the variance is reduced even more effectively than with bagging.

## 4. Key Features of Random Forests

-   **Out-of-Bag (OOB) Error Estimation:**
    -   Since each tree is trained on a bootstrap sample, on average it only sees about **2/3** of the original data. The remaining **1/3** are "out-of-the-bag" (OOB) for that tree.
    -   To get a prediction for any data point `i`, we can use only the trees that did *not* have `i` in their bootstrap sample.
    -   The OOB error is the average error calculated from these OOB predictions. It serves as a valid estimate of the test error **without needing explicit [[Cross-Validation]]**.

-   **Overfitting:**
    -   Increasing the number of trees (`B`) does **not** cause the model to overfit. The error rate will converge as `B` gets large.
    -   Using very deep trees can still lead to some overfitting, but it's much less severe than with a single tree because of the averaging process.

### Summary of Advantages & Disadvantages

-   **Advantages:**
    -   Generally high predictive accuracy.
    -   Robust and less prone to overfitting than single trees.
    -   Handles non-linearities and interactions well.
-   **Disadvantages:**
    -   Becomes a "black box" model, losing the simple interpretability of a single tree.