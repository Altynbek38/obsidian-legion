
### **Part 1: The Definition of a Supervised Learning Model**

#### **1.1 The Core Goal**
The goal of supervised learning is to learn a **mapping** function, `f`, that takes inputs `x` and maps them to outputs `y`. This is done using a **training set**, `D`, which is a collection of labeled input-output pairs.

*   **Training Set:** `D = {(xᵢ, yᵢ)}` for `i=1 to n`

*   **Components:**
    *   `D`: The full training dataset.
    *   `n`: The total number of training examples.
    *   `xᵢ`: The input, which is a vector of **features** (also called attributes or explanatory variables). These are often organized in an `n x p` design matrix, where `p` is the number of features.
    *   `yᵢ`: The output or **response variable**. This is the value we want to predict.

Since we know the true value of `yᵢ` in our training data, we can compare our model's predictions to the actual values and compute **error metrics**.

#### **1.2 Types of Supervised Learning Problems**

The type of problem is determined by the nature of the response variable `y`:

*   **Classification:**
    *   **When:** The response variable `y` is **categorical** (i.e., it belongs to a finite set of classes).
    *   **Examples:** Detecting if an email is spam or ham, face detection in an image, market segmentation.

*   **Regression:**
    *   **When:** The response variable `y` is a **real-valued scalar** (a continuous number).
    *   **Examples:** Predicting the wage of an individual, forecasting the value of a financial asset, predicting the temperature in a building.

#### **1.3 The Underlying Theoretical Model**
In supervised learning, we assume there is a true, but unknown, relationship between `x` and `y`. We can express this as:

*   **Formula:** `y = f(x) + ε`
    *   `f(x)`: The true, systematic information that `x` provides about `y`. This is the function we want to estimate.
    *   `ε`: A random **error term**, which is independent of `x` and has a mean of zero. It represents the unpredictable or unmeasured variation in `y`.

---

### **Part 2: Bias, Variance, and Prediction Error**

The goal of machine learning is to create an estimate, `f̂(x)`, that is as close as possible to the true function `f(x)`. The error of our model can be broken down.

#### **2.1 Bias**
*   **Definition:** The systematic error in a model's predictions. It measures how far off the *average* prediction is from the correct value. Bias is caused by incorrect assumptions in the learning algorithm (e.g., assuming a linear relationship when it is actually non-linear).
*   **Formula:** `Bias(x) = E[f̂(x)] - f(x)`
*   **Key Idea:** **High Bias ⇒ Underfitting**. An underfit model is too simple and fails to capture the underlying structure of the data.

#### **2.2 Variance**
*   **Definition:** Measures the sensitivity of the model to variations in the training data. It describes how much the model's prediction `f̂(x)` would change if we trained it on a different training set.
*   **Formula:** `Var(f̂(x)) = E[(f̂(x) - E[f̂(x)])²]`
*   **Key Idea:** **High Variance ⇒ Overfitting**. An overfit model is too complex and learns the random noise in the training data instead of the true signal. It performs poorly on new, unseen data.

#### **2.3 The Bias-Variance Trade-off**
The total error of a model is a combination of bias, variance, and an irreducible error.

*   **Expected Prediction Error (EPE):** `EPE = E[(y - ŷ)²] = Reducible Error + Irreducible Error`
    *   **Irreducible Error (`Var(ε)`):** The noise inherent in the data itself. No model, no matter how good, can reduce this error.
    *   **Reducible Error:** The error that we can control and minimize by selecting a better model.
        *   **Formula:** `Reducible Error = [Bias(f̂(X))]² + Var(f̂(X))`

This creates the **Bias-Variance Trade-off**:
*   Simple models tend to have **high bias** and low variance.
*   Complex models tend to have **low bias** and high variance.
The goal of machine learning is to find a model that has the best balance of bias and variance, thereby minimizing the total reducible error.

---

### **Part 3: The Purpose of Estimating *f***

There are two primary reasons why we want to estimate the function `f`:

1.  **Prediction:** We want to accurately predict the output `y` for new inputs `x`. In this case, our estimated function `f̂` can be treated as a **black box**. We care about its predictive accuracy, not its exact form.

2.  **Inference:** We want to understand the relationship between the inputs `x` and the output `y`. The goal is not just to predict, but to know *how* `y` is affected by changes in `x`. Key questions for inference include:
    *   Which predictors are most important?
    *   What is the magnitude and sign (positive or negative) of the relationship?
    *   Is the relationship linear or non-linear?

This leads to the **Accuracy vs. Interpretability Trade-off**. Highly complex and flexible models (like neural networks) may be very accurate but hard to interpret. Simpler models (like linear regression) are highly interpretable but may sacrifice some accuracy.

---

### **Part 4: Model Fitting and Selection**

*   **Underfitting (High Bias):** The model is too simple and fails to capture the underlying trend. It performs poorly on both training and test data.
*   **Good Fit/Robust:** The model successfully captures the underlying trend without fitting the noise.
*   **Overfitting (High Variance):** The model is too complex and fits the random noise in the training data. It performs very well on training data but poorly on new (test) data.

This is often visualized with a **Train and Test Loss Curve**. As model complexity increases, the training loss will always decrease. However, the test loss will decrease to a certain point and then start to rise as the model begins to overfit. The optimal model is at the point where the test loss is at its minimum.

---

### **Part 5: The Cost (or Loss) Function**

#### **5.1 Definition**
A **Cost Function** (or **Loss Function**) measures the performance of a model. It quantifies the error between the predicted values (`ŷ`) and the expected values (`y`) into a single real number. The goal of training a model is to find the parameters that minimize this function.

#### **5.2 Common Loss Functions**

*   **For Regression Problems:**
    *   **Mean Squared Error (MSE):** `MSE = (1/n) * Σ(yᵢ - ŷᵢ)²`
        *   Penalizes larger errors more heavily due to the squaring.
    *   **Mean Absolute Error (MAE):** `MAE = (1/n) * Σ|yᵢ - ŷᵢ|`
        *   Less sensitive to outliers than MSE.

*   **For Binary Classification Problems:**
    *   **Misclassification Rate:** `L(θ) = (1/n) * Σ I(yᵢ ≠ ŷᵢ)`
        *   Simply the proportion of incorrect predictions.
    *   **Binary Cross-Entropy Loss:** `L(θ) = -(1/n) * Σ [yᵢ log(ŷᵢ) + (1 - yᵢ) log(1 - ŷᵢ)]`
        *   The standard for classification when the model outputs probabilities. It heavily penalizes confident but incorrect predictions.