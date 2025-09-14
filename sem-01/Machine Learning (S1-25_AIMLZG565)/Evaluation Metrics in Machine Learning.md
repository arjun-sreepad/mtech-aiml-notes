# 📘 Evaluation Metrics in Machine Learning

Evaluating machine learning models is essential because training a model alone is not enough—we need to know how well it generalizes to unseen data. To achieve this, datasets are usually divided into **training**, **validation**, and **test** sets. The training set is used to fit the model, the validation set helps tune hyperparameters and reduce overfitting, and the test set is kept aside for the final unbiased evaluation. A typical split is 70% training, 15% validation, and 15% testing. For small datasets, **cross-validation** is often preferred.

Depending on whether the problem is **classification** or **regression**, the evaluation metrics differ. Classification problems predict discrete categories (spam or not spam, disease or healthy), while regression predicts continuous values (house prices, temperatures). Choosing the right metric is critical, because each one highlights different aspects of model performance.

---

## 🔹 Classification Metrics

The foundation of classification evaluation is the **confusion matrix**, which compares actual vs predicted labels.  

|               | Predicted Positive | Predicted Negative |
|---------------|-------------------|-------------------|
| **Actual Positive** | True Positive (TP) | False Negative (FN) |
| **Actual Negative** | False Positive (FP) | True Negative (TN) |

From this, several metrics are derived:

- **Accuracy** measures the proportion of correctly classified examples. It is intuitive and works well on balanced datasets, but becomes misleading on imbalanced ones. For example, predicting all negatives in a rare-disease dataset gives high accuracy but no real usefulness.  
- **Accuracy Error** or misclassification rate is simply 1 − Accuracy, showing the proportion of incorrect predictions.  
- **Precision** focuses on the correctness of positive predictions. It asks: “Of all the predicted positives, how many are truly positive?” This is crucial when false positives are costly, such as in spam detection.  
- **Recall** (or sensitivity, or True Positive Rate) asks: “Of all the actual positives, how many did we catch?” It is vital when false negatives are costly, such as in medical testing.  
- Since precision and recall often trade off, the **F1 score** combines them using their harmonic mean, offering balance in cases where both false positives and false negatives matter.  
- The **Fβ score** generalizes this idea: β>1 emphasizes recall, while β<1 emphasizes precision. For example, β=2 in medical testing favors catching more positives.  
- **Logarithmic Loss (LogLoss)** penalizes models for being confident but wrong, making it ideal for probabilistic classifiers where calibrated probability estimates matter (e.g., predicting loan defaults).  
- The **ROC curve** shows the trade-off between recall (TPR) and false positive rate (FPR). The **AUC (Area Under Curve)** provides a threshold-independent score of model discrimination ability, often used in medical diagnosis.  

> Quick formulas you may reference while reading (optional):  
> TPR/Recall = TP / (TP + FN), FPR = FP / (FP + TN).

---

## 🔹 Regression Metrics

Regression problems deal with continuous values. Errors are measured as differences between actual and predicted values.  

- **Mean Absolute Error (MAE)** is the average of absolute errors. It is easy to interpret and robust to outliers, but treats all errors equally. For instance, predicting daily temperature differences.  
- **Mean Squared Error (MSE)** squares errors before averaging. This punishes large errors heavily, making it useful in contexts like stock price prediction, but harder to interpret since it’s not in original units.  
- **Root Mean Squared Error (RMSE)** solves this by taking the square root, restoring the original unit. For example, predicting house prices where “off by $5000” is intuitive.  
- **Mean Absolute Percentage Error (MAPE)** expresses errors as percentages, useful in business forecasting, though it fails when actual values are zero.  
- **R² score** (coefficient of determination) measures how much variance in the target is explained by the model. An R² of 0.9 means the model explains 90% of variance. But R² can be misleading if many predictors are added.  
- **Adjusted R²** corrects this by penalizing excessive predictors, making it better for comparing models with different numbers of features.  
- **Huber Loss** combines MSE and MAE. Small errors are squared (like MSE), but large errors are treated linearly (like MAE), making it robust to outliers. A good example is delivery time prediction, where most times are consistent but occasional outliers exist.  

---

## 🔑 Closing Note

The choice of evaluation metric depends not only on the dataset but also on the **real-world context**. In classification, the key question is: *Are false positives or false negatives costlier?* In regression, it is: *Do we care more about average deviation, large errors, percentage-based accuracy, or variance explained?* The best practice is to monitor multiple metrics rather than relying on one.

---

# ⚡ Cheat Sheet — Metrics Summary

## Classification Metrics

