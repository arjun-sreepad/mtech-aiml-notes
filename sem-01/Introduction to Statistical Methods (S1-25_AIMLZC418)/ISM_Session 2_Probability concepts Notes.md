# 📘 Session 2: Probability Concepts — Detailed Notes (GitHub + LaTeX)

This document expands every concept from the PPT with clear explanations and examples.

---

## 1. Random Experiments, Sample Space, Events

### 1.1 Random Experiment
An **action with uncertain outcome** even under identical conditions.
- Examples: flip a coin; toss a die; pull a card; wait-time for a bus; classify phone calls (voice/data).

### 1.2 Sample Space (S)
Set of **all possible outcomes** of an experiment.
- Toss one die: $S=\{1,2,3,4,5,6\}$
- Test a chip: $S=\{\text{accept}, \text{reject}\}$
- Two coins: $S=\{\text{HH},\text{HT},\text{TH},\text{TT}\}$

### 1.3 Event
An **event** is a **subset** of $S$.
- **Simple** event: contains one outcome (e.g., $A=\{6\}$).
- **Compound** event: multiple outcomes (e.g., $B=\{4,5,6\}$).
- **Null event** $\varnothing$: impossible event.
- **Sure event** $S$: always occurs.

---

## 2. Set Operations on Events

### 2.1 Complement
$A^c=\{ \omega\in S:\omega\notin A \}$ — outcomes **not** in $A$.
- Probability rule: $P(A^c)=1-P(A)$.

### 2.2 Union and Intersection
- **Union**: $A\cup B=\{\omega:\omega\in A\ \text{or}\ \omega\in B\}$
- **Intersection**: $A\cap B=\{\omega:\omega\in A\ \text{and}\ \omega\in B\}$
- **Addition rule**: $P(A\cup B)=P(A)+P(B)-P(A\cap B)$

### 2.3 Mutually Exclusive vs Independent
- **Mutually Exclusive (Disjoint)**: $A\cap B=\varnothing$. If $A$ occurs, $B$ cannot.
  - For disjoint events: $P(A\cup B)=P(A)+P(B)$.
- **Independent**: $P(A\cap B)=P(A)P(B)$. The occurrence of one **does not change** the probability of the other.
  - Note: Independent events **need not** be disjoint (and disjoint non-trivial events cannot be independent).

---

## 3. Definitions of Probability

### 3.1 Classical (Equally Likely Outcomes)
$P(A)=\dfrac{\text{# favorable outcomes}}{\text{# total outcomes}}$

### 3.2 Empirical (Frequentist)
$P(A)\approx \dfrac{\text{# times A occurs}}{\text{# trials}}$ as trials $\to\infty$.

### 3.3 Axiomatic (Kolmogorov)
For a sample space $S$ and event $A\subseteq S$:
1) $0\le P(A)\le 1$  
2) $P(S)=1$  
3) If $A$ and $B$ are disjoint: $P(A\cup B)=P(A)+P(B)$
- Monotonicity: If $A\subseteq B$ then $P(A)\le P(B)$.
- Complement: $P(A^c)=1-P(A)$.

---

## 4. Key Rules You Will Use Constantly
- **Addition rule**: $P(A\cup B)=P(A)+P(B)-P(A\cap B)$
- **Disjoint simplification**: if $A\cap B=\varnothing$, $P(A\cup B)=P(A)+P(B)$
- **Complement rule**: $P(A^c)=1-P(A)$
- **Multiplication (independence)**: if independent, $P(A\cap B)=P(A)P(B)$
- **Conditional probability** (preview of Session 3):
  $$ P(A\mid B)=\frac{P(A\cap B)}{P(B)},\quad P(B)>0 $$

---

## 5. Worked Examples from PPT (Step-by-step)

### Example 1 — Valid probability assignments
Four mutually exclusive outcomes $A,B,C,D$. Which are permissible?
- Rule: $P(\cdot)\in[0,1]$ and total $=1$.  
- (a) $0.38+0.16+0.11+0.35=1.00$ → **Valid**  
- (b) $0.31+0.27+0.28+0.16=1.02>1$ → **Invalid**  
- (c) $P(C)=-0.06<0$ → **Invalid**  
- (d) $\tfrac12+\tfrac14+\tfrac18+\tfrac1{16}=0.5+0.25+0.125+0.0625=0.9375\neq1$ → **Invalid**  
- (e) $\tfrac58+\tfrac16+\tfrac13+\tfrac29= \frac{45+9+16+8}{72}= \frac{78}{72}>1$ → **Invalid**

### Example 2 — Two dice
Total outcomes = 36.
1) $P(\text{sum}>8)=\frac{\#\{9,10,11,12\}}{36}=\frac{10}{36}=\frac{5}{18}$  
   (9:4, 10:3, 11:2, 12:1 ways → $4+3+2+1=10$).  
2) $P(\text{sum}<6)=\frac{\#\{2,3,4,5\}}{36}=\frac{10}{36}=\frac{5}{18}$  
   (2:1, 3:2, 4:3, 5:4 → $1+2+3+4=10$).  
3) $P(\text{neither 7 nor 11})=1-P(7)-P(11)=1-\frac{6}{36}-\frac{2}{36}= \frac{28}{36}=\frac{7}{9}$.

