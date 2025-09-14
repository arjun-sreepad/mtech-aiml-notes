# 📘 Linear Regression – Complete Notes

This document covers **Linear Regression fundamentals**, including assumptions, cost function, optimization, and error metrics (MSE, RMSE, MAE).  
It is structured step by step with explanations and examples.

---

## 🔹 1. Assumptions of Linear Regression

Before applying Linear Regression, certain assumptions must hold:

### 1. Linearity
- Relationship between predictors (X) and target (Y) must be linear.  
- *Example*: Study hours vs exam score often increases linearly.

### 2. Independence of Errors
- Residuals should be independent of each other.  
- *Example*: In stock prices, today’s error should not depend on yesterday’s error.

### 3. Homoscedasticity (Constant Variance of Errors)
- Spread of residuals should be roughly constant across all levels of X.  
- *Example*: Predicting house prices should not have tiny errors for cheap houses and huge errors for expensive houses.

### 4. Normality of Residuals
- Residuals should follow a normal distribution.  
- Important for hypothesis testing and confidence intervals.  
- *Example*: Exam score prediction errors cluster around 0.

### 5. No Multicollinearity
- Independent variables should not be highly correlated with each other.  
- *Example*: House size and number of bedrooms are strongly correlated → violates this assumption.

### 6. Mean of Residuals = 0
- On average, positive and negative errors should cancel out.  
- *Example*: If salary predictions are always underestimated by 1000 AED, mean residual ≠ 0.

### 7. No Endogeneity
- Predictors should not correlate with residuals.  
- *Example*: Omitting "innate ability" in income prediction biases coefficients.

### 8. Fixed Independent Variables
- Predictors should be measured without error.  
- *Example*: Measuring height with a faulty tape violates this assumption.

---

## 🔹 2. Cost Function in Linear Regression

The **Cost Function** measures how far predictions are from actual values.  
The most common is **Mean Squared Error (MSE)**:

<img src="https://latex.codecogs.com/svg.latex?J(\beta)=\frac{1}{n}\sum_{i=1}^{n}(y_i-\hat{y}_i)^2" />

- Lower cost = better fit.  
- The goal of regression is to minimize this cost.

---

## 🔹 3. Global Minimum

- The cost function is typically **U-shaped (convex)**.  
- The **global minimum** is the lowest point where the cost is smallest.  
- At this point, coefficients (β) represent the best-fit regression line.

---

## 🔹 4. Gradient Descent Algorithm

**Gradient Descent** is an optimization method to reach the global minimum.

### Formula

<img src="https://latex.codecogs.com/svg.latex?\beta_j=\beta_j-\alpha\frac{\partial%20J}{\partial%20\beta_j}" />

Where:
- α = learning rate  
- ∂J/∂βⱼ = gradient (slope)

### Steps
1. Start with random coefficients.  
2. Compute gradient of cost function.  
3. Update coefficients in the opposite direction.  
4. Repeat until convergence.

---

## 🔹 5. Learning Rate (α)

- Controls step size in gradient descent.  

### Cases
- **Too Small (α ↓)** → Converges slowly.  
- **Too Large (α ↑)** → Overshoots, may never converge.  
- **Just Right** → Efficient convergence to global minimum.

*Example*: Walking down a valley:  
- Small steps → reach bottom very slowly.  
- Large jumps → risk bouncing around, never settling.  
- Balanced steps → reach bottom smoothly.

---

## 🔹 6. Error Metrics

### 1. Mean Squared Error (MSE)

<img src="https://latex.codecogs.com/svg.latex?MSE=\frac{1}{n}\sum_{i=1}^{n}(y_i-\hat{y}_i)^2" />

- Penalizes large errors heavily.  
- Units are squared → not intuitive.  
- Very sensitive to outliers.

---

### 2. Root Mean Squared Error (RMSE)

<img src="https://latex.codecogs.com/svg.latex?RMSE=\sqrt{MSE}" />

- Same unit as target variable (interpretable).  
- Still punishes large errors.  
- Popular in real-world regression problems.

---

### 3. Mean Absolute Error (MAE)

<img src="https://latex.codecogs.com/svg.latex?MAE=\frac{1}{n}\sum_{i=1}^{n}|y_i-\hat{y}_i|" />

- Average of absolute errors.  
- A more **robust** metric when data has outliers.  
- Easy to interpret as “average error.”

---

## 🔹 7. Advantages & Disadvantages

| Metric | Advantages | Disadvantages |
|--------|------------|---------------|
| **MSE**  | Smooth, good for optimization, punishes large errors | Units squared, sensitive to outliers |
| **RMSE** | Same units as target, interpretable, punishes large errors | Sensitive to outliers |
| **MAE**  | Robust to outliers, simple to explain | Doesn’t emphasize large errors, less smooth for optimization |

---

## 🔹 8. Which One to Use?

- **MSE** → When **large mistakes are very costly**.  
  *Example*: Predicting aircraft engine failure time (catastrophic if wrong).  

- **RMSE** → When you need **interpretability** and want to penalize big mistakes more.  
  *Example*: Predicting house prices (e.g., "off by 20,000 AED on average").  

