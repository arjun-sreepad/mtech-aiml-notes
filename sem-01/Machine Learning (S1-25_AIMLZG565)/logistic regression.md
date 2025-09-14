# 📘 Regression & Classification in Machine Learning

This note covers:
1. Linear Regression & Cost Function  
2. Underfitting, Overfitting, Generalization  
3. Ridge (L2) and Lasso (L1) Regularization  
4. Bias–Variance Tradeoff  
5. Elastic Net (L1 + L2)  
6. Logistic Regression (Classification)  

---

## ⚙️ Linear Regression & Cost Function (MSE)

Linear Regression predicts a **continuous value**.  

**Cost Function (Mean Squared Error - MSE):**  
<img src="https://latex.codecogs.com/png.latex?J(\theta)%20=%20\frac{1}{2m}%20\sum_{i=1}^{m}%20\big(%20h_\theta(x^{(i)})%20-%20y^{(i)}%20\big)^2" />

- **m** → number of training examples  
- **hθ(x)** → predicted value  
- **y** → actual value  
- Goal → minimize cost to find best-fit line  

---

## 🔴 Underfitting
- **Concept:** Model too simple → fails to capture trend.  
- **Train Accuracy:** Low  
- **Test Accuracy:** Low  
- **Example:** Straight line for quadratic data.  

---

## 🔵 Overfitting
- **Concept:** Model too complex → memorizes noise.  
- **Train Accuracy:** Very High (~100%)  
- **Test Accuracy:** Much Lower  
- **Example:** Very high-degree polynomial passing exactly through all points.  

---

## 🟢 Generalized Model
- **Concept:** Balanced → captures real patterns, not noise.  
- **Train Accuracy:** High (80–95%)  
- **Test Accuracy:** Close to train (small gap).  
- **Example:** Reasonable linear/polynomial model explaining variance and predicting well.  

---

## 📊 Accuracy Expectations

| Model Type    | Training Accuracy | Test Accuracy | Gap |
|---------------|------------------|---------------|-----|
| Underfitting  | < 70%            | < 70%         | Small but both low |
| Overfitting   | 95–100%          | 60–80%        | Large |
| Generalized   | 80–95%           | ~Close        | Small |

---

## 📘 Ridge Regression (L2 Regularization)

Adds **penalty for large coefficients** → prevents overfitting.  

**Cost Function:**  
<img src="https://latex.codecogs.com/png.latex?J(\theta)%20=%20\frac{1}{2m}%20\sum_{i=1}^{m}%20\big(h_\theta(x^{(i)})-y^{(i)}\big)^2%20+%20\lambda%20\sum_{j=1}^{n}\theta_j^2" />

- Shrinks coefficients smoothly  
- Never makes them exactly zero  
- Keeps all features  

**Example:** House price prediction with correlated features (size & bedrooms) → both coefficients reduced but retained.  

---

## 📘 Lasso Regression (L1 Regularization)

Adds **absolute value penalty** → some coefficients shrink to zero.  

**Cost Function:**  
<img src="https://latex.codecogs.com/png.latex?J(\theta)%20=%20\frac{1}{2m}%20\sum_{i=1}^{m}%20\big(h_\theta(x^{(i)})-y^{(i)}\big)^2%20+%20\lambda%20\sum_{j=1}^{n}\lvert\theta_j\rvert" />

- Feature selection built-in  
- Sparse models (irrelevant features dropped)  

**Example:** Student performance with many features (attendance, study hours, diet, hobbies) → irrelevant ones (like “pets owned”) drop to 0.  

---

## 📘 Bias–Variance Tradeoff

- **Bias:** Error from being too simple → Underfitting  
- **Variance:** Error from being too complex → Overfitting  
- **Goal:** Balance both for best generalization  

**Regularization helps balance bias–variance**  
- Ridge → lowers variance (smooth shrinkage)  
- Lasso → lowers variance + does feature selection  

---

