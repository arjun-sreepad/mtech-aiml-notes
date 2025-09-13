# Mathematical Foundations – Formula Sheet

## Matrix Basics
- Addition: \((A+B)_{ij} = a_{ij} + b_{ij}\)
- Scalar multiplication: \((\lambda A)_{ij} = \lambda a_{ij}\)
- Matrix product: \((AB)_{ij} = \sum_{k=1}^n a_{ik} b_{kj}\)

---

## Transpose Properties
- \((A^T)^T = A\)
- \((A+B)^T = A^T + B^T\)
- \((AB)^T = B^T A^T\)

---

## Inverse Properties
- \(AA^{-1} = A^{-1}A = I\)
- \((AB)^{-1} = B^{-1}A^{-1}\)
- \((A+B)^{-1} \neq A^{-1}+B^{-1}\)

---

## Determinant & Inverse (2×2)
For \(A = \begin{bmatrix} a & b \\ c & d \end{bmatrix}\):

$$
\det(A) = ad - bc
$$

If \(\det(A) \ne 0\):

$$
A^{-1} = \frac{1}{ad - bc} \begin{bmatrix} d & -b \\ -c & a \end{bmatrix}
$$

---

## Gaussian Elimination – Steps
1. Use pivot to eliminate entries below in each column.  
2. Obtain row echelon form (upper triangular).  
3. Back-substitute to solve.  
4. (Optional) Reduce to RREF (pivots = 1, pivot is the only non-zero in its column).

---

## Elementary Row Operations
- Swap rows: \(R_i \leftrightarrow R_j\)  
- Scale a row: \(\lambda R_i\) with \(\lambda \ne 0\)  
- Row replacement: \(R_i \to R_i + \lambda R_j\)  
