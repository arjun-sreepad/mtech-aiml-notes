# 📘 Descriptive Statistics – PPT Revision Notes (Annotated & Complete)

This file expands **every point** in the PPT with clear explanations and a full section on **Box and Whisker plots**.

---

## 1) Statistics & Data
**Statistics** is the science of collecting, organizing, analyzing, and interpreting data to support decisions.

### 1.1 Types of Data
- **Qualitative (Categorical)**: describe qualities or labels; cannot be meaningfully averaged.  
  - **Nominal**: categories with **no order** (e.g., Gender, Eye color, Political party).  
  - **Ordinal**: categories with an **order/rank** but **unknown interval** between ranks (e.g., Poor < Good < Excellent, Gold–Silver–Bronze).
- **Quantitative (Numerical)**: measurable quantities; arithmetic makes sense.  
  - **Discrete**: **countable** values (e.g., # of children, defects per hour).  
  - **Continuous**: measured on a continuum; **infinitely many** possible values in an interval (e.g., weight, voltage, time).

### 1.2 Levels of Measurement
- **Nominal** → labels only.  
- **Ordinal** → order only; differences not meaningful.  
- **Interval** → order + **meaningful differences**; **no true zero** (e.g., °C/°F).  
- **Ratio** → order + meaningful differences + **true zero**; ratios are meaningful (e.g., weight, age, salary).

---

## 2) Measures of Central Tendency
These summarize the **center** of a distribution.

### 2.1 Mean (arithmetic average)
- Uses **all values** → most stable but **sensitive to outliers**.  
- Good for **symmetric** data and when you’ll compute SD/variance.

### 2.2 Median (50th percentile)
- **Middle value** when data are ordered.  
- Robust to outliers → preferred for **skewed** distributions (income, housing prices).

### 2.3 Mode
- **Most frequent** value/category.  
- Works for **nominal** data; may be **non-unique** (bi/multimodal).

> **Empirical relation (moderate skew)**:  
> $$ 3 \times \text{Median} = \text{Mode} + 2 \times \text{Mean} $$

---

## 3) Distribution Shapes
- **Symmetric**: Mean ≈ Median ≈ Mode.  
- **Right (positive) skew**: tail to the right; Mean > Median > Mode.  
- **Left (negative) skew**: tail to the left; Mean < Median < Mode.  
- **Bimodal / multimodal**: two or more peaks → often mixtures of groups.

---

## 4) Measures of Variability (Spread)
Explain how **dispersed** the data are.

### 4.1 Range
- Simplest spread: **Max – Min**.  
- For **continuous** measurements, some books use **real limits**:  
  - Range = **URL(X_max) – LRL(X_min)**, where URL = upper real limit, LRL = lower real limit of the class of the extreme observations.

### 4.2 Variance & Standard Deviation (SD)
- **Deviation** from mean: \(x_i - \bar{x}\).  
- Deviations sum to zero → **square** them and add: **Sum of Squares (SS)**.  
- **Variance** = average of squared deviations; **SD** = square root of variance.  
- **Population** uses \(N\); **sample** uses \(n-1\) (degrees of freedom) to remove bias.

### 4.3 Interquartile Range (IQR)
- **Middle 50% spread**: \(IQR = Q_3 - Q_1\).  
- **Resistant** to outliers. Crucial for **boxplots** and **outlier detection**.

---

## 5) Five‑Number Summary
- **Minimum, Q1, Median (Q2), Q3, Maximum**.  
- Summarizes location & spread with just five numbers; basis for **boxplots**.

---

## 6) Box and Whisker Plot (FULL)
A **boxplot** is a compact visualization of the five‑number summary and outliers.

### 6.1 Components
- **Box** spans from **Q1** (25th percentile) to **Q3** (75th percentile).  
- **Median line** inside the box at **Q2**.  
- **Whiskers** extend **from the box** to the **most extreme data points that are not outliers**.  
- **Outliers** are plotted individually beyond “fences”.

### 6.2 Fences & Outlier Rules
- **IQR** = \(Q_3 - Q_1\).  
- **Lower fence (LF)** = \(Q_1 - 1.5 \times IQR\).  
- **Upper fence (UF)** = \(Q_3 + 1.5 \times IQR\).  
  - Points **outside LF/UF** are **potential (mild) outliers**.  
- Many texts (and your PPT) also mention **major outliers** using **3 × IQR**:  
  - **Major lower fence** = \(Q_1 - 3 \times IQR\).  
  - **Major upper fence** = \(Q_3 + 3 \times IQR\).

### 6.3 Whisker Endpoints
- **Lower whisker** ends at the **smallest** observation **≥ LF**.  
- **Upper whisker** ends at the **largest** observation **≤ UF**.  
- Any points beyond are plotted as **separate dots** (mild/major).

### 6.4 What a Boxplot Tells You
- **Center** (median), **spread** (IQR & whisker length), **skewness** (longer whisker or median off‑center), and **outliers**.  
- **Comparative boxplots** (side‑by‑side) are great for comparing groups (median shift, spread, skew differences).

### 6.5 Quick ASCII Guide
```
min ──●───────┌───────────────box (Q1 to Q3)───────────────┐───────●── max
              │                | Median |                  │
      <─whisker─>                                         <─whisker─>
Fences: LF = Q1 - 1.5*IQR, UF = Q3 + 1.5*IQR
Outliers: plotted beyond fences (•)
```

### 6.6 Worked Mini‑Example
Data (sorted): 11, 12, 13, 16, 16, 17, 17, 18, 21 (n = 9)  
- **Median (Q2)** at position \( (n+1)/2 = 5 \Rightarrow 16 \).  
- Lower half: 11, 12, 13, 16 → **Q1** = average of 12 & 13 = **12.5**.  
- Upper half: 17, 17, 18, 21 → **Q3** = average of 17 & 18 = **17.5**.  
- **IQR** = 17.5 − 12.5 = **5**.  
- **Fences**:  
  - LF = 12.5 − 1.5×5 = **5.0**; UF = 17.5 + 1.5×5 = **25.0**.  
  - No data < 5 or > 25 → **no outliers**.  
- **Whiskers**: lower = 11 (≥ 5), upper = 21 (≤ 25).  
- Interpretation: median near center of box → **rough symmetry**.

> ⚠️ **Note on quartile conventions:** Different software/books use slightly different rules for computing Q1/Q3 when \(n\) is even/odd. State your method if answers must match exactly.

---

## 7) Practice Patterns (from PPT)
- Compute **Mean, Median, SD, Variance, IQR** for a dataset; then **draw a boxplot** and **comment on outliers**.  
- Compare **two branches** via **two boxplots** to discuss center, spread, and skew.

---

## 8) Takeaways
- Choose **median & IQR** for skewed data/outliers; **mean & SD** for symmetric data.  
- **Boxplots** quickly show center, spread, skew, and outliers; great for comparisons.  
- **Sum of Squares** justifies variance/SD and links to ANOVA/regression.