## 🧶 Elastic Net (L1 + L2)

**Idea:** Combine Ridge + Lasso.  

**Cost Function:**  
<img src="https://latex.codecogs.com/png.latex?J(\theta)=\frac{1}{2m}\sum_{i=1}^{m}(h_{\theta}(x^{(i)})-y^{(i)})^{2}+\lambda\!\left[\frac{1-\alpha}{2}\sum_{j=1}^{n}\theta_{j}^{2}+\alpha\sum_{j=1}^{n}\lvert\theta_{j}\rvert\right]" />

- **α = 0 → Ridge**  
- **α = 1 → Lasso**  
- **0 < α < 1 → Elastic Net**  

**When to use:**  
- Many correlated features  
- Need shrinkage + feature selection together  

**Example:** Predicting medical outcomes with many tests (blood sugar, cholesterol, blood pressure, etc.) → Elastic Net handles correlation while dropping useless tests.  

---

## 🧭 Logistic Regression (Binary Classification)

Predicts **probability of belonging to a class (0/1)**.  

### 1) Model  
Linear score:  
<img src="https://latex.codecogs.com/png.latex?z=\theta^{\top}x" />

Sigmoid:  
<img src="https://latex.codecogs.com/png.latex?\hat{p}=\sigma(z)=\frac{1}{1+e^{-z}}" />

- Predicts **probability** (0 ≤ p ≤ 1).  
- Classify using threshold (default 0.5).  

---

### 2) Example
- **Email Spam:**  
  - Email A → 0.9 → Spam  
  - Email B → 0.2 → Not spam  
- **Student Pass/Fail:**  
  - Hours studied = 10 → p=0.8 → Pass  
  - Hours studied = 2 → p=0.3 → Fail  

---

### 3) Loss Function (Log-Loss / Cross-Entropy)  
<img src="https://latex.codecogs.com/png.latex?J(\theta)=-\frac{1}{m}\sum_{i=1}^{m}\big[y^{(i)}\log\hat{p}^{(i)}+(1-y^{(i)})\log(1-\hat{p}^{(i)})\big]" />

- Punishes wrong confident predictions heavily  
- Convex → easier optimization  

---

### 4) Regularized Logistic Regression
- Add **L2** penalty → shrink all weights  
- Add **L1** penalty → drop irrelevant features  
- Use **Elastic Net** for mixed benefit  

---

### 5) Evaluation Metrics
- **Confusion Matrix:** TP, FP, TN, FN  
- **Accuracy:** (TP+TN)/(Total)  
- **Precision:** TP/(TP+FP)  
- **Recall:** TP/(TP+FN)  
- **F1:** harmonic mean of Precision & Recall  
- **ROC-AUC/PR-AUC:** quality independent of threshold  

---

## 🧰 Step-by-Step Workflow

1. **Collect Data** (e.g., Students → Pass/Fail)  
2. **Preprocess Features** (scale numbers, encode categories)  
3. **Split Data** (Train/Validation/Test)  
4. **Choose Model** (Logistic, add Ridge/Lasso/Elastic Net if needed)  
5. **Train** (minimize log-loss via gradient descent)  
6. **Tune Threshold** (default 0.5; adjust if recall/precision more important)  
7. **Evaluate** (metrics, confusion matrix)  
8. **Interpret** (coefficients → impact on odds)  
9. **Deploy & Monitor** (track drift, recalibrate thresholds)  

---

## ✅ Final Summary

- **Linear Regression** → continuous prediction  
- **Logistic Regression** → probability/class prediction  
- **Underfitting** → low train & test (high bias)  
- **Overfitting** → high train, low test (high variance)  
- **Ridge** → shrink all weights (L2)  
- **Lasso** → shrink some weights to zero (L1)  
- **Elastic Net** → combo (L1+L2)  
- **Bias–Variance Tradeoff** → main principle for generalization  
- **Logistic Regression Metrics** → accuracy, precision, recall, F1, AUC  

