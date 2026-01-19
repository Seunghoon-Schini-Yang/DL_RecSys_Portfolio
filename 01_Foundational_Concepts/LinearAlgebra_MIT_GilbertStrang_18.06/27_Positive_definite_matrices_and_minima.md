# 📚 Lecture 27: Positive definite matrices and minima

### ¶ Positive definite matrices ¶

**○ Quadratic forms**<br>
Geometrically, quadratic forms describe <b>parabolas</b>, <b>ellipses</b> and <b>energy surfaces</b>.
```math
Q(\vec{x}) = \vec{x}^{T}A\vec{x}
```

Examples :<br>
- $\vec{x}^{T}I\vec{x} = \lVert \vec{x} \rVert^{2} \quad\rightarrow\quad$ circle / sphere<br>
- $\vec{x}^{T}A\vec{x}$ with different eigenvalues $\quad\rightarrow\quad$ ellipse<br>
<br><br>

**○ Definition of positive definite matrices**<br>
A symmetric matrix $A$ is <b>positive definite</b> if
```math
\vec{x}^{T}A\vec{x} > 0 \:\text{for all}\: \vec{x} \not= \vec{0}
```

- Positive semidefinite : $\vec{x}^{T}A\vec{x} \ge 0$<br>
- Indefinite : quadratic form takes both positive and negative values<br>
<br><br>

**○ Eigenvalues and positive definiteness**<br>
A symmetric matrix is positive definite <b>if and only if all its eigenvalues are positive</b>.
<br><br>
Diagonalize $A = Q\Lambda Q^{T}$ (Spectral theorem)

```math
\begin{align}
\vec{x}^{T}A\vec{x} {} &= \vec{x}^{T}Q\Lambda Q^{T}\vec{x} \\
&= (\vec{x}^{T}Q)\Lambda(Q^{T}\vec{x}) \\
&= \vec{y}^{T}\Lambda\vec{y}
&= \sum \lambda_{i} y_{i}^{2} \quad(\vec{y} = Q^{T}\vec{x})
\end{align}
```
If every $\lambda_{i} > 0$, the sum $\sum \lambda_{i} y_{i}^{2}$ is always positive.

This links <b>linear algebra (eigenvalues) to geometry (shape of the quadratic surface)</b>.
<br><br><br><br>


### ¶ Tests for positive definiteness ¶

1. Eigenvalue test
- All eigenvalues $\lambda_{i} > 0$

2. Pivot test (Gaussian elimination)
- All pivots are positive (with no row exchanges)
- Very practical for computation

3. Principal minors <a href="https://en.wikipedia.org/wiki/Sylvester%27s_criterion">(Sylvester’s criterion)</a>
- All leading principal determinants are positive
<br><br><br><br>


### ¶ Linking linear algebra to optimization problems ¶

Positive definite matrices create <b>bowl-shaped quadratic functions</b><br>
whose unique minimum occurs where $A\vec{x} = b$,<br>
<b>linking linear systems, eigenvalues, and optimization into one unified picture</b>.
<br><br>

**○ Minima of quadratic functions**<br>

```math
f(x) = \frac{1}{2}\vec{x}^{T}A\vec{x} - \vec{b}^{T}\vec{x}
```
Above form of function represents
- <b>Energy in physics</b> (ex. Spring system : $\frac{1}{2}kx^{2} - Fx$)
- <b>Error in least square</b>
- <b>Cost in optimization</b>

Taking derivatives
- Gradient : $\nabla f(x) = A\vec{x} - \vec{b}$<br>
- Setting derivative to zero : $A\vec{x} = \vec{b}$<br>
- Hessian : $\nabla^{2} f(x) = A$<br>

If $A$ is positive definite,<br>
then the critical point solving $A\vec{x} = \vec{b}$ is a <b>unique global minimum</b>.<br>
Positive definiteness of $A$ means the function is <b>globally convex with a unique minimum</b>.<br>
This explains why <b>solving linear systems often corresponds to minimizing an energy or error</b>.
<br><br>

**○ Geometry of the minimum**<br>
The surface $\vec{x}^{T}A\vec{x}$ is a <b>bowl</b> if $A$ is positive definite.<br>
The minimum is at the bottom of the bowl.

If eigenvalues are
- large → steep directions
- small → flat directions
<br><br>

**○ Connection to least squares**<br>
In least squares,
```math
A^{T}A\vec{x} = A^{T}\vec{b}
```
- For $(m \times n)$ matrix $A$, $(A^{T}A)$ is always positive semi-definite.<br>
Positive definite if columns of $A$ are independent. (rank = $n$)
```math
\vec{x}^{T}(A^{T}A)\vec{x} = (\vec{x}^{T}A^{T})(A\vec{x}) = (A\vec{x})^{T}(A\vec{x}) = \lVert A\vec{x} \rVert^{2} \ge 0
```

This explains :
- Why least squares has a unique solution
- Why $A^{T}A$ appears naturally in minimization
<br><br>

**○ Physical and practical interpretations**<br>
Positive definite matrices guarantee <b>Stability / Uniqueness / Predictability</b>.
- Mechanical systems : Stiffness matrices
- Electrical networks : Energy dissipation
- Optimization : Convex functions
- Machine learning : Loss functions with unique minima