- **MAE** → When **outliers exist** and you want a **robust average miss**.  
  *Example*: Predicting taxi fares (one luxury trip shouldn’t dominate).  

---

## 🔹 9. Key Takeaways

- **Assumptions** ensure regression is valid.  
- **Cost Function (MSE)** measures fit.  
- **Gradient Descent** finds the best coefficients.  
- **Learning Rate** controls convergence speed.  
- **MSE, RMSE, MAE** are core error metrics:  
  - MSE → optimization, punishes large errors.  
  - RMSE → interpretable, balances penalties.  
  - MAE → robust, simple, less sensitive to outliers.  

# 📘 Linear Regression & Regularization in Machine Learning

---

## ⚙️ Cost Function (Mean Squared Error - MSE)
The cost function measures how well the model’s predictions fit the actual data.  
In linear regression, the cost function is:

<img src="https://latex.codecogs.com/png.latex?J(\theta)%20=%20\frac{1}{2m}%20\sum_{i=1}^{m}%20\big(%20h_\theta(x^{(i)})%20-%20y^{(i)}%20\big)^2" />

- **m** → number of training examples  
- **hθ(x)** → predicted value (hypothesis)  
- **y** → actual value  
- **Goal** → minimize the cost function (reach the global minimum)

---

## 🔴 Underfitting
- **Definition**: Model is too simple and fails to capture the underlying trend.
- **Accuracy Pattern**:  
  - Training Accuracy: Low  
  - Test Accuracy: Low  
- **Example**: Fitting a straight line to quadratic data.

---

## 🔵 Overfitting
- **Definition**: Model memorizes noise along with the true pattern.
- **Accuracy Pattern**:  
  - Training Accuracy: Very High (close to 100%)  
  - Test Accuracy: Much Lower (large gap)  
- **Example**: High-degree polynomial perfectly fitting training points but failing on unseen data.

---

## 🟢 Well-Generalized Model
- **Definition**: Captures the main patterns and generalizes to unseen data.
- **Accuracy Pattern**:  
  - Training Accuracy: High (not perfect)  
  - Test Accuracy: Close to training (small gap)  
- **Example**: A suitable regression model that explains variance and predicts reliably.

---

## 📊 Ideal Accuracy Values (General Guidelines)

| Model Type       | Training Accuracy | Test Accuracy | Gap Between Train & Test |
|------------------|------------------|---------------|--------------------------|
| Underfitting     | < 70%            | < 70%         | Small gap (but both low) |
| Overfitting      | 95–100%          | 60–80%        | Large gap                |
| Generalized      | 80–95%           | Close (within 2–5%) | Small gap, both high |

---

## 📘 Ridge Regression (L2 Regularization)

### 🔹 Cost Function
<img src="https://latex.codecogs.com/png.latex?J(\theta)%20=%20\frac{1}{2m}%20\sum_{i=1}^{m}%20\big(h_\theta(x^{(i)})%20-%20y^{(i)}\big)^2%20+%20\lambda%20\sum_{j=1}^{n}%20\theta_j^2" />

- \( \lambda \) = regularization parameter (strength of penalty).  
- Shrinks coefficients closer to 0 but never eliminates features.

### 🔹 Effect
- Reduces variance.  
- Prevents overfitting.  
- Keeps all features but **shrinks their impact**.

---

## 📘 Lasso Regression (L1 Regularization)

### 🔹 Cost Function
<img src="https://latex.codecogs.com/png.latex?J(\theta)%20=%20\frac{1}{2m}%20\sum_{i=1}^{m}%20\big(h_\theta(x^{(i)})%20-%20y^{(i)}\big)^2%20+%20\lambda%20\sum_{j=1}^{n}%20|\theta_j|" />

- \( \lambda \) = regularization parameter.  
- Larger \( \lambda \) → stronger shrinkage, more features eliminated.

### 🔹 Effect
- Prevents overfitting.  
- Creates sparse models (many coefficients = 0).  
- Automatically selects the most important features.

---

## 📘 Bias and Variance

### 🔹 Bias
- **Definition**: Error from simplifying assumptions.  
- **High Bias → Underfitting**  
- Model cannot learn patterns → poor performance on both train & test.  

### 🔹 Variance
- **Definition**: Error from excessive sensitivity to training data.  
- **High Variance → Overfitting**  
- Model learns noise → high train accuracy, low test accuracy.  

### ⚖️ Bias–Variance Tradeoff
- Goal: balance bias and variance.  
- Low Bias + Low Variance = well-generalized model.  

---

## 🛠 Role of Regularization
- **Ridge (L2)**: Shrinks coefficients, reduces variance, keeps all features.  
- **Lasso (L1)**: Shrinks some coefficients to zero, reduces variance, performs feature selection.  
- **Elastic Net**: Combines Ridge + Lasso.  

---

## ✅ Final Summary
- **Underfitting** → Low train, low test (High Bias).  
- **Overfitting** → High train, low test (High Variance).  
- **Generalized** → High train, high test, small gap (Balanced).  
- **Ridge (L2)** → Controls variance by shrinking coefficients.  
- **Lasso (L1)** → Controls variance + selects features.  
- **Bias–Variance Tradeoff** → Central idea for building robust models.  
