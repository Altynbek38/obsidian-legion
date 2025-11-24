
***

# Classification & Logistic Regression
#ML #SupervisedLearning #Classification #LogisticRegression

## 1. Classification Basics
In classification, the target variable **$y$** is categorical.
*   **Binary Classification:** $y \in \{0, 1\}$ (e.g., 0: Negative/Normal, 1: Positive/Disease).
*   **Multiclass Classification:** $y \in \{0, 1, ..., K\}$ where $K \ge 2$ (e.g., Image recognition categories).

**Why not Linear Regression?**
Fitting a linear line ($f(x) = \theta^T x$) does not work well because predictions can fall outside the range $[0,1]$.

---

## 2. Logistic Regression Model
To ensure predictions stay between 0 and 1, we map the linear output through a **Sigmoid Function**.

### The Sigmoid Function
$$ \sigma(z) = \frac{1}{1 + e^{-z}} $$
*   **Range:** $[0, 1]$
*   **Hypothesis:** $f_\theta(x) = \sigma(\theta^T x) = \frac{1}{1 + e^{-\theta^T x}}$
*   **Interpretation:** $f_\theta(x)$ is the estimated probability that $y=1$.
    $$ f_\theta(x) = P(y=1 | x; \theta) $$

### Classification Rule
We predict the class based on a threshold (usually 0.5):
> [!info] Decision Boundary
> *   **Predict $y=1$** if $f_\theta(x) \ge 0.5$ (implies $\theta^T x \ge 0$)
> *   **Predict $y=0$** if $f_\theta(x) < 0.5$ (implies $\theta^T x < 0$)

---

## 3. Cost Function & Optimization
We cannot use Least Squares. Instead, we use **Maximum Likelihood Estimation (MLE)** to find parameters $\theta$ that maximize the likelihood of the observed data.

### Log-Likelihood
We maximize the Log-Likelihood:
$$ \mathcal{L}(\theta) = \sum_{i=1}^n [y_i \log(\hat{y}_i) + (1-y_i)\log(1-\hat{y}_i)] $$

### Cost Function (to Minimize)
By taking the negative average of the log-likelihood, we get the cost function to minimize:
$$ \mathcal{L}(\theta) = - \frac{1}{n} \sum_{i=1}^n [y_i \log(\hat{y}_i) + (1-y_i)\log(1-\hat{y}_i)] $$

---

## 4. Interpretation: Odds and Log-Odds
Logistic regression models the relationship between the predictors and the probability of success.

### Odds
The ratio of the probability of success to the probability of failure.
$$ \text{Odds} = \frac{P(y=1|x)}{P(y=0|x)} = e^{\theta^T x} $$
*   **Range:** $[0, +\infty)$
*   Interpretation is exponential (harder to intuit directly).

### Log-Odds (Logit)
By taking the log of the odds, we linearize the relationship.
$$ \log(\text{Odds}) = \theta^T x $$
*   **Range:** $(-\infty, +\infty)$
*   **Advantage:** Linearly related to $x$. If $x$ increases by 1, the **log-odds** increase by $\theta$.

---

## 5. Multiclass Classification
When $K > 2$ (more than two categories).

### Method A: One Versus Rest (OVR)
*   Train **$K$** separate binary classifiers.
*   For each classifier, one class is Positive ($k$) and all others are Negative.
*   **Prediction:** Choose the class $k$ that yields the highest score ($\max f_k(x)$).
*   *Downside:* Loses valid probabilistic interpretation.

### Method B: Softmax
*   Generalizes the sigmoid function for vectors.
*   Converts a vector of raw scores $z$ into a probability distribution.
$$ p_k = \text{softmax}(z_k) = \frac{e^{z_k}}{\sum_{j=1}^K e^{z_j}} $$
*   Ensures all probabilities sum to 1.

---

## 6. Metrics: Confusion Matrix
A table used to evaluate the performance of a classification model.

| | Actual Positive (1) | Actual Negative (0) |
|---|---|---|
| **Predicted Positive (1)** | **True Positive (TP)** | **False Positive (FP)** |
| **Predicted Negative (0)** | **False Negative (FN)** | **True Negative (TN)** |

*   **TP:** Correctly predicted true.
*   **TN:** Correctly predicted false.
*   **FP (Type I Error):** Model predicted True, but it was actually False.
*   **FN (Type II Error):** Model predicted False, but it was actually True.