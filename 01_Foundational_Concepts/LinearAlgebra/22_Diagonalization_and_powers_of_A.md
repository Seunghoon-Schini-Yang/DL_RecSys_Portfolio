# 📚 Lecture 22: Diagonalization and powers of A

**○ Diagonalization**

Suppose $n$ linearly independent eigenvectors $\vec{v}$ of $A$.<br>
```math
S = \begin{bmatrix} \vec{v}_{1} & \vec{v}_{2} & \cdots & \vec{v}_{n} \end{bmatrix}
```
<br>

Then
```math
\begin{align}
AS {} &= A \begin{bmatrix} \vec{v}_{1} & \vec{v}_{2} & \cdots & \vec{v}_{n} \end{bmatrix} \\\\
&= \begin{bmatrix} \lambda_{1}\vec{v}_{1} & \lambda_{2}\vec{v}_{2} & \cdots & \lambda_{n}\vec{v}_{n} \end{bmatrix} \\\\
&= \begin{bmatrix} \vec{v}_{1} & \vec{v}_{2} & \cdots & \vec{v}_{n} \end{bmatrix} \begin{bmatrix}
\lambda_{1} & 0 & \cdots & 0 \\
0 & \lambda_{2} & \cdots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \cdots & \lambda_{n}
\end{bmatrix} \\\\
&= S\Lambda
\end{align}
```
<br>

```math
\therefore \: S^{-1}AS = \Lambda \quad\leftrightarrow\quad S\Lambda S^{-1} = A
```
<br>

- Assume we have full set of $n$ independent eigenvectors of $A$.<br>
then $S$ is invertible.<br>
If not, we can't diagonalize the matrix.

- $A$ is sure to have $n$ independent eigenvectors (and be diagonalizeable)<br>
if all the $\lambda$'s are different. (No repeated $\lambda$'s)<br>

- Repeated eigenvalues : May or may not have $n$ independent eigenvectors.<br>

Example 1)<br>
In this case, need $2$ independent eigenvectors to have $S^{-1}$,<br>
but only one eigenvector exists corresponding to the repeated eigenvector.

```math
\begin{align}
A = \begin{bmatrix} 2 & 1 \\ 0 & 2 \end{bmatrix} \\
\det(A- \lambda I) = \begin{vmatrix} 2-\lambda & 1 \\ 0 & 2-\lambda \end{vmatrix} = (2-\lambda)^{2} = 0 \\
(\lambda_{1}, \vec{v}_{1}) = (\lambda_{2}, \vec{v}_{2}) = (2, \begin{bmatrix} 1 \\ 0 \end{bmatrix})
\end{align}
```
<br>

Example 2)<br>
In this case, there are $2$ independent eigenvectors corresponding to the repeated eigenvalue.<br>
$\therefore \: A$ is diagonalizable and has $S^{-1}$.<br>

```math
\begin{align}
A = \begin{bmatrix} 2 & 0 \\ 0 & 2 \end{bmatrix} \\
\det(A- \lambda I) = \begin{vmatrix} 2-\lambda & 0 \\ 0 & 2-\lambda \end{vmatrix} = (2-\lambda)^{2} = 0 \\\\\\
\lambda_{1} = \lambda_{2} = 2 \quad\rightarrow\quad
\begin{cases}
(\lambda_{1}, \vec{v}_{1}) = (2, \begin{bmatrix} 1 \\ 0 \end{bmatrix}) \\
(\lambda_{2}, \vec{v}_{2}) = (2, \begin{bmatrix} 0 \\ 1 \end{bmatrix}) 
\end{cases} \\\\
\therefore \: S = \begin{bmatrix} \vec{v}_{1} & \vec{v}_{2} \end{bmatrix} = \begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix} = I \quad\leftrightarrow\quad S^{-1} = I
\end{align}
```
<br>

**○ Powers of $A$**

- eigenvalues of $A^{k}$ are the $k$-th powers of the eigenvalues of $A$.<br>
- eigenvectors of $A^{k}$ are the same of the eigenvectors of $A$.<br>

With $\quad A = S\Lambda S^{-1}$,
```math
\begin{cases}
A {} &= S\Lambda S^{-1} \\
A^{2} &= (S\Lambda S^{-1})(S\Lambda S^{-1}) = S\Lambda^{2} S^{-1} \\
\vdots & \quad\vdots \\
A^{k} &= S\Lambda^{k} S^{-1}
\end{cases}
```
<br>

With $\quad A\vec{v} = \lambda \vec{v}$,
```math
\begin{cases}
A\vec{v} {} &= \lambda\vec{v} \\
A^{2}\vec{v} &= A(\lambda \vec{v}) = \lambda (A\vec{v}) = \lambda^{2}\vec{v} \\
\vdots & \quad\vdots \\
A^{k}\vec{v} &= \lambda^{k}\vec{v}
\end{cases}
```
<br>

- $A^{k} \rightarrow 0$ as $k \rightarrow \infty$<br>
if all $|\lambda_{i}| < 1$.<br>
<br>

**○ As sequence**

```math
\begin{align}
\text{For equation}\quad \vec{u}_{k+1} = A\vec{u}_{k}
\quad\text{start with given vector}\quad \vec{u}_{0}. \\
\begin{cases}
\vec{u}_{1} {} &= A\vec{u}_{0} \\
\vec{u}_{2} &= A^{2}\vec{u}_{0} \\
\vdots & \quad\quad\vdots \\
\vec{u}_{k} &= A^{k}\vec{u}_{0}
\end{cases}
\end{align}
```

```math
\text{With}\quad \vec{c} = \begin{bmatrix} c_{1} \\ c_{2} \\ \vdots \\ c_{n} \end{bmatrix} = S^{-1}\vec{u}_{0} \: ,
```
```math
\begin{align}
\vec{u}_{0} {} &= c_{1}\vec{v}_{1} + c_{2}\vec{v}_{2} + \cdots + c_{n}\vec{v}_{n} = S\vec{c} \\\\
\vec{u}_{1} = A\vec{u}_{0} &= c_{1}A\vec{v}_{1} + c_{2}A\vec{v}_{2} + \cdots + c_{n}A\vec{v}_{n} \\
&= c_{1}\lambda_{1} \vec{v}_{1} + c_{2}\lambda_{2} \vec{v}_{2} + \cdots + c_{n}\lambda_{n} \vec{v}_{n} = S\Lambda \vec{c} \\\\
\vec{u}_{k} = A^{k}\vec{u}_{0} &= c_{1}\lambda_{1}^{k} \vec{v}_{1} + c_{2}\lambda_{2}^{k} \vec{v}_{2} + \cdots + c_{n}\lambda_{n}^{k} \vec{v}_{n} = S\Lambda^{k} \vec{c}
\end{align}
```
<br>

- Example : <b>Fibonacci sequence</b>  $(0, 1, 1, 2, 3, 5, 8, ...)$

```math
\begin{align}
\begin{cases}
F_{k+2} = F_{k+1} + F_{k} \\ F_{k+1} = F_{k+1}
\end{cases} {} & \quad\rightarrow\quad
\begin{bmatrix} F_{k+2} \\ F_{k+1} \end{bmatrix} = \begin{bmatrix} 1 & 1 \\ 1 & 0 \end{bmatrix} \begin{bmatrix} F_{k+1} \\ F_{k} \end{bmatrix} \\
& \quad\rightarrow\quad u_{k+1} = Au_{k} \quad\text{(First-order system)}
\end{align}
```
<br>

```math
\text{With}\quad A = \begin{bmatrix} 1 & 1 \\ 1 & 0 \end{bmatrix},
```
```math
\begin{align}
\det(\lambda I - A) = \begin{vmatrix} \lambda-1 & -1 \\ -1 & \lambda \end{vmatrix} = (\lambda-1)\lambda - 1 = \lambda^{2} - \lambda - 1 \\\\
\therefore \: (\lambda_{1}, \lambda_{2}) = (\frac{1+\sqrt{5}}{2}, \frac{1-\sqrt{5}}{2}) \approx (1.618, -0.618) \\
\rightarrow\quad \Lambda = \begin{bmatrix} 1.618 & 0 \\ 0 & -0.618 \end{bmatrix}
\end{align}
```
<br>

```math
\text{with} \: \vec{c} = \begin{bmatrix} c_{1} \\ c_{2} \end{bmatrix} = S^{-1}\vec{u}_{0}
```

```math
\begin{cases}
\quad\vec{u}_{0} {} &= \begin{bmatrix} F_{1} \\ F_{0} \end{bmatrix} = \begin{bmatrix} 1 \\ 0 \end{bmatrix} = S\vec{c} \\
\quad\vec{u}_{k} &= \begin{bmatrix} F_{k+1} \\ F_{k} \end{bmatrix} = A^{k}\vec{u}_{0} = S\Lambda^{k}\vec{c} \\
\vec{u}_{k+1} &= \begin{bmatrix} F_{k+2} \\ F_{k+1} \end{bmatrix} = Au_{k} = A^{k+1}\vec{u}_{0} = S\Lambda^{k+1}\vec{c}
\end{cases}
```

```math
\text{As}\quad k \rightarrow \infty, \quad\text{then}\quad
\Lambda^{k} = \begin{bmatrix} 1.618^{k} & 0 \\ 0 & (-0.618)^{k} \end{bmatrix} \rightarrow \begin{bmatrix} \infty & 0 \\ 0 & 0 \end{bmatrix} 
```

```math
\begin{align}
\therefore \: \lim_{k\to\infty}\vec{u}_{k} {} &= \lim_{k\to\infty} [(c_{1}(1.618)^{k} \vec{v}_{1} + c_{2}(-0.618)^{k} \vec{v}_{2})] \\
& \approx \lim_{k\to\infty} (1.618)^{k}c_{1}\vec{v}_{1} \quad\text{(Blows up to infinity)}
\end{align}
```
