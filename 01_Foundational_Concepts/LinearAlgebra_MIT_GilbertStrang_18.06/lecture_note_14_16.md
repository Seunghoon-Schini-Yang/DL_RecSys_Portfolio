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
<br>

- Null space and Row space are <b>orthogonal complements</b> in $`R^{n}`$.

```math
\begin{cases}
C(A^{T}) \perp N(A) \\
n = dim(C(A^{T})) + dim(N(A))
\end{cases}
```
<br><br>

- $`A^{T}A`$ is <b>Square</b> and <b>Symmetric</b><br>
Square : $`(n \times m) \cdot (m \times n) = (n \times n)`$<br>
Symmetric : $`(A^{T}A)^{T} = A^{T}A`$

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
<br><br>

- From ① and ②, $`N(A) = N(A^{T}A)`$

```math
\begin{align}
\text{①}\quad \begin{cases}
\text{If}\quad \vec{x} \in N(A) \quad (A\vec{x} = \vec{0}) \\
\text{then}\quad \vec{x} \in N(A^{T}A) \quad (A^{T}A\vec{x} = A^{T}\vec{0} = \vec{0}) \\
\text{Thus}\quad N(A) \subset N(A^{T}A)
\end{cases} \\\\

\text{②}\quad \begin{cases}
\text{If}\quad \vec{x} \in N(A^{T}A) \quad (A^{T}A\vec{x} = \vec{0}) \\
\text{then}\quad \vec{x} \in N(A) \quad (A\vec{x} = \vec{0}) \\
\Big( \because\quad \vec{x}^{T}(A^{T}A)\vec{x} = (\vec{x}^{T}A^{T})(A\vec{x}) = (A\vec{x})^{T}(A\vec{x}) = \lVert A\vec{x} \rVert^{2} = 0 \Big) \\
\text{Thus}\quad N(A^{T}A) \subset N(A)
\end{cases}
\end{align}
```

- $`rank(A) = rank(A^{T}A)`$<br>
$`\Big( \because\quad rank(A) = n - dim(N(A)) = n - dim(N(A^{T}A)) = rank(A^{T}A) \Big)`$

<br><br><br>

# 📚 Lecture 15: Projections onto subspaces

**○ Projections**
<p align="center">
    <img src="images/lecture_15_01.jpg" alt="img_15_01" width="400">
</p>

```math
\begin{align}
\text{For}\quad \vec{\underset{(n \times 1)}a}, \vec{\underset{(n \times 1)}b} \quad
\begin{cases}
\vec{a}^{T}(\vec{b} - k\vec{a}) = 0 \\
k\vec{a}^{T}\vec{a} = \vec{a}^{T}\vec{b} \\
k = \frac{\vec{a}^{T}\vec{b}}{\vec{a}^{T}\vec{a}}
\end{cases} \\\\

\text{proj.}\quad \vec{p} = \vec{a}k = \vec{a}\frac{\vec{a}^{T}\vec{b}}{\vec{a}^{T}\vec{a}}
= (\frac{\vec{a}\vec{a}^{T}}{\vec{a}^{T}\vec{a}})\vec{b} = \underset{(n \times n)}P\vec{b} \\\\
P = \frac{\vec{a}\vec{a}^{T}}{\vec{a}^{T}\vec{a}}
\end{align}
```

$C(P)$ : Line through $\vec{a}$<br>
$rank(P) = 1$<br>

- Why project?<br>
Because $A\vec{x} = \vec{b}$ may have no solution.<br>
To choose the closest vector in the column space,<br>
solve $A\vec{\hat{x}} = \vec{p}$ instead of $\vec{b}$.<br>
($\vec{p}$ : proj. of $\vec{b}$ onto the column space.)<br>

plane of $(\vec{a_{1}}, \vec{a_{2}}) = C(A)$ (→ Column space of $A$)<br>
$(A = [\vec{a_{1}} \vec{a_{2}}])$<br>
$\vec{p} = \hat{x_{1}}\vec{a_{1}} + \hat{x_{2}}\vec{a_{2}} = A\vec{\hat{x}}$<br><br>
Find $\vec{\hat{x}}$<br>
key : $(\vec{e} = \vec{b}-\vec{p} = \vec{b}-A\vec{\hat{x}})$ is perpendicular to the plane.

```math
\begin{align}
\vec{e} (= \vec{b}-A\vec{x}) \in N(A^{T}) \\
\vec{e} \perp C(A)
\end{align}
```

