# Mathematical Foundations for ML – Lecture 1 Notes

## 1. Linear Algebra Basics
- **Linear Algebra**: Study of vectors and rules to manipulate them.  
- Vectors can be numbers, polynomials, functions → any objects closed under addition & scalar multiplication.  
- We usually work in \(\mathbb{R}^n\) (n-dimensional real space).

---

## 2. Systems of Linear Equations
- General form:

$$
a_{11}x_1 + a_{12}x_2 + \dots + a_{1n}x_n = b_1
$$

$$
a_{21}x_1 + a_{22}x_2 + \dots + a_{2n}x_n = b_2
$$

- Compact form:

$$
Ax = b
$$

- Solutions can be:
  - **Unique** (one solution).  
  - **No solution** (inconsistent system).  
  - **Infinite solutions** (underdetermined system).  

---

## 3. Matrices

### Definition
A matrix \(A \in \mathbb{R}^{m \times n}\):

$$
A =
\begin{bmatrix}
a_{11} & a_{12} & \dots & a_{1n} \\
a_{21} & a_{22} & \dots & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{m1} & a_{m2} & \dots & a_{mn}
\end{bmatrix}
$$

- **Row vector**: \(1 \times n\) matrix.  
- **Column vector**: \(m \times 1\) matrix.

---

### Matrix Operations
1. **Addition** (element-wise):  \((A+B)_{ij} = a_{ij} + b_{ij}\)  
2. **Scalar Multiplication**:  \((\lambda A)_{ij} = \lambda a_{ij}\)  
3. **Matrix Multiplication** (\(A \in \mathbb{R}^{m\times k}, B \in \mathbb{R}^{k\times n}\)):  
   \(C = AB,\; c_{ij} = \sum_{l=1}^{k} a_{il} b_{lj}\)

---

### Properties of Matrices
- **Associativity**: \((AB)C = A(BC)\)  
- **Distributivity**: \((A+B)C = AC + BC\), \(A(C+D) = AC + AD\)  
- **Identity**: \(I_m A = A I_n = A\)  

- **Transpose Properties**:  
  - \((A^T)^T = A\)  
  - \((A+B)^T = A^T + B^T\)  
  - \((AB)^T = B^T A^T\)

- **Inverse Properties** (if \(A^{-1}\) exists):  
  - \(AA^{-1} = A^{-1}A = I\)  
  - \((AB)^{-1} = B^{-1}A^{-1}\)  
  - \((A+B)^{-1} \neq A^{-1}+B^{-1}\)

---

### Determinant & Inverse (2×2)
For \(2 \times 2\) matrix:

$$
A = \begin{bmatrix} a & b \\ c & d \end{bmatrix},\quad
\det(A) = ad - bc
$$

If \(\det(A) \neq 0\), then

$$
A^{-1} = \frac{1}{ad - bc} \begin{bmatrix} d & -b \\ -c & a \end{bmatrix}
$$

General rule: **Inverse exists iff** \(\det(A) \ne 0\).

---

## 4. Elementary Row Transformations
Used in **Gaussian Elimination**:
1. Swap two rows \(R_i \leftrightarrow R_j\).  
2. Multiply a row by a nonzero constant \(\lambda R_i\), \(\lambda \ne 0\).  
3. Add a multiple of one row to another: \(R_i \to R_i + \lambda R_j\).  

**Note**: These do not change the solution set of equations.

---

## 5. Gaussian Elimination
- Goal: Convert system \(Ax=b\) into a simpler form (row echelon or reduced row echelon).  
- Process:
  1. Use pivot rows to eliminate entries below the pivot → upper triangular matrix.  
  2. Continue elimination until row echelon form is reached.  
  3. (Optional) Continue to reduced row echelon form → pivots = 1, only nonzero entry in column.  

### Example (Row Echelon Form)

$$
\begin{bmatrix}
1 & -2 & 1 & -1 & 1 & \vert & 0 \\
0 & 0 & 1 & -1 & 3 & \vert & -2 \\
0 & 0 & 0 & 1 & -2 & \vert & 1 \\
0 & 0 & 0 & 0 & 0 & \vert & a+1
\end{bmatrix}
$$

- If \(a \neq -1\) → no solution.  
- If \(a = -1\) → solutions exist.  

---

## 6. Particular vs General Solution
- **Particular Solution**: One solution obtained directly.  
- **General Solution**: Particular solution + linear combination of solutions to the homogeneous system \(Ax=0\).  
