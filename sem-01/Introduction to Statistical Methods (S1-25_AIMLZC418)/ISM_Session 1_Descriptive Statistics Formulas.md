# 🧾 Descriptive Statistics – Formulas & Symbols (Annotated & Complete)

Math is written for GitHub: block equations use `$$ ... $$`.

---

## A) Central Tendency

### Mean
- **Ungrouped**:  
$$ \bar{x} = \frac{\sum x_i}{n} $$
- **Grouped**:  
$$ \bar{x} = \frac{\sum f_i x_i}{\sum f_i} $$
**Symbols:** $\bar{x}$ = sample mean, $x_i$ = i‑th value (or class midpoint), $f_i$ = frequency, $n$ = sample size.

### Median
- **Grouped data**:  
$$ \text{Median} = L + \left(\frac{\frac{n}{2} - C_f}{f_m}\right)\,h $$
**Symbols:**  
$L$ = lower boundary of median class;  
$C_f$ = cumulative frequency before median class;  
$f_m$ = frequency of median class;  
$h$ = class width;  
$n$ = total frequency.

### Mode (grouped)
$$ \text{Mode} = L + \left(\frac{f_1 - f_0}{2f_1 - f_0 - f_2}\right)\,h $$
**Symbols:**  
$L$ = lower boundary of modal class;  
$f_1$ = frequency of modal class;  
$f_0$ = frequency of class before modal;  
$f_2$ = frequency of class after modal;  
$h$ = class width.

---

## B) Percentiles, Quartiles & IQR
- **Percentile position (ungrouped)**:  
$$ P_k = \frac{k}{100}(n+1) $$
- **Quartiles**: $Q_1$ (25%), $Q_2$ (50% = median), $Q_3$ (75%).  
- **Interquartile Range**:  
$$ IQR = Q_3 - Q_1 $$

**Whisker/Fence definitions (for boxplots):**
- **Lower fence (LF)**:  
$$ LF = Q_1 - 1.5\,IQR $$
- **Upper fence (UF)**:  
$$ UF = Q_3 + 1.5\,IQR $$
- **Major‑outlier fences (optional)**:  
$$ LF_{3} = Q_1 - 3\,IQR, \qquad UF_{3} = Q_3 + 3\,IQR $$

**Whisker endpoints:**
- **Lower whisker**: smallest observation $\ge LF$ → denote as $W_{\min}$.  
- **Upper whisker**: largest observation $\le UF$ → denote as $W_{\max}$.

**Symbols:** $Q_1,Q_2,Q_3$ = quartiles; $IQR$ = interquartile range; $LF,UF$ = fences; $W_{\min},W_{\max}$ = whisker tips.

---

## C) Variability (Range, Variance, SD)
- **Range** (simple):  
$$ R = X_{\max} - X_{\min} $$
- **Range with real limits (continuous classes)**:  
$$ R = URL(X_{\max}) - LRL(X_{\min}) $$

- **Sum of Squares (SS)**:  
$$ SS = \sum (x_i - \bar{x})^2 $$

- **Population**:  
$$ \sigma^2 = \frac{\sum (x_i - \mu)^2}{N}, \qquad \sigma = \sqrt{\sigma^2} $$

- **Sample**:  
$$ s^2 = \frac{\sum (x_i - \bar{x})^2}{n-1}, \qquad s = \sqrt{s^2} $$

**Symbols:**  
$X_{\max},X_{\min}$ = max/min observations;  
$URL, LRL$ = upper/lower real limits of classes;  
$SS$ = sum of squares;  
$\mu$ = population mean; $\bar{x}$ = sample mean;  
$\sigma^2,\sigma$ = population variance/SD; $s^2,s$ = sample variance/SD;  
$N$ = population size; $n$ = sample size;  
$n-1$ = degrees of freedom ($df$).

---

## D) Skewness (Empirical Relation)
_For moderately skewed data:_  
$$ 3\,\text{Median} = \text{Mode} + 2\,\text{Mean} $$
Used to check consistency of computed measures.

---

## E) Outlier Identification (Boxplot Rule)
- A point $x$ is a **potential (mild) outlier** if $x < LF$ or $x > UF$.  
- A point $x$ is a **major outlier** if $x < LF_3$ or $x > UF_3$.

---

## F) Symbols Master Table
| Symbol | Meaning |
|---|---|
| $x_i$ | i‑th observation |
| $f_i$ | frequency of i‑th class |
| $n, N$ | sample size, population size |
| $\bar{x}, \mu$ | sample mean, population mean |
| $s^2, \sigma^2$ | sample variance, population variance |
| $s, \sigma$ | sample SD, population SD |
| $SS$ | sum of squares $\sum (x_i-\bar{x})^2$ |
| $Q_1,Q_2,Q_3$ | quartiles (25%, 50%, 75%) |
| $IQR$ | interquartile range $Q_3-Q_1$ |
| $LF, UF$ | lower/upper fences $Q_1-1.5IQR$, $Q_3+1.5IQR$ |
| $LF_3, UF_3$ | major outlier fences $Q_1-3IQR$, $Q_3+3IQR$ |
| $W_{\min}, W_{\max}$ | whisker endpoints |
| $L, h$ | lower class boundary, class width |
| $C_f, f_m$ | cumulative freq before median class, freq of median class |
| $f_0, f_1, f_2$ | pre‑modal, modal, post‑modal class frequencies |
| $URL, LRL$ | upper/lower real limits (continuous classes) |

---