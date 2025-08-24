# 🧾 Probability — Formulas & Symbols (Annotated)

## Axioms & Basic Rules
- $0\le P(A)\le 1$, $\;P(S)=1$
- If $A\cap B=\varnothing$: $\;P(A\cup B)=P(A)+P(B)$
- General addition rule: $\;P(A\cup B)=P(A)+P(B)-P(A\cap B)$
- Complement: $\;P(A^c)=1-P(A)$
- Independence: $\;P(A\cap B)=P(A)P(B)$
- Conditional probability: $\;P(A\mid B)=\dfrac{P(A\cap B)}{P(B)}$

## Counting (Permutations & Combinations)
- Factorial: $n!=n(n-1)\cdots 2\cdot 1$
- Permutation (ordered): $\;{}^nP_r=\dfrac{n!}{(n-r)!}$
- Combination (unordered): $\;{n\choose r}=\dfrac{n!}{r!(n-r)!}$
- With repetition (common cases):
  - Combinations with repetition: ${n+r-1\choose r}$
  - Arrangements of multiset: $\dfrac{n!}{n_1!\,n_2!\cdots}$

## Symbols
- $S$: sample space; $\omega$: outcome; $A,B$: events
- $A^c$: complement; $A\cup B$: union; $A\cap B$: intersection
- $n!$: factorial; ${n\choose r}$: binomial coefficient
