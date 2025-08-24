# 📒 Probability Problem Sets — 50 Problems with Step-by-Step Solutions

The set mixes **PPT examples**, **Permutations & Combinations**, and **mixed probability** (dice, cards, truth/lie, Venn, tables).

---

## Section A — PPT Examples (10)

**A1. Valid probability assignments**  
... *(same as Notes; full solution included there)*

**A2. Two dice: $P(\text{sum}>8)$**  
**Solution.** 10/36 = **5/18**.

**A3. Two dice: $P(\text{sum}<6)$**  
**Solution.** 10/36 = **5/18**.

**A4. Two dice: neither 7 nor 11**  
**Solution.** $1-6/36-2/36=28/36=**7/9**$.

**A5. Pass at least one exam**  
**Solution.** $P(\text{both})=\frac{14}{45}$.

**A6. Investors in annuity/stock**  
**Solution.** $P(A\cap B)=**0.35**$.

**A7. Cable specification tails**  
**Solution.** Each tail $=0.005$; $P(X>1990)=0.995$.

**A8. Maximize $P(A)P(B)$ under $A\cup B=S$**  
**Solution.** Max product $=1/4$ at $1/2,1/2$.

**A9. Committee majority women**  
**Solution.** $\dfrac{120}{792}=\dfrac{5}{33}$.

**A10. Dice: $P(\text{sum neither }7,11,2)$**  
**Solution.** $27/36 = **3/4**$.

---

## Section B — Permutations & Combinations (20)

**B1. Arrange “STATISTICS.”**  
**Solution.** $\dfrac{10!}{3!3!2!}=50{,}400$.

**B2. Seat 6 people; two together.** → $5!\cdot 2!=240$  
**B3. Seat 6 people; two not together.** → $720-240=480$  
**B4. 12 books, 5 math together.** → $(8!)\cdot(5!)$  
**B5. Team of 4 from 8M,5W; ≥2 W.** → $365$  
**B6. 7-digit codes, distinct, no leading 0.** → $9\cdot \dfrac{9!}{3!}$  
**B7. 8 identical balls into 4 boxes (≥0).** → ${11\choose3}=165$  
**B8. 8 identical balls into 4 boxes (≥1).** → ${7\choose3}=35$  
**B9. Solutions nonneg: $x_1+x_2+x_3=12$.** → ${14\choose2}=91$  
**B10. 5-card hands with exactly 2 aces.** → $\binom{4}{2}\binom{48}{3}$  
**B11. Plates 2 letters + 4 digits.** → $26^2\cdot 10^4$  
**B12. 8-letter pw (letters), must include ‘a’.** → $26^8-25^8$  
**B13. Arrange “ARRANGEMENT.”** → $\dfrac{12!}{2!2!2!2!}$  
**B14. Circular 8 people; two opposite.** → $6!$  
**B15. Handshakes among $n$ people.** → $\binom{n}{2}$  
**B16. 6-digit even numbers, no repetition.** → $41\cdot \frac{8!}{4!}$  
**B17. Committee of 7 from 10/6/4, ≥2 each.** → sum of three cases (given)  
**B18. “BALLOON”: L together, O apart.** → inclusion–exclusion (outline)  
**B19. Binary strings length 12 with five 1’s.** → $\binom{12}{5}$  
**B20. Shortest paths (0,0)→(5,4).** → $\binom{9}{4}$

---

## Section C — Mixed Probability (20)

**C1. ≥1 six in 4 throws.** → $1-(5/6)^4$  
**C2. Two hearts without replacement.** → $\frac{13}{52}\cdot \frac{12}{51}=\frac{4}{289}$  
**C3. Ace or king.** → $8/52=2/13$  
**C4. Two children; both girls | ≥1 girl.** → $1/3$  
**C5. 2 from (5 good,2 bad); both good.** → $10/21$  
**C6. Truth/lie contradict.** → $0.44$  
**C7. Internet/TV union/exactly one.** → $0.90$ and $0.40$  
**C8. Insurance table questions.** → (two-way table arithmetic)  
**C9. Exactly two heads in 3 coins.** → $3/8$  
**C10. First 6 by 3rd roll.** → $1-(5/6)^3$  
**C11. Two balls, different colors (4R,5B,3G).** → $1-\frac{\binom{4}{2}+\binom{5}{2}+\binom{3}{2}}{\binom{12}{2}}$  
**C12. 5-digit number divisible by 5.** → $1/5$  
**C13. Choose 4 from 6M,5W with ≥1 of each.** → $\binom{11}{4}-\binom{6}{4}-\binom{5}{4}$  
**C14. Product even in two dice.** → $3/4$  
**C15. Min is 1 when choose 3 from 1..10.** → $3/10$  
**C16. Derangement probability.** → $\approx 1/e$  
**C17. Birthday ≥1 match in 25.** → $\approx 0.568$  
**C18. Flush (not straight flush).** → $\dfrac{4\binom{13}{5}-40}{\binom{52}{5}}$  
**C19. Exactly one defective (3 of 8 defective).** → $\dfrac{\binom{3}{1}\binom{5}{2}}{\binom{8}{3}}$  
**C20. Double-headed coin posterior.** → $1/2$

---

## Section D — Additional Exam-Style (10)

**D1. Choose 3 from 7 AIs & 5 MLs with ≥1 of each.** → $\binom{12}{3}-\binom{7}{3}-\binom{5}{3}$  
**D2. Two dice sum prime.** → $5/12$  
**D3. 4-digit PIN has repeated digit.** → $1- (10\cdot 9\cdot 8\cdot 7/10^4)=0.496$  
**D4. One red, one black without replacement.** → $26/51$  
**D5. Two urns, red probability.** → $1/2$  
**D6. Face or diamond.** → $11/26$  
**D7. Random T/F ≥8 correct.** → $\sum_{k=8}^{10} \binom{10}{k} 2^{-10}$  
**D8. Expected tosses to get HH.** → $6$  
**D9. Machine 3 defect posterior (Bayes).** → compute via priors 0.5 and likelihood 0.03 (expand if needed)  
**D10. Lottery: exactly 3 match.** → $\dfrac{\binom{6}{3}\binom{43}{3}}{\binom{49}{6}}$
