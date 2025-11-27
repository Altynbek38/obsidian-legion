Of course. Here are the summarized notes from your lecture slides, formatted for Obsidian.

---

# Lecture 9: Introduction to Classification & Logistic Regression
`tags: #ML #classification #logistic_regression`

## 1. Introduction to Classification

> **Classification** is a type of supervised learning where the goal is to predict a **categorical** target variable `y`.

-   **Examples:**
    -   Spam detection (spam/ham)
    -   Fraud detection (fraud/safe)
    -   Tumor diagnosis (malignant/benign)

### Types of Classification

-   **[[Binary Classification]]:** The target variable `y` has only two possible outcomes.
    -   Conventionally noted as `0` (negative class) and `1` (positive class).
    -   Example: `y = 0` (normal rhythm), `y = 1` (atrial fibrillation).

-   **Multiclass Classification:** The target variable `y` has more than two possible outcomes.
    $$ y \in \{0, 1, 2, ..., K\}, \text{ where } K \ge 2 $$

### Why Not Use Linear Regression?

-   If we fit a [[Linear Regression]] model to a classification problem, the output $h_\theta(x)$ can be greater than 1 or less than 0.
-   This makes it difficult to interpret the output as a probability, which should be constrained to the range `[0, 1]`.

## 2. Logistic Regression

A classification algorithm that models the probability of a discrete outcome.

### Hypothesis Function

The hypothesis $h_\theta(x)$ is modeled using the **Sigmoid Function** (also called the **Logistic Function**). This function squashes any real-valued input `z` into the `[0, 1]` range.

-   **Sigmoid Function $\sigma(z)$:**
    $$ \sigma(z) = \frac{1}{1 + e^{-z}} $$
-   **Logistic Regression Hypothesis $h_\theta(x)$:** We set $z = \theta^T x$.
    $$ h_\theta(x) = \sigma(\theta^T x) = \frac{1}{1 + e^{-\theta^T x}} $$

### Interpretation of the Hypothesis

> The output of the hypothesis, $h_\theta(x)$, is the **estimated probability** that the output `y` is 1, given the input `x` and parameters `\theta`.

$$ h_\theta(x) = P(y=1 | x; \theta) $$
-   Since there are only two classes, the probability of `y=0` is:
    $$ P(y=0 | x; \theta) = 1 - P(y=1 | x; \theta) $$

### Decision Boundary

To make a final prediction (0 or 1), we use a threshold, typically 0.5.

-   **Predict `y = 1` if:** $h_\theta(x) \ge 0.5$
    -   This occurs when the input to the sigmoid function is non-negative: $\theta^T x \ge 0$.
-   **Predict `y = 0` if:** $h_\theta(x) < 0.5$
    -   This occurs when the input to the sigmoid function is negative: $\theta^T x < 0$.

> The equation $\theta^T x = 0$ defines the **[[Decision Boundary]]**, which is a line or plane that separates the two classes.

## 3. Optimization: Finding the Parameters $\theta$

We need a [[Cost Function]] to measure how well the model fits the training data. We find the parameters $\theta$ by minimizing this cost function.

### Likelihood

The probability of observing a specific label `y` for a given `x` can be written compactly as:
$$ p(y|x; \theta) = (h_\theta(x))^y (1 - h_\theta(x))^{1-y} $$

The **likelihood** of the parameters $\theta$ given the entire dataset is the product of these probabilities for all `n` training examples. Our goal is to find $\theta$ that maximizes this likelihood.
$$ L(\theta) = \prod_{i=1}^{n} p(y_i|x_i; \theta) = \prod_{i=1}^{n} h_\theta(x_i)^{y_i} (1 - h_\theta(x_i))^{1-y_i} $$

### Cost Function (Log Loss / Binary Cross-Entropy)

Maximizing the likelihood is equivalent to maximizing the log-likelihood (which is computationally easier) or **minimizing the negative average log-likelihood**. This gives us our cost function $J(\theta)$.

$$ J(\theta) = - \frac{1}{n} \sum_{i=1}^{n} \left[ y_i \log(h_\theta(x_i)) + (1-y_i) \log(1-h_\theta(x_i)) \right] $$

> We use an optimization algorithm like [[Gradient Descent]] to find the parameters $\theta$ that **minimize** this cost function $J(\theta)$.

## 4. Model Interpretation

### Odds

Odds represent the ratio of the probability of an event occurring to the probability of it not occurring.
$$ \text{odds} = \frac{P(Y=1|x)}{P(Y=0|x)} = \frac{h_\theta(x)}{1-h_\theta(x)} = e^{\theta^T x} $$
-   Odds are exponential and can be hard to interpret directly.

### Log-Odds (Logit)

To linearize the relationship, we take the natural logarithm of the odds. This is also called the **logit function**.
$$ \log(\text{odds}) = \log\left( \frac{p}{1-p} \right) = \theta^T x $$
-   **Interpretation:** A one-unit increase in a feature $x_j$ changes the **log-odds** by its corresponding coefficient $\theta_j$. This provides a linear and more intuitive interpretation of the model's parameters.
-   A positive log-odds means probability > 50%.
-   A negative log-odds means probability < 50%.

## 5. Multi-Class Classification

Handling problems where $y \in \{0, 1, ..., K\}$ with $K > 2$.

### One-vs-Rest (OvR) or One-vs-All (OvA)

-   **Strategy:** Train $K$ independent binary logistic regression classifiers. For each class `k`, a classifier is trained to distinguish class `k` (positive) from all other classes (negative).
-   **Prediction:** For a new input `x`, apply all $K$ classifiers and predict the class `k` which has the highest output probability.
    $$ \text{prediction} = \arg\max_{k} h_\theta^{(k)}(x) $$
-   **Drawback:** The resulting probabilities from each classifier are not guaranteed to sum to 1.

### Softmax Regression (Multinomial Logistic Regression)

-   **Strategy:** A generalization of logistic regression that handles multiple classes directly.
-   **Process:**
    1.  For each class `k`, calculate a linear score: $z_k = \theta_k^T x$.
    2.  Apply the **[[Softmax]] function** to convert the scores $z = [z_1, ..., z_K]$ into a probability distribution. The probability for class `k` is:
        $$ p_k = \text{softmax}(z_k) = \frac{e^{z_k}}{\sum_{j=1}^{K} e^{z_j}} $$
-   **Advantage:** The output is a vector of probabilities $[p_1, ..., p_K]$ that are guaranteed to sum to 1, providing a valid probabilistic interpretation.

## 6. Evaluation Metrics

### [[Confusion Matrix]]

A table used to describe the performance of a classification model on a set of test data for which the true values are known.

|                | **Actual: Positive** | **Actual: Negative** |
| :------------- | :------------------: | :------------------: |
| **Pred: Pos**  |   True Positive (TP)   |  False Positive (FP)   |
| **Pred: Neg**  |  False Negative (FN)   |   True Negative (TN)   |

-   **TP:** Model correctly predicts the positive class.
-   **TN:** Model correctly predicts the negative class.
-   **FP (Type I Error):** Model incorrectly predicts the positive class.
-   **FN (Type II Error):** Model incorrectly predicts the negative class.