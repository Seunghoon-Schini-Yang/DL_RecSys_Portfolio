# 📚 Lecture 14: Orthogonal vectors and subspaces

- When vectors $x$ and $y$ are orthogonal (or perpendicular),

```math
\begin{align}
x^{T}y = 0 \\
\lVert x \rVert^{2} + \lVert y \rVert^{2} = \lVert x+y \rVert^{2} \\\\

\begin{cases}
x^{T}x + y^{T}y = (x+y)^{T}(x+y) = x^{T}x + x^{T}y + y^{T}x + y^{T}y \\
x^{T}y + y^{T}x = 2x^{T}y = 0 \\
x^{T}y = 0
\end{cases} \\
\end{align}
```
<br>

- "Subspace $`S`$ is orthogonal to subspace $`T`$" means, <br>
→ Every vector in $`S`$ is orthogonal to every vector in $`T`$.

```math
s^{T}t = 0 \quad (\vec{s} \in S, \vec{t} \in T)
```
<br>

- Row space is orthogonal to Null space.<br>
Null space and Row space are <b>orthogonal complements</b> in $`R^{n}`$.

```math
\begin{align}
Ax = \begin{bmatrix} \vec{row_{1}} \\ \vec{row_{2}} \\ \vdots \\ \vec{row_{m}} \end{bmatrix} \begin{bmatrix} x_{1} \\ x_{2} \\ \vdots \\ x_{n} \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \\ \vdots \\ 0 \end{bmatrix} \\\\
\begin{cases}
\text{Row space :}\quad (c_{1}\vec{row_{1}} + c_{2}\vec{row_{2}} + \cdots + c_{m}\vec{row_{m}}) \\
\text{Null space :}\quad \begin{bmatrix} x_{1} \\ x_{2} \\ \vdots \\ x_{n} \end{bmatrix}
\end{cases} \\
(c_{1}\vec{row_{1}} + c_{2}\vec{row_{2}} + \cdots + c_{m}\vec{row_{m}}) \begin{bmatrix} x_{1} \\ x_{2} \\ \vdots \\ x_{n} \end{bmatrix} = 0 \\\\
\text{(All vectors from Row space)} \quad\perp\quad \text{(All vectors from Null space)}
\end{align}
```
<br><br>

- $`A^{T}A`$ : Square, Symmetric

- $`Ax = b`$ has solution when <b>$`A^{T}A`$ is invertible.</b>

```math
\begin{cases}
Ax = b \\
(A^{T}A)x = A^{T}b
\end{cases}
```
<br>

- $`A^{T}A`$ is <b>invertible</b> exactly if A has <b>independent columns</b>.<br>

- If $`A`$ has dependent columns, then so does $`A^{T}A`$.<br>
→ This means $`A^{T}A`$ is <b>not invertible</b>.

When ($i$-th, $j$-th) columns of $`A`$ are dependent,

```math
\begin{align}
\underset{(m \times n)}{A} = \begin{bmatrix} \cdots & \vec{col_{i}} & \cdots & \vec{col_{j}} & \cdots \end{bmatrix} \quad (\vec{col_{j}} = k*\vec{col_{i}}) \\\\
\underset{(n \times m)}{A^{T}} = \begin{bmatrix} \vdots \\ \vec{row_{i}} \\ \vdots \\ \vec{row_{j}} \\ \vdots \end{bmatrix} \quad (\vec{row_{j}} = \vec{col_{j}}^{T} = k*\vec{col_{i}}^{T} = k*\vec{row_{i}})
\end{align}
```

then ($i$-th, $j$-th) rows and columns of $A^{T}A$ are dependent.

```math
\begin{align}
\underset{(n \times n)}{A^{T}A} \quad
\begin{cases}
= \begin{bmatrix} \cdots & \vec{col_{i}} & \cdots & \vec{col_{j}} & \cdots \end{bmatrix} \quad (\vec{col_{j}} = k*\vec{col_{i}}) \\
= \begin{bmatrix} \vdots \\ \vec{row_{i}} \\ \vdots \\ \vec{row_{j}} \\ \vdots \end{bmatrix} \quad (\vec{row_{j}} = \vec{col_{j}}^{T} = k*\vec{col_{i}}^{T} = k*\vec{row_{i}})
\end{cases}
\end{align}
```

Example)

```math
\begin{align}\begin{cases}
A = \begin{bmatrix} 1 & 3 \\ 1 & 3 \\ 1 & 3 \end{bmatrix} \quad (rank(A) = \Gamma = 1) \\
A^{T}A = \begin{bmatrix} 1 & 1 & 1 \\ 3 & 3 & 3 \end{bmatrix} \begin{bmatrix} 1 & 3 \\ 1 & 3 \\ 1 & 3 \end{bmatrix} = \begin{bmatrix} 3 & 9 \\ 9 & 27 \end{bmatrix} \quad (rank(A^{T}A) = 1)
\end{cases}\end{align}
```

- $`rank(A) = rank(A^{T}A)`$

- $`N(A) = N(A^{T}A)`$




