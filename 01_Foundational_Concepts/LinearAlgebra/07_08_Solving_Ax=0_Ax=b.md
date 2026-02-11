# 📚 Lecture 7: Solving $A\vec{x} = \vec{0}$ : pivot variables, special solutions

```math
\begin{align*}
A = \begin{bmatrix} 1 & 2 & 2 & 2 \\ 2 & 4 & 6 & 8 \\ 3 & 6 & 8 & 10 \end{bmatrix} → \begin{bmatrix} 1 & 2 & 2 & 2 \\ 0 & 0 & 2 & 4 \\ 0 & 0 & 2 & 4 \end{bmatrix} → \begin{bmatrix} 1 & 2 & 2 & 2 \\ 0 & 0 & 2 & 4 \\ 0 & 0 & 0 & 0 \end{bmatrix} = U \quad\text{(row echelon form)}
\end{align*}
```

We say that $x_{i}$ is a <b>free variable</b>,
if its corresponding column in a row echelon form $U$ is not a pivot column.<br>
We can assign any number "<b>freely</b>" to those free variables.<br>

```math
\begin{align*}
Ux = \begin{bmatrix} 1 & 2 & 2 & 2 \\ 0 & 0 & 2 & 4 \\ 0 & 0 & 0 & 0 \end{bmatrix}
\begin{bmatrix} x_{1} \\ x_{2} \\ x_{3} \\ x_{4} \end{bmatrix} \\
\begin{cases}
\text{pivot variables :} \quad x_{1}, x_{3} \\
\text{free variables :} \quad x_{2}, x_{4}
\end{cases}
\end{align*}
```

- (# of pivot variables) = (rank of $A$) = $\rho(A) = 2$<br>
- (# of free variables) $= (n - \rho(A)) = (4 - 2) = 2$<br>

```math
\begin{align*}
\begin{matrix}
\begin{bmatrix} 1 & 2 & 2 & 2 \\ 0 & 0 & 2 & 4 \\ 0 & 0 & 0 & 0 \end{bmatrix} \\
\text{(row echelon form)}
\end{matrix} \quad → \quad
\begin{matrix}
\begin{bmatrix} 1 & 2 & 0 & -2 \\ 0 & 0 & 1 & 2 \\ 0 & 0 & 0 & 0 \end{bmatrix} \\
\text{(reduced row echelon from)}
\end{matrix} = R = rref(A)
\end{align*}
```
<br>

```math
\begin{align*}
\begin{bmatrix} 1 & 2 & 0 & -2 \\ 0 & 0 & 1 & 2 \\ 0 & 0 & 0 & 0 \end{bmatrix}
\begin{bmatrix} x_{1} \\ x_{2} \\ x_{3} \\ x_{4} \end{bmatrix}
→ \begin{bmatrix} 1 & 0 & 2 & -2 \\ 0 & 1 & 0 & 2 \\ 0 & 0 & 0 & 0 \end{bmatrix}
\begin{bmatrix} x_{1} \\ x_{3} \\ x_{2} \\ x_{4} \end{bmatrix}
\\ \text{(Exhange column 2 and 3)} \\\\\\
R = \begin{bmatrix} \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} & \begin{pmatrix} 2 & -2 \\ 0 & 2 \end{pmatrix} \end{bmatrix} = \begin{bmatrix} \underset{(n_{p}\times n_{p})}I & \underset{(n_{p}\times n_{f})}F \end{bmatrix} \\
\begin{cases}
(I, F) \text{  : (pivot columns, free columns)} \\
(n_{p}, n_{f}) \text{  : (num of pivot variables, num of free variables)}
\end{cases}
\end{align*}
```

Suppose $A$ is a $(m\times n)$ matrix with $m < n$. (More unknowns than equations.)<br>
There will be free variables (at least one).<br>
$\therefore$ There must be non-zero solutions to $A\vec{x} = \vec{0}$.
<br>

**○ Null Space**
```math
\begin{align*}
R\vec{x} = \vec{0} \\\\
→ \begin{bmatrix} I & F \end{bmatrix} \begin{bmatrix} \vec{x}_{pivot} \\ \vec{x}_{free} \end{bmatrix} = O \\\\
→ \begin{bmatrix} \underset{(n_{p}\times n_{p})}I & F \end{bmatrix} \begin{bmatrix} -F \\ \underset{(n_{f}\times n_{f})}I \end{bmatrix} = \underset{(n_{p}\times n_{f})}O \quad\text{(Zero matrix.)}
\end{align*}
```
```math
\text{Null}(R) = \ker(R)\: (\text{Null space of}\: R) \:\text{: The linear combinations of columns of  } \begin{bmatrix} -F \\ I \end{bmatrix} \\
```
<br><br><br>


# 📚 Lecture 8: Solving $A\vec{x} = \vec{b}$ : row reduced form $R$

**○ $x_{n}$ : Special Solutions**
- Specific vectors in the <b>null space</b> of a matrix $A$ for the equation $A\vec{x} = \vec{0}$.<br>
They are found by setting one free variable to $1$ and all other free variables to $0$,<br>
then solving for the pivot variables.<br>
Each free variable generates a unique special solution.


**○ $x_{p}$ : Particular Solution**
- Consider a linear system of equations with infinite solutions.<br>
A particular solution is <b>one solution out of the infinite set of possible solutions</b>.<br>
The easiest way to find a particular solution is to <b>pick values for the free variables</b>,<br>
which then determines the values of the pivot variables.<br>

**○ Solvability**<br>
- $A\vec{x} = \vec{b}$ is solvable when $\vec{b} \in C(A)$.
- If a combination of rows of $A$ gives zero row, then same combination of entities of $\vec{b}$ must give 0.

```math
\begin{align*}
\text{Augemented matrix :}\quad \begin{bmatrix} A & \vec{b} \end{bmatrix}
= \begin{bmatrix} 1 & 2 & 2 & 2 & b_{1} \\ 2 & 4 & 6 & 8 & b_{2} \\ 3 & 6 & 8 & 10 & b_{3} \end{bmatrix} → \begin{bmatrix} 1 & 2 & 2 & 2 & b_{1} \\ 0 & 0 & 2 & 4 & b_{2}-2b_{1} \\ 0 & 0 & 0 & 0 & b_{3}-b_{2}-b_{1} \end{bmatrix} \\\\
b_{3}-b_{2}-b_{1} = 0
\end{align*}
```
$[1, 5, 6]$ satisfying $b_{3}-b_{2}-b_{1} = 0$ can be $\vec{b}$.<br>

```math
\vec{b} = \begin{bmatrix} b_{1} \\ b_{2} \\ b_{3} \end{bmatrix} = \begin{bmatrix} 1 \\ 5 \\ 6 \end{bmatrix}
```

To find complete solution to $A\vec{x} = \vec{b}$.
1. $\vec{x}_{particular} = \vec{x}_{p}$
- Set all free variables to zero.
- Solve $A\vec{x} = \vec{b}$ for pivot variables.

```math
\begin{align*}
\begin{bmatrix} 1 & 2 & 2 & 2 \\ 0 & 0 & 2 & 4 \\ 0 & 0 & 0 & 0 \end{bmatrix}
\begin{bmatrix} x_{1} \\ x_{2} \\ x_{3} \\ x_{4} \end{bmatrix}
= \begin{bmatrix} 1 \\ 3 \\ 0 \end{bmatrix}
= \begin{bmatrix} b_{1} \\ b_{2}-2b_{1} \\ b_{3}-b_{2}-b_{1} \end{bmatrix} \\
\begin{cases}
\text{pivot variables :} \quad x_{1}, x_{3} \\
\text{free variables :} \quad x_{2}, x_{4}
\end{cases} \\\\
\vec{x}_{p} = \begin{bmatrix} -2 \\ 0 \\ \frac{3}{2} \\ 0 \end{bmatrix} \quad
\begin{cases}
x_{2} = x_{4} = 0 \quad\text{(Set free variables zero.)} \\
2x_{1} + 2x_{3} = 1 \\ 2x_{3} = 3
\end{cases}
\end{align*}
```

2. $\vec{x}_{nullspace} = \vec{x}_{n}$

```math
\begin{align*}
\begin{bmatrix} 1 & 2 & 2 & 2 \\ 0 & 0 & 2 & 4 \\ 0 & 0 & 0 & 0 \end{bmatrix}
\begin{bmatrix} x_{1} \\ x_{2} \\ x_{3} \\ x_{4} \end{bmatrix}
= \begin{bmatrix} 0 \\ 0 \\ 0 \end{bmatrix} \\
\begin{cases}
\text{pivot variables :} \quad x_{1}, x_{3} \\
\text{free variables :} \quad x_{2}, x_{4}
\end{cases} \\\\
\vec{x}_{n} = c_{1}\vec{x}_{n1} + c_{2}\vec{x}_{n2}
= c_{1}\begin{bmatrix} -2 \\ 1 \\ 0 \\ 0 \end{bmatrix} + c_{2}\begin{bmatrix} 2 \\ 0 \\ -2 \\ 1 \end{bmatrix} \quad
\begin{cases}
(x_{2}, x_{4}) = (1, 0) \quad\text{for}\quad \vec{x}_{n1} \\
(x_{2}, x_{4}) = (0, 1) \quad\text{for}\quad \vec{x}_{n2}
\end{cases}
\end{align*}
```

- $\vec{x}_{complete}$

```math
\begin{align*}
\vec{x}_{complete} = \vec{x}_{particular} + \vec{x}_{nullspace} {}
&= \vec{x}_{p} + \vec{x}_{n} \\\\
&= \begin{bmatrix} -2 \\ 0 \\ \frac{3}{2} \\ 0 \end{bmatrix} + c_{1}\begin{bmatrix} -2 \\ 1 \\ 0 \\ 0 \end{bmatrix} + c_{2}\begin{bmatrix} 2 \\ 0 \\ -2 \\ 1 \end{bmatrix}
\end{align*}
```
<br>

Plot all solutions $\vec{x}_{complete} \in R_{4}$.<br>
Then "two-dimensional subspace (a plane) that doesn't go through the origin" comes out.

```math
\begin{align*}\begin{cases}
\vec{x}_{n} \quad\text{: Two-dimensional subspace (a plane)} \\
\vec{x}_{p} \quad\text{: Doesn't go through the origin}
\end{cases}\end{align*}
```
<br>

**○ Rank**
- $\rho(A)$ : Rank of $(m \times n)$ matrix $A$.

- Num of pivot variables cannot be bigger than $n$ and $m$.<br>
$\rho(A) <= m$ and $\rho(A) <= n$<br>

- Full column rank : $\rho(A) = n < m$.<br>
In this case, there are no free variables.<br>
Null space $\ker(A) = O$ and $\vec{x}_{n} = 0$.<br>
$\therefore\: \vec{x} = \vec{x}_{p} + \vec{x}_{n} = \vec{x}_{p}$<br>
This system has only one unique solution if it exists.<br>
(= This system has either $0$ or $1$ solution.)
```math
R = \begin{bmatrix} I \\ O \end{bmatrix}
```

- Full row rank : $\rho(A) = m < n$<br>
In this case, we can solve $A\vec{x} = \vec{b}$ for every $\vec{b}$.<br>
Left with $(n - \rho(A) = n - m)$ free variables.<br>
This system has $\infty$ solutions.
```math
R = \begin{bmatrix} I & F \end{bmatrix}
```

- Full rank : $\rho(A) = m = n$<br>
In this case, $A$ is <b>invertible</b>.<br>
$rref(A) = I$ (Reduced row echelon form of $A$ is $I$.)<br>
This system has only $1$ solution.

- $\rho(A) < m$ and $\rho(A) < n$<br>
This system has no solution or $\infty$ solutions.
```math
R = \begin{bmatrix} I & F \\ 0 & 0 \end{bmatrix}
```
