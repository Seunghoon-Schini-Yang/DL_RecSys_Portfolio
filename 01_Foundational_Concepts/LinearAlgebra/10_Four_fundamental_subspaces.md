# 📚 Lecture 10: The four fundamental subspaces

### ¶ Four Fundamental Subspaces ¶

Given $(m\times n)$ matrix $A$,<br>
**○ 4 fundamental subspaces**
- Row space : $C(A^{T}) \in R^{n}$
- Column space : $C(A) \in R^{m}$
- Null space : $N(A) = \ker(A) \in R^{n}$
- Left null space : $N(A^{T}) \in R^{m}$

**○ Dimensions**
- Dimensions of row space and column space are equal.<br>
$dim(C(A)) = dim(C(A^{T}))$<br>

- <Column space, Left Null space> $\in R^{m}$<br>
$dim(C(A)) = \rho(A) =$ (Num of pivot variables)<br>
$dim(N(A^{T})) = m - \rho(A)$<br>
$m = dim(C(A)) + dim(N(A^{T}))$<br>
- <Row space, Null space> $\in R^{n}$<br>
$dim(C(A^{T})) = dim(C(A)) = \rho(A)$<br>
$dim(N(A)) = n - \rho(A) =$ (Num of free variables)<br>
$n = dim(C(A^{T})) + dim(N(A))$<br>
<br>

**○ Null space of $A^{T}$**

```math
\begin{align*}
\underset{(m\times m)}E[\underset{(m\times n)}A \underset{(m\times m)}I] = [\underset{(m\times n)}R \underset{(m\times m)}E] \\
→ EA = R
\end{align*}
```
If $A$ is <b>square and invertible</b>, $EA = I$.

- Example :
```math
\begin{align*}
A = \begin{bmatrix} 1 & 2 & 3 & 1 \\ 1 & 1 & 2 & 1 \\ 1 & 2 & 3 & 1 \end{bmatrix} \\\\
\text{Augmented Matrix :}\quad \begin{bmatrix} A & I \end{bmatrix}
= \begin{bmatrix} 1 & 2 & 3 & 1 \\ 1 & 1 & 2 & 1 \\ 1 & 2 & 3 & 1 \end{bmatrix}
\begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{bmatrix} \\
→ \quad \begin{bmatrix} R & E \end{bmatrix}
= \begin{bmatrix} 1 & 0 & 1 & 1 \\ 0 & 1 & 1 & 0 \\ 0 & 0 & 0 & 0 \end{bmatrix}
\begin{bmatrix} -1 & 2 & 0 \\ 1 & -1 & 0 \\ -1 & 0 & 1 \end{bmatrix} \\\\
→ \underbrace{\begin{bmatrix} -1 & 2 & 0 \\ 1 & -1 & 0 \\ -1 & 0 & 1 \end{bmatrix}}_{E} \underbrace{\begin{bmatrix} 1 & 2 & 3 & 1 \\ 1 & 1 & 2 & 1 \\ 1 & 2 & 3 & 1 \end{bmatrix}}_{A} = \underbrace{\begin{bmatrix} 1 & 0 & 1 & 1 \\ 0 & 1 & 1 & 0 \\ 0 & 0 & 0 & 0 \end{bmatrix}}_{R}
\end{align*}
```
$E$ is on the <b>left</b> side of $A$. (Tht's why it's called "Left Null space")<br>
The linear combination of the "third row of $E$" and the "rows of $A$" becomes the "zero row of R".<br>
(Rows of $A$ = Columns of $A^{T}$)<br>
It means that the third row of $E$ is a special solution to $A^{T}\vec{x} = \vec{0}$.

```math
N(A^{T}) = c\begin{bmatrix} -1 \\ 0 \\ 1 \end{bmatrix} ,\quad dim(N(A^{T})) = 1
```
