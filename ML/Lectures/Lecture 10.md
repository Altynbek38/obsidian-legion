
---

# Lecture 9: Logistic Regression and Classification

`tags: #ML #SupervisedLearning #Classification`

## 1. Introduction to Classification

-   **Goal**: Predict a **categorical** target variable `y`.
-   **Binary Classification**: Two possible outcomes.
    -   Usually labeled `0` (negative class) and `1` (positive class).
    -   *Examples*: Spam vs. Ham, Malignant vs. Benign tumor.
-   **Multiclass Classification**: More than two possible outcomes.
    -   *Examples*: 'Bad', 'average', 'good' students; different nationalities.

## 2. Why Not Use Linear Regression?

Using [[Linear Regression]] for classification is a bad idea because:
1.  The output is not a probability. It can produce values greater than 1 or less than 0.
2.  It is not well-suited for fitting the non-linear, step-like nature of classification data.

## 3. The Logistic Regression Model

To solve the issues with linear regression, we use a function that "squashes" the output into a `[0, 1]` range.

-   **Hypothesis Function**: The core of logistic regression is the **Sigmoid Function** (or Logistic Function).

    ```
    f_θ(x) = σ(θᵀx)
    ```

-   **Sigmoid Function `σ(z)`**:
    ```
    σ(z) = 1 / (1 + e⁻ᶻ)
    ```
    Where `z = θᵀx` is the output of a linear model. The sigmoid function has an "S" shape and maps any real number to a value between 0 and 1.

> [!NOTE] Interpretation
> The output `f_θ(x)` is the **estimated probability** that `y=1` given the input `x`.
> `f_θ(x) = P(y=1 | x; θ)`

## 4. The Decision Boundary

To make a final prediction (0 or 1), we use a threshold on the probability.
-   **Rule**:
    -   Predict `y = 1` if `f_θ(x) ≥ 0.5`
    -   Predict `y = 0` if `f_θ(x) < 0.5`
-   This is equivalent to:
    -   Predict `y = 1` if `θᵀx ≥ 0`
    -   Predict `y = 0` if `θᵀx < 0`
-   The **decision boundary** is the line (or hyperplane) where `θᵀx = 0`.

## 5. Optimization: The Cost Function

To train the model (i.e., find the best parameters `θ`), we need a cost function to minimize.
-   **Principle**: We use **Maximum Likelihood Estimation (MLE)**, which finds the parameters `θ` that maximize the probability of observing the training data.
-   **Cost Function (Log Loss / Binary Cross-Entropy)**: Minimizing this function is the same as maximizing the likelihood.
    ```
    J(θ) = -1/m * Σ [yᵢ log(f_θ(xᵢ)) + (1 - yᵢ) log(1 - f_θ(xᵢ))]
    ```
-   We use an algorithm like [[Gradient Descent]] to find the `θ` that **minimizes** this cost function `J(θ)`.

## 6. Interpretation via Log-Odds

While the probability `f_θ(x)` is non-linear, we can transform it to make it linearly interpretable.
-   **Odds**: The ratio of the probability of an event happening to it not happening.
    -   `Odds = P(y=1) / P(y=0)`
-   **Log-Odds (Logit)**: The logarithm of the odds.
    -   The key insight is that the log-odds are **linear** in `x`: `log(Odds) = θᵀx`.

> [!INFO] Why Log-Odds are Useful
> A one-unit increase in a feature `xⱼ` changes the log-odds by `θⱼ`. This makes the model's coefficients directly interpretable in a linear way.

## 7. Multiclass Classification Strategies

How to extend binary classification to `K` classes.
-   **One-vs-Rest (OvR)**:
    -   Train `K` separate binary classifiers.
    -   Classifier `k` learns to distinguish "class `k`" from "all other classes".
    -   To predict, choose the class `k` whose classifier gives the highest output score.
-   **Softmax Regression**:
    -   A generalization of the logistic function for multiple classes.
    -   It calculates a score `zₖ = θₖᵀx` for each class `k`.
    -   The **Softmax function** converts these scores into a probability distribution (all probabilities sum to 1).
        ```
        pₖ = eᶻᵏ / (Σ eᶻᵢ)
        ```

## 8. Evaluating Performance: The Confusion Matrix

A table used to describe the performance of a classification model.
-   **True Positive (TP)**: Predicted: **True**, Actual: **True**. (Correctly identified positive)
-   **True Negative (TN)**: Predicted: **False**, Actual: **False**. (Correctly identified negative)
-   **False Positive (FP)**: Predicted: **True**, Actual: **False**. (Type I Error)
-   **False Negative (FN)**: Predicted: **False**, Actual: **True**. (Type II Error)