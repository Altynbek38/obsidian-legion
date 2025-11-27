
---

# Lecture 10: Classification & Logistic Regression
`tags: #ML #classification #logistic_regression`

## 1. Introduction to Classification

> **Classification** is a supervised learning task where the goal is to predict a **categorical** (discrete) target variable `y`.

-   **Examples:** Spam detection, fraud analysis, medical diagnosis.

-   **Binary Classification:** The target `y` has two possible classes, typically labeled `0` (negative class) and `1` (positive class).

-   **Multiclass Classification:** The target `y` can take one of K possible classes, where K > 2.
    $$ y \in \{0, 1, 2, ..., K\} $$

-   **Why not Linear Regression?** Using linear regression for classification is not ideal because its output can be outside the `[0, 1]` range, making it unsuitable for probability estimation.

## 2. Logistic Regression

A classification algorithm that models the probability that an input `x` belongs to a particular class.

### Hypothesis Function

The hypothesis $h_\theta(x)$ outputs the estimated probability that `y=1`. It uses the **Sigmoid (or Logistic) Function** to ensure the output is between 0 and 1.

-   **Sigmoid Function, $\sigma(z)$:** Squashes any real number to the range `(0, 1)`.
    $$ \sigma(z) = \frac{1}{1 + e^{-z}} $$
-   **Hypothesis, $h_\theta(x)$:** We feed the linear model output, $z = \theta^T x$, into the sigmoid function.
    $$ h_\theta(x) = \sigma(\theta^T x) = \frac{1}{1 + e^{-\theta^T x}} $$
-   **Interpretation:** $h_\theta(x)$ is the estimated probability $P(y=1 | x; \theta)$.

### Decision Boundary

To make a final prediction, we use a threshold on the probability (commonly 0.5).

-   **Predict `y = 1`** if $h_\theta(x) \ge 0.5$, which happens when $\theta^T x \ge 0$.
-   **Predict `y = 0`** if $h_\theta(x) < 0.5$, which happens when $\theta^T x < 0$.

> The line or surface defined by **$\theta^T x = 0$** is the **[[Decision Boundary]]** that separates the classes.

## 3. Optimization and Cost Function

To find the best parameters $\theta$, we use the principle of **Maximum Likelihood Estimation**. We want to find $\theta$ that makes our observed training data most probable.

-   **Likelihood Function $L(\theta)$:** The probability of observing all `n` data points, which is the product of individual probabilities.
    $$ L(\theta) = \prod_{i=1}^{n} P(y_i|x_i; \theta) = \prod_{i=1}^{n} h_\theta(x_i)^{y_i} (1 - h_\theta(x_i))^{1-y_i} $$
-   **Cost Function $J(\theta)$ (Log Loss / Binary Cross-Entropy):** For easier optimization, we minimize the *negative average log-likelihood*. This becomes our cost function.
    $$ J(\theta) = - \frac{1}{n} \sum_{i=1}^{n} \left[ y_i \log(h_\theta(x_i)) + (1-y_i) \log(1-h_\theta(x_i)) \right] $$
    - We use an algorithm like [[Gradient Descent]] to find the $\theta$ that **minimizes** $J(\theta)$.

## 4. Model Interpretation

### Odds & Log-Odds

While probabilities are useful, interpreting the model's coefficients ($\theta$) is easier using log-odds.

-   **Odds:** The ratio of the probability of an event happening to it not happening.
    $$ \text{odds} = \frac{P(Y=1|x)}{P(Y=0|x)} = e^{\theta^T x} $$
-   **Log-Odds (Logit):** Taking the log of the odds linearizes the relationship.
    $$ \log(\text{odds}) = \log\left( \frac{p}{1-p} \right) = \theta^T x $$
    - **Advantage:** The log-odds change linearly with the features `x`. A one-unit increase in $x_j$ changes the log-odds by $\theta_j$.

## 5. Multi-Class Classification

### One-vs-Rest (OvR)

-   **Strategy:** Train `K` separate binary logistic regression classifiers. For each class `k`, a model is trained to distinguish `k` (positive) from all other classes (negative).
-   **Prediction:** For a new input, predict the class `k` corresponding to the classifier with the highest output probability.
-   **Drawback:** The predicted probabilities from the K models are not guaranteed to sum to 1.

### Softmax Regression

-   **Strategy:** A direct generalization of logistic regression for multi-class problems.
-   **Process:**
    1.  Calculate a linear score for each class: $z_k = \theta_k^T x$.
    2.  Use the **[[Softmax]] function** to convert scores into a probability distribution.
        $$ P(y=k|x) = \frac{e^{z_k}}{\sum_{j=1}^{K} e^{z_j}} $$
-   **Advantage:** The output is a vector of probabilities that sum to 1, providing a valid probabilistic interpretation.

## 6. Evaluation: The Confusion Matrix

A table that summarizes the performance of a classification model.

|                | **Actual: Positive** | **Actual: Negative** |
| :------------- | :------------------: | :------------------: |
| **Pred: Pos**  |   True Positive (TP)   |  False Positive (FP)   |
| **Pred: Neg**  |  False Negative (FN)   |   True Negative (TN)   |

-   **TP:** Correctly predicted positive.
-   **TN:** Correctly predicted negative.
-   **FP (Type I Error):** Incorrectly predicted positive (a "false alarm").
-   **FN (Type II Error):** Incorrectly predicted negative (a "miss").