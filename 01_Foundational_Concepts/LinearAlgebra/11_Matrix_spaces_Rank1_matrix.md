# 📚 Lecture 11: Matrix spaces; rank 1 Matrix

**○ Matrix spaces**<br>
Space $M$ = All $(3 \times 3)$ matrices.
```math
\begin{align*}
\text{One of basis for  } M : \begin{bmatrix} 1 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 0 \end{bmatrix}, \begin{bmatrix} 0 & 1 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 0 \end{bmatrix}, \begin{bmatrix} 0 & 0 & 1 \\ 0 & 0 & 0 \\ 0 & 0 & 0 \end{bmatrix}, \cdots, \begin{bmatrix} 0 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 1 & 0 \end{bmatrix}, \begin{bmatrix} 0 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 1 \end{bmatrix} \\\\
dim(M) = 9
\end{align*}
```

- Subspace $S$ = All $(3 \times 3)$ <b>sysmmetric</b> matrices.<br>
$\dim(S) = 6$<br>
- Subspace $U$ = All $(3 \times 3)$ <b>upper triangular</b> matrices.<br>
$\dim(U) = 6$<br>
- Subspace $D$ = $S \cap U$ = All $(3 \times 3)$ <b>diagonal</b> matrices.<br>
$\dim(S \cap U) = \dim(D) = 3$<br>
- $S + U$ = (Any element of $S$) + (Any element of $U$) = All $(3 \times 3)$ matrices = $M$<br>
$dim(S \cap U) + dim(S + U) = 3 + 9 = 12 = 6 + 6 = dim(S) + dim(U)$<br>
<br>

**○ Rank 1 matrix**<br>
Every Rank $1$ marix $A$ has the form of <b>some column times some row</b>.
```math
A = \vec{u}\vec{v}^{T} =  \begin{bmatrix} u_{1} \\ u_{2} \\ \vdots \\ u{_m} \end{bmatrix} \begin{bmatrix} v_{1} & v_{2} & \cdots & v_{n} \end{bmatrix}
```
Example :
```math
\text{(Rank 1 matrix)}\quad A = \begin{bmatrix} 1 & 4 & 5 \\ 2 & 8 & 10 \end{bmatrix} = \begin{bmatrix} 1 \\ 2 \end{bmatrix}\begin{bmatrix} 1 & 4 & 5 \end{bmatrix} = uv^{T}
```
<br>

Rank $1$ matrices are like the <b>building blocks</b> for all matrices.<br>
Break matrix $A$ down as a combination of $\rho(A)$ matrices of rank $1$.
```math
A = \vec{u}_{1}\vec{v}_{1}^{T} + \vec{u}_{2}\vec{v}_{2}^{T} + \cdots + \vec{u}_{\rho(A)}\vec{v}_{\rho(A)}^{T} = \sum_{i=1}^{\rho(A)} \vec{u}_{i}\vec{v}_{i}^{T}
```

Example : $(5 \times 17)$ matrix $A$ of rank $4$.<br>
```math
A = \vec{u}_{1}\vec{v}_{1}^{T} + \vec{u}_{2}\vec{v}_{2}^{T} + \vec{u}_{3}\vec{v}_{3}^{T} + \vec{u}_{4}\vec{v}_{4}^{T} = \sum_{i=1}^{4} \vec{u}_{i}\vec{v}_{i}^{T}
```
<br>

**○ Subspaces**<br>

Question 1 :
- Does $(4 \times 4)$ matrices of rank $3$ form a subspace?<br>

```math
\begin{align*}
A = \begin{bmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & 0 \end{bmatrix},\quad B = \begin{bmatrix} 0 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & 1 \end{bmatrix} \\
A + B = \begin{bmatrix} 1 & 0 & 0 & 0 \\ 0 & 2 & 0 & 0 \\ 0 & 0 & 2 & 0 \\ 0 & 0 & 0 & 1 \end{bmatrix} \\\\
\begin{cases}
rank(A) = rank(B) = 3 \\
rank(A+B) = 4 \not= 3 = rank(A) = rank(B)
\end{cases} \\\\
(4 \times 4) \text{  matrices of rank 3 do not form a subspace.}
\end{align*}
```
<br>

Question 2 :
```math
\text{Subspace}\: S \:\text{: All}\: \vec{v} = \begin{bmatrix} v_{1} \\ v_{2} \\ v_{3} \\ v_{4} \end{bmatrix} \in R^{4} \:\text{with}\: (v_{1} + v_{2} + v_{3} + v_{4} = 0)
```

- What's the dimentsion of $S$?
- What's the basis for $S$?

```math
\begin{align*}
A\vec{v} = \begin{bmatrix} 1 & 1 & 1 & 1 \end{bmatrix} \begin{bmatrix} v_{1} \\ v_{2} \\ v_{3} \\ v_{4} \end{bmatrix} = 0 \\\\\\
\begin{cases}
\dim(C(A)) = Rank(A) = \rho(A) = 1 \\
\dim(N(A)) = \dim(S) = n - \rho(A) = 4 - 1 = 3 \\
\dim(C(A^{T})) = \rho(A) = 1 \\
\dim(N(A^{T})) = m - \rho(A) = 1 - 1 = 0
\end{cases} \\\\\\
\text{One of basis for}\: S : \quad \begin{bmatrix} -1 \\ 1 \\ 0 \\ 0 \end{bmatrix}, \begin{bmatrix} -1 \\ 0 \\ 1 \\ 0 \end{bmatrix}, \begin{bmatrix} -1 \\ 0 \\ 0 \\ 1 \end{bmatrix}
\end{align*}
```
<br>

**○ Linear Differential Equation**<br>
```math
\begin{align*}
\frac{d^{2}y}{dx^{2}} + y = 0 \\\\
y = c_{1}\cos{x} + c_{2}\sin{x} \\
\begin{cases}
\text{Basis :} \quad \cos{x},\: \sin{x} \\
\text{Dimension :} \quad 2
\end{cases}
\end{align*}
```