```math
\begin{align}
\begin{cases}
\vec{a_{1}}^{T}(\vec{b}-A\vec{\hat{x}}) = 0 \\
\vec{a_{2}}^{T}(\vec{b}-A\vec{\hat{x}}) = 0
\end{cases} \\\\
\text{→}\quad \begin{bmatrix} \vec{a_{1}}^{T} \\ \vec{a_{2}}^{T} \end{bmatrix} (\vec{b}-A\vec{\hat{x}}) = A^{T} (\vec{b}-A\vec{\hat{x}}) = \begin{bmatrix} 0 \\ 0 \end{bmatrix} \\\\
\begin{cases}
A^{T}A\vec{\hat{x}} = A^{T}\vec{b} \\
\vec{\hat{x}} = (A^{T}A)^{-1}A^{T}\vec{b} \\
\vec{\hat{p}} = A\vec{\hat{x}} = A(A^{T}A)^{-1}A^{T}\vec{b} = P\vec{b} \end{cases} \\
\text{→}\quad\therefore\quad P = A(A^{T}A)^{-1}A^{T} \\
\end{align}
```

- $P^{T} = P$ : Symmetric<br>

```math
\begin{align}
P^{T} {} &= (A(A^{T}A)^{-1}A^{T})^{T} \\
&= (A^{T})^{T}((A^{T}A)^{-1})^{T}A^{T} \\
&= A(A^{T}A)^{-1}A^{T} \quad<\because\quad (M^{-1})^{T} = (M^{T})^{-1}> \\
&= P
\end{align}
```

- $P^{2} = P$ : Project twice, get the same answer as did in the first projection.<br>

```math
\begin{align}
P^{2} = PP {} &= (A(A^{T}A)^{-1}A^{T})(A(A^{T}A)^{-1}A^{T}) \\
&= A(A^{T}A)^{-1}(A^{T}A)(A^{T}A)^{-1}A^{T} \\
&= A(A^{T}A)^{-1}A^{T} \\
&= P
\end{align}
```

<br><br><br>

# 📚 Lecture 16: Projection matrices and least squares

- If $\vec{b}$ $\in$ column space, then $P\vec{b} = \vec{b}$
```math
\begin{align}
P\vec{b} {} &= A(A^{T}A)^{-1}A^{T}\vec{b} \\
&= A(A^{T}A)^{-1}A^{T}A\vec{x} \quad (\vec{b} = A\vec{x}, \quad \because \ \vec{b} \in \text{column space}) \\
&= A\vec{x} \\
&= \vec{b}
\end{align}
```
<br>

- If $\vec{b}$ $\perp$ column space, then $P\vec{b} = \vec{0}$
```math
\begin{align}
P\vec{b} {} &= A(A^{T}A)^{-1}A^{T}\vec{b} \\
&= A(A^{T}A)^{-1}\vec{0} \quad (A^{T}\vec{b} = \vec{0}, \quad \because \ \vec{b} \perp \text{column space}) \\
&= \vec{0}
\end{align}
```
<br>

- $(I-P)$ is proj. onto $N(A^{T})$.

```math
\begin{align}
\vec{e} {} &= \vec{b} - \vec{p} \\
&= I\vec{b} - P\vec{b} \\
&= (I-P)\vec{b}
\end{align}
```

```math
\begin{align}
\vec{b} {} &= \vec{p} + \vec{e} \\
&= P\vec{b} + (I-P)\vec{b}
\end{align}
```

<br>

**○ Least Squares**

- Fitting by a line<br>
For 3 points : $[(1,1), (2,2), (3,2)]$

<!-- ![LeastSquares-15-01](images/lecture_15_02.jpg) -->
<p align="center">
    <img src="images/lecture_15_02.jpg" alt="img_15_02" width="400">
</p>

```math
\begin{align}
b = c + dt \\\\
\begin{cases}
c + d = 1 \\
c + 2d = 2 \\
c + 3d = 2
\end{cases} \\\\
A\vec{x} = \vec{b} \quad\text{→}\quad \begin{bmatrix} 1 & 1 \\ 1 & 2 \\ 1 & 3 \end{bmatrix}\begin{bmatrix} c \\ d \end{bmatrix} = \begin{bmatrix} 1 \\ 2 \\ 2 \end{bmatrix}
\end{align}
```

There is no solution for this system,<br>
but we can find the best solution by multiplying $A^{T}$.

```math
(A\vec{x} = \vec{b}) \quad\text{→}\quad (A^{T}A\vec{\hat{x}} = A^{T}\vec{b})
```
<br>

- 2 ways to find $\vec{\hat{x}}$

```math
\vec{\hat{x}} = \begin{bmatrix} \hat{c} \\ \hat{d} \end{bmatrix}
```
<br>

1) Solve $A^{T}A\vec{\hat{x}} = A^{T}\vec{b}$

```math
\begin{align}
\begin{cases}
A^{T}A = \begin{bmatrix} 1 & 1 & 1 \\ 1 & 2 & 3 \end{bmatrix}\begin{bmatrix} 1 & 1 \\ 1 & 2 \\ 1 & 3 \end{bmatrix} = \begin{bmatrix} 3 & 6 \\ 6 &  14 \end{bmatrix} \\
A^{T}\vec{b} = \begin{bmatrix} 1 & 1 & 1 \\ 1 & 2 & 3 \end{bmatrix}\begin{bmatrix} 1 \\ 2 \\ 2 \end{bmatrix} = \begin{bmatrix} 5 \\ 11 \end{bmatrix} \quad
\end{cases} \\\\

A^{T}A\vec{\hat{x}} = A^{T}\vec{b} \quad \text{→} \quad
\begin{bmatrix} 3 & 6 \\ 6 & 14 \end{bmatrix}\begin{bmatrix} \hat{c} \\ \hat{d} \end{bmatrix} = \begin{bmatrix} 5 \\ 11 \end{bmatrix} \\

\begin{cases}
3\hat{c} + 6\hat{d} = 5 \\
6\hat{c} + 14\hat{d} = 11
\end{cases} \quad \text{→} \quad
\begin{cases}
\hat{c} = \frac{2}{3} \\
\hat{d} = \frac{1}{2} \\
\end{cases}
\end{align}
```

2) Minimize $\lVert A\vec{\hat{x}} - \vec{b} \rVert^{2} {} = \lVert \vec{e} \rVert^{2}$

```math
\begin{align}
\lVert A\vec{\hat{x}} - \vec{b} \rVert^{2} {} &= \lVert \vec{e} \rVert^{2} \\
&= e_{1}^{2} + e_{2}^{2} + e_{3}^{2} \\
&= (\hat{c}+\hat{d}-1)^{2} + (\hat{c}+2\hat{d}-2)^{2} + (\hat{c}+3\hat{d}-2)^{2} \\
&= 3\hat{c}^{2} + 14\hat{d}^{2}+9+12\hat{c}\hat{d}-10\hat{c}-22\hat{d} \\
&= f(\hat{c},\hat{d})
\end{align}
```

```math
\begin{align}
\text{Minimize} \quad f(\hat{c},\hat{d}) \quad \begin{cases}
\frac{\partial f}{\partial \hat{c}} = 6\hat{c} + 12\hat{d} - 10 = 0 \\
\frac{\partial f}{\partial \hat{d}} = 12\hat{c} + 28\hat{d} - 22 = 0
\end{cases} \quad \text{→} \quad
\begin{cases}
\hat{c} = \frac{2}{3} \\
\hat{d} = \frac{1}{2} \\
\end{cases}
\end{align}
```
<br>

- Find $\vec{p}$ and $\vec{e}$.

<p align="center">
    <img src="images/lecture_15_03.jpg" alt="img_15_03" width="500">
</p>

```math
\begin{align}
\vec{p} = \hat{c} + \hat{d}\vec{t} {} &= \frac{2}{3} + \frac{1}{2}\vec{t} \\
&= \begin{bmatrix} \frac{2}{3} \\ \frac{2}{3} \\ \frac{2}{3} \end{bmatrix} + \frac{1}{2}\begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix}
= \begin{bmatrix} \frac{7}{6} \\ \frac{5}{3} \\ \frac{13}{6} \end{bmatrix}
\end{align}
```

```math
\vec{e} = \vec{b} - \vec{p} = \begin{bmatrix} 1 \\ 2 \\ 2 \end{bmatrix} - \begin{bmatrix} \frac{7}{6} \\ \frac{5}{3} \\ \frac{13}{6} \end{bmatrix} = \begin{bmatrix} -\frac{1}{6} \\ \frac{1}{3} \\ -\frac{1}{6} \end{bmatrix}
```
<br>

- $\vec{e}$ is<br>
: orthogonal to $C(A)$. (column space of A)<br>
: perpendicular to $\vec{p}$. $(\because \: \vec{p} \in C(A))$

<p align="center">
    <img src="images/lecture_15_04.jpg" alt="img_15_04" width="500">
</p>

```math
\begin{align}
\vec{e} \cdot \vec{p} = 0 \quad (\because \: \vec{e} \perp \vec{p}) \\\\
\vec{e}^{T}A = \begin{bmatrix} 1 & 1 \\ 1 & 2 \\ 1 & 3 \end{bmatrix} = \begin{bmatrix} 0 & 0 \end{bmatrix} \quad (\because \: \vec{e} \perp C(A))
\end{align}
```
<br>

- If $A$ has independent columns, then $A^{T}A$ is invertible.<br>
Suppose $A^{T}A\vec{x} = 0$, then $\vec{x}$ must be $\vec{0}$ for $A^{T}A$ to be invertible.
```math
\begin{align}
A^{T}A\vec{x} = \vec{0} \quad\text{→}\quad
\begin{cases}
\vec{x}^{T}A^{T}A\vec{x} = 0 \\
(A\vec{x})^{T}(A\vec{x}) = \lVert A\vec{x} \rVert^{2} = 0 \\
A\vec{x} = \vec{0}
\end{cases} \\
\text{→}\quad \vec{x} = \vec{0} \quad (\because \: A \: \text{has independent columns.}) \\
\text{→}\quad \therefore \: A^{T}A \: \text{is invertible.}
\end{align}
```
<br>

- Columns definitely independent if they are perpendicular unit vectors. (= Orthonormal)
```math
\text{ex)} \quad \begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix}, \begin{bmatrix} 0 \\ 1 \\ 0 \end{bmatrix}, \begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix}
```