### Example 3 — Passing statistics and mathematics
Given $P(\text{pass stat})=\tfrac23$, $P(\text{not pass math})=\tfrac59 \Rightarrow P(\text{pass math})=\tfrac49$, and
$P(\text{pass at least one})=\tfrac45$. Find $P(\text{pass both})$.
\begin{align*}
P(\text{S}\cup\text{M})&=P(\text{S})+P(\text{M})-P(\text{S}\cap\text{M})\\
\tfrac45&=\tfrac23+\tfrac49-P(\text{both})=\tfrac{6+4}{9}-P(\text{both})=\tfrac{10}{9}-P(\text{both})\\
P(\text{both})&=\tfrac{10}{9}-\tfrac{4}{5}=\tfrac{50-36}{45}=\tfrac{14}{45}.
\end{align*}

### Example 4 — Investors: annuities and stock
$P(A)=0.75$, $P(B)=0.45$, $P(A\cup B)=0.85$.
\begin{align*}
P(A\cap B)&=P(A)+P(B)-P(A\cup B)=0.75+0.45-0.85=0.35.
\end{align*}

### Example 5 — Cable specs
Given spec is $2000\pm 10$, and symmetry: $P(X>2010)=P(X<1990)$. Also $P(\text{meets spec})=0.99$.
Then $P(1990\le X\le 2010)=0.99 \Rightarrow P(X<1990)+P(X>2010)=0.01$.
By symmetry, each tail is $0.005$.
- (a) $P(\text{too large})=P(X>2010)=0.005$  
- (b) $P(X>1990)=1-P(X\le 1990)=1-0.005=0.995$

### Example 6 — Maximize $P(A)\cdot P(B)$
$A,B$ are **mutually exclusive** and $A\cup B=S$. Then $P(A)+P(B)=1$. For fixed sum, product is maximal when equal: $P(A)=P(B)=1/2$ → max product $=1/4$.

### Example 7 — Committee with majority women
Choose 5 from 8 men + 4 women. Probability of **majority women** (≥3 women).
Total ways: $\binom{12}{5}$. Favorable: $W=3,4,5$:
\begin{align*}
\binom{4}{3}\binom{8}{2}+\binom{4}{4}\binom{8}{1}+\binom{4}{5}\binom{8}{0}
= \binom{4}{3}\binom{8}{2}+\binom{4}{4}\binom{8}{1}+0
= 4\cdot 28 + 1\cdot 8 = 120.
\end{align*}
Thus $P=\dfrac{120}{\binom{12}{5}}=\dfrac{120}{792}=\dfrac{10}{66}=\dfrac{5}{33}\approx 0.1515$.

---

## 6. Common Misconceptions & Exam Tips
- **Disjoint ≠ Independent** (except for trivial cases).  
- Always check axiom constraints: **non‑negativity** and **sum to 1**.  
- For “at least one” use complement: $P(\ge 1) = 1 - P(0)$.  
- Draw a **Venn diagram** or list outcomes for dice/card problems.  
- For committees/seating, decide **order matters?** If no → combinations; if yes → permutations.