| Metric | Formula | Pros | Cons | When to Use | Example |
|--------|---------|------|------|-------------|---------|
| Accuracy | <img src="https://latex.codecogs.com/svg.latex?%5CLarge%20Accuracy%3D%5Cfrac%7BTP%2BTN%7D%7BTP%2BTN%2BFP%2BFN%7D"> | Simple, intuitive | Misleading on imbalanced data | Balanced datasets | Digit recognition |
| Error Rate | <img src="https://latex.codecogs.com/svg.latex?%5CLarge%20Error%3D1-Accuracy%3D%5Cfrac%7BFP%2BFN%7D%7BTP%2BTN%2BFP%2BFN%7D"> | Shows misclassifications | Same limits as accuracy | General baseline | Any classification |
| Precision | <img src="https://latex.codecogs.com/svg.latex?%5CLarge%20Precision%3D%5Cfrac%7BTP%7D%7BTP%2BFP%7D"> | Focuses on positive prediction quality | Ignores false negatives | Cost of false positives is high | Spam filter |
| Recall (TPR) | <img src="https://latex.codecogs.com/svg.latex?%5CLarge%20Recall%3DTPR%3D%5Cfrac%7BTP%7D%7BTP%2BFN%7D"> | Captures positives | Ignores false positives | Cost of false negatives is high | Disease detection |
| F1 Score | <img src="https://latex.codecogs.com/svg.latex?%5CLarge%20F1%3D2%5Ctimes%5Cfrac%7BPrecision%5Ctimes%20Recall%7D%7BPrecision%2BRecall%7D"> | Balances precision & recall | Ignores TN | Imbalanced data | Fraud detection |
| Fβ Score | <img src="https://latex.codecogs.com/svg.latex?%5CLarge%20F_%5Cbeta%3D(1%2B%5Cbeta%5E2)%5Ccdot%5Cfrac%7BPrecision%5Ctimes%20Recall%7D%7B(%5Cbeta%5E2%5Ctimes%20Precision)%2BRecall%7D"> | Weighs recall vs precision | Need β choice | Prioritize one error type | Medical tests |
| Log Loss | <img src="https://latex.codecogs.com/svg.latex?%5CLarge%20LogLoss%3D-%5Cfrac%7B1%7D%7BN%7D%5Csum_%7Bi%3D1%7D%5EN%5B%20y_i%5Clog(p_i)%2B(1-y_i)%5Clog(1-p_i)%20%5D"> | Uses probabilities, punishes overconfidence | Less interpretable | Probabilistic models | Loan default |
| ROC–AUC | Curve of TPR vs FPR | Threshold independent | Can mislead with heavy class imbalance | Comparing models | Medical diagnosis |

---

## Regression Metrics

| Metric | Formula | Pros | Cons | When to Use | Example |
|--------|---------|------|------|-------------|---------|
| MAE | <img src="https://latex.codecogs.com/svg.latex?%5CLarge%20MAE%3D%5Cfrac%7B1%7D%7Bn%7D%5Csum_%7Bi%3D1%7D%5En%7C%20y_i-%5Chat%7By%7D_i%20%7C"> | Easy to interpret, robust | Treats all errors equally | Interpretability needed | Temperature prediction |
| MSE | <img src="https://latex.codecogs.com/svg.latex?%5CLarge%20MSE%3D%5Cfrac%7B1%7D%7Bn%7D%5Csum_%7Bi%3D1%7D%5En%20(y_i-%5Chat%7By%7D_i)%5E2"> | Punishes large errors, smooth for optimization | Units squared, less intuitive | Penalize large errors | Stock prediction |
| RMSE | <img src="https://latex.codecogs.com/svg.latex?%5CLarge%20RMSE%3D%5Csqrt%7B%5Cfrac%7B1%7D%7Bn%7D%5Csum_%7Bi%3D1%7D%5En%20(y_i-%5Chat%7By%7D_i)%5E2%7D"> | Same unit as target, interpretable | Sensitive to outliers | Interpretability + penalty | House price |
| MAPE | <img src="https://latex.codecogs.com/svg.latex?%5CLarge%20MAPE%3D%5Cfrac%7B100%5C%25%7D%7Bn%7D%5Csum_%7Bi%3D1%7D%5En%20%5Cleft%7C%5Cfrac%7By_i-%5Chat%7By%7D_i%7D%7By_i%7D%5Cright%7C"> | Percentage, business-friendly | Undefined at zero | Forecasting | Sales prediction |
| R² | <img src="https://latex.codecogs.com/svg.latex?%5CLarge%20R%5E2%3D1-%5Cfrac%7B%5Csum%20(y_i-%5Chat%7By%7D_i)%5E2%7D%7B%5Csum%20(y_i-%5Cbar%7By%7D)%5E2%7D"> | Explains variance | Can mislead with many predictors | Variance explained | GDP models |
| Adjusted R² | <img src="https://latex.codecogs.com/svg.latex?\Large%20Adjusted%20R%5E2%3D1-(1-R%5E2)\cdot\frac{n-1}{n-p-1}"> | Corrects for predictors | Less intuitive | Comparing models | Economics |
| Huber Loss | <img src="https://latex.codecogs.com/svg.latex?%5CLarge%20L_%5Cdelta(y%2C%5Chat%7By%7D)%3D%5Cbegin%7Bcases%7D%20%5Cfrac%7B1%7D%7B2%7D(y-%5Chat%7By%7D)%5E2%2C%20%5C%20%5Ctext%7Bif%7D%20%7C%20y-%5Chat%7By%7D%20%7C%20%5Cleq%20%5Cdelta%20%5C%5C%20%5Cdelta%5Ccdot(%7C%20y-%5Chat%7By%7D%20%7C-%5Cfrac%7B1%7D%7B2%7D%5Cdelta)%2C%20%5C%20%5Ctext%7Botherwise%7D%20%5Cend%7Bcases%7D"> | Robust to outliers | Requires δ tuning | Outlier-prone data | Delivery times |

---

> **Tip:** If you ever see formulas not rendering on GitHub, ensure you’re using an `<img src="https://latex.codecogs.com/svg.latex?...">` link and that special characters (spaces, `+`, `%`, etc.) are URL-encoded.
