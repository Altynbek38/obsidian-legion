
---

# Lecture 11: Evaluation Metrics, Cross-Validation & Hyperparameter Tuning
`tags: #ML #evaluation #cross_validation #hyperparameters`

This lecture covers how to evaluate classification models, ensure those evaluations are reliable, and tune the models for optimal performance.

## 1. Classification Metrics

Metrics are used to evaluate the performance of a classification model. The choice of metric depends on the specific problem and the business objective. All metrics are derived from the [[Confusion Matrix]].

### The Confusion Matrix

A table that summarizes a model's predictions against the actual true labels.

|                | **Actual: Positive** | **Actual: Negative** |
| :------------- | :------------------: | :------------------: |
| **Pred: Pos**  |   True Positive (TP)   |  False Positive (FP)   |
| **Pred: Neg**  |  False Negative (FN)   |   True Negative (TN)   |

-   **TP:** Correctly identified as positive.
-   **TN:** Correctly identified as negative.
-   **FP (Type I Error):** Incorrectly identified as positive (e.g., a safe transaction flagged as fraud).
-   **FN (Type II Error):** Incorrectly identified as negative (e.g., a fraudulent transaction missed).

### Core Metrics

-   **Accuracy:** The fraction of all predictions that were correct.
    > **Use when:** Classes are balanced and all errors (FP, FN) have similar costs.
    > **Warning:** Can be misleading on imbalanced datasets.
    $$ \text{Accuracy} = \frac{TP + TN}{TP + TN + FP + FN} $$

-   **Precision:** Of all the positive predictions made, how many were actually correct.
    > **Use when:** The cost of **False Positives** is high (e.g., spam detection, flagging mishandled baggage). You want to be sure when you predict positive.
    $$ \text{Precision} = \frac{TP}{TP + FP} $$

-   **Recall (Sensitivity or True Positive Rate):** Of all the actual positive instances, how many did the model correctly identify.
    > **Use when:** The cost of **False Negatives** is high (e.g., medical diagnosis of a disease). You want to find all the positives.
    $$ \text{Recall} = \frac{TP}{TP + FN} $$

-   **F1-Score:** The harmonic mean of Precision and Recall.
    > **Use when:** You need a balance between Precision and Recall, especially on **imbalanced datasets**.
    $$ \text{F1-Score} = 2 \cdot \frac{\text{Precision} \cdot \text{Recall}}{\text{Precision} + \text{Recall}} $$

### Threshold-Based Metrics

Classification models often output a probability. A **threshold** is used to convert this probability into a class label (e.g., if prob > 0.5, predict 1). These metrics evaluate the model across *all* possible thresholds.

-   **ROC-AUC Curve (Receiver Operating Characteristic - Area Under Curve):**
    -   Plots **True Positive Rate (Recall)** vs. **False Positive Rate** at all thresholds.
    -   **FPR:** The fraction of actual negatives that were incorrectly classified as positive. $FPR = \frac{FP}{FP+TN}$.
    -   **Interpretation:** A good model has a curve that bows towards the top-left corner. The **AUC** score (Area Under the Curve) summarizes the curve in one number:
        -   AUC = 1: Perfect classifier.
        -   AUC = 0.5: Random (useless) classifier.

-   **Precision-Recall (PR) Curve:**
    -   Plots Precision vs. Recall at all thresholds.
    -   More informative than ROC-AUC on highly **imbalanced datasets**.

## 2. Cross-Validation

> **[[Cross-Validation]]** is a technique for assessing how a model will generalize to new, unseen data. It provides a more reliable performance estimate than a single train-test split.

### K-Fold Cross-Validation

-   **Process:**
    1.  Split the dataset into `k` equal-sized subsets (or "folds").
    2.  Train the model on `k-1` folds.
    3.  Validate (test) the model on the remaining fold.
    4.  Repeat this process `k` times, with each fold serving as the validation set once.
    5.  The final performance is the average of the performance across all `k` folds.
-   **Pros:** Reduces overfitting risk, more robust evaluation.
-   **Cons:** Can be computationally expensive, may not preserve class balance in folds.

### Stratified K-Fold Cross-Validation

-   **Process:** Same as K-Fold, but it ensures that the **class distribution** (percentage of each class) is the same in each fold as it is in the overall dataset.
-   **Use when:** This is the standard for classification problems, especially with imbalanced data.
-   **Pros:** Preserves class balance, leading to more reliable and representative evaluation.

## 3. Hyperparameter Tuning

> A **hyperparameter** is a configuration that is set *before* the learning process begins (e.g., learning rate, number of folds in CV). Tuning is the process of finding the optimal hyperparameters for a model.

### The Challenge

The number of hyperparameters can be large, and evaluating each combination is computationally expensive. There is no single "best" value; it depends on the data.

### Tuning Methods

-   **Grid Search:**
    -   **Strategy:** Define a discrete set of values for each hyperparameter you want to tune. The algorithm exhaustively trains and evaluates the model on **every possible combination** of these values.
    -   **Pros:** Simple and comprehensive (within the defined grid).
    -   **Cons:** Very slow and computationally expensive. Suffers from the "curse of dimensionality."

-   **Random Search:**
    -   **Strategy:** Define a *range* or statistical distribution for each hyperparameter. The algorithm randomly samples a fixed number of combinations from this search space.
    -   **Pros:** Much more efficient than Grid Search. Often finds better or comparable results in less time.
    -   **Cons:** Not guaranteed to find the absolute best combination.