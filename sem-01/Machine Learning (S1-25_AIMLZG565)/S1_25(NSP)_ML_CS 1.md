
# 📘 Machine Learning Types – Notes

Machine Learning (ML) can be classified into different types based on supervision, availability of labels, and learning approach.

---

## 🔹 1. Supervised Learning
- **Definition**: The machine learns using **labeled data** (input-output pairs).  
- **Type of Problems**: Regression & Classification.  
- **Type of Data**: Labeled data.  
- **Training**: Requires **external supervision**.  
- **Approach**: Maps inputs → known outputs.  

### Subtypes & Examples:
- **Regression** (continuous target variable)  
  - Predicts numerical values.  
  - Example: *Housing Price Prediction*.  
- **Classification** (categorical target variable)  
  - Predicts discrete categories.  
  - Example: *Medical Imaging (disease detection)*.  

**When to Use**: When you have labeled historical data and want to predict outcomes for new data.

---

## 🔹 2. Unsupervised Learning
- **Definition**: The machine is trained on **unlabeled data** without guidance.  
- **Type of Problems**: Association & Clustering.  
- **Type of Data**: Unlabeled data.  
- **Training**: No supervision.  
- **Approach**: Discovers hidden patterns & structures.  

### Subtypes & Examples:
- **Clustering**  
  - Groups similar data points.  
  - Example: *Customer Segmentation*.  
- **Association**  
  - Finds relationships in data.  
  - Example: *Market Basket Analysis*.  

**When to Use**: When you don’t have labeled data but want to discover hidden structures or relationships.

---

## 🔹 3. Semi-Supervised Learning
- **Definition**: Uses **small labeled data + large unlabeled data**.  
- **Type of Problems**: Classification & Clustering.  
- **Type of Data**: Partially labeled.  
- **Approach**: Learns from both supervised & unsupervised methods.  

### Subtypes & Examples:
- **Classification** – Example: *Text Classification*.  
- **Clustering** – Example: *Lane-finding on GPS Data*.  

**When to Use**: When labeling data is expensive/time-consuming, but you have plenty of unlabeled data.

---

## 🔹 4. Reinforcement Learning
- **Definition**: An agent interacts with the environment, learns via **rewards & penalties**.  
- **Type of Problems**: Reward-based (control/decision making).  
- **Type of Data**: No predefined dataset, learns from experience.  
- **Training**: No supervision, uses **trial-and-error**.  
- **Approach**: Learns optimal actions to maximize rewards.  

### Subtypes & Examples:
- **Classification** – Example: *Optimized Marketing*.  
- **Control** – Example: *Driverless Cars*.  

**When to Use**: When decisions need to be made sequentially with feedback from the environment.

---

## ✅ Comparison Table – Types of Machine Learning

| **Criteria**      | **Supervised Learning**                | **Unsupervised Learning**                  | **Semi-Supervised Learning**           | **Reinforcement Learning**                              |
|-------------------|----------------------------------------|--------------------------------------------|-----------------------------------------|--------------------------------------------------------|
| **Definition**    | Learns using labeled data              | Learns from unlabeled data                  | Learns from small labeled + large unlabeled data | Learns by interacting with environment (rewards/penalty) |
| **Type of Problems** | Regression & Classification            | Association & Clustering                    | Classification & Clustering             | Reward-based (decision/control)                        |
| **Type of Data**  | Labeled Data                           | Unlabeled Data                              | Partially labeled Data                  | No predefined data                                     |
| **Training**      | External supervision                   | No supervision                              | Partial supervision                     | No supervision (trial-and-error)                       |
| **Approach**      | Maps input → output                    | Finds patterns & hidden structure           | Combines supervised + unsupervised      | Optimizes behavior via feedback                        |
| **Examples**      | Housing Prices, Medical Imaging        | Customer Segmentation, Market Basket        | Text Classification, Lane Finding       | Marketing Optimization, Driverless Cars                |
| **When to Use**   | When you have labeled data & want predictions | When you want hidden patterns without labels | When labels are limited but unlabeled data is plenty | When actions need optimization via environment feedback |

---
