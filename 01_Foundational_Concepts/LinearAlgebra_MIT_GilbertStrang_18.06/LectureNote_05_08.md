# 📚 Lecture 5: Transposes, permutations, spaces $R^n$

<br>**○ Symmetric**

```math
\begin{align*}
R = \begin{bmatrix} a & b & c \\ d & e & f \end{bmatrix} \\
RR^{T} \quad \text{: Why symmetric?} \\
(RR^{T})^{T} = RR^{T} \quad \text{: This is why.}
\end{align*}
```

<br>**○ Vector Spaces**
- Vector spaces has to be closed under <b>multiplication and addition</b> of vectors.
<br>In other words, <b>linear combinations</b>.

Ex1) The first quadrant ($Q1$) is not a vector space.
<br>It's not closed under multiplication by all real numbers.<br>$(-1) * (3, 2) = (-3, -2) \not\in Q1$ 

Ex2) $R^{2}$ Space is a vector space.


<br>**○ Subpaces**

- Subspaces of $R^{2}$
1. All of $R^{2}$
2. Any line through zero vector
3. Zero vector

Every subspace has got to contain zero vector.

<br>**○ Column Space**

- All linear combinations from columns of A form a subspace called <b>column space</b>.

```math
A = \begin{bmatrix} 1 & 3 \\ 2 & 3 \\ 4 & 1 \end{bmatrix}
\quad\text{→} \quad C(A) \quad\text{(Column space of A)} 
```
<br>

- Take all their linear combinations, we can fill out the whole plane.

```math
C(A) = R^{2} \quad : \quad
a\begin{bmatrix} 1 \\ 2 \\ 4 \end{bmatrix} + b\begin{bmatrix} 3 \\ 3 \\ 1 \end{bmatrix}
```

<br><br><br>

# 📚 Lecture 6: Column space and null space

<br>**○ For subspaces $S$ and $T$, intersection $S \cap T$ is a subspace.**

```math
\begin{align*}
\text{When two vectors}\quad \vec{v}, \vec{w} \quad \text{in}\quad S \cap T \\
\text{then}\quad \begin{rcases}
a\vec{v}+b\vec{w} \in S \\
a\vec{v}+b\vec{w} \in T
\end{rcases} \quad\text{(Linear Combinations)} \\
\text{So,}\quad a\vec{v}+b\vec{w} \in S \cap T
\end{align*}
```
<br>

<br>**○ Column Space**

```math
\begin{align*}
A = \begin{bmatrix} 1 & 1 & 2 \\ 2 & 1 & 3 \\ 3 & 1 & 4 \\ 4 & 1 & 5 \end{bmatrix} \\
C(A) = \begin{cases}
\text{Column Space of  } A \\
\text{All linear combinations of columns of  } A
\end{cases}
\end{align*}
```
<br>

- Does $C(A)$ fill the full 4-dimensional space $R^{4}$ ?<br>
- Does $Ax = b$ have a solution for every $b \in R^{4}$ ?<br>
- Which $b$'s allow this system to be solved?<br>
→ Can solve $Ax=b$ exactly when $b \in C(A)$.<br>

```math
Ax = \begin{bmatrix} 1 & 1 & 2 \\ 2 & 1 & 3 \\ 3 & 1 & 4 \\ 4 & 1 & 5 \end{bmatrix}\begin{bmatrix} x_{1} \\ x_{2} \\ x_{3} \end{bmatrix} = \begin{bmatrix} b_{1} \\ b_{2} \\ b_{3} \\ b_{4} \end{bmatrix} = b
```

<br>**○ Null Space**

- Null Space is a vector space.

```math
\begin{align*}
Ax = \begin{bmatrix} 1 & 1 & 2 \\ 2 & 1 & 3 \\ 3 & 1 & 4 \\ 4 & 1 & 5 \end{bmatrix}\begin{bmatrix} x_{1} \\ x_{2} \\ x_{3} \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \\ 0 \\ 0 \end{bmatrix} \\
\text{In this system,}\quad x \quad\text{can be}\quad \begin{bmatrix} 0 \\ 0 \\ 0 \end{bmatrix} \quad\text{or}\quad \begin{bmatrix} 1 \\ 1 \\ -1 \end{bmatrix} \quad\text{or else.}
\end{align*}
```

Solutions to $Ax = 0$ always give a subspace. (Contain zero vector at least.)<br>
$N(A)$ (Null space of $A$) always contains zero vector.

```math
\begin{align*}
\text{If}\quad Av = 0 \quad\text{and}\quad Aw = 0, \\
\text{then} \quad\begin{cases}
A(v+w) = 0 \quad\text{(Addition)} \\
A(cv) = 0 \quad\text{(Multiplication)}
\end{cases} \\
\text{So, null space is a vector space.}
\end{align*}
```
<br>

- When $b \not= 0$, the set of solutions is not a vector space.

```math
Ax = \begin{bmatrix} 1 & 1 & 2 \\ 2 & 1 & 3 \\ 3 & 1 & 4 \\ 4 & 1 & 5 \end{bmatrix}\begin{bmatrix} x_{1} \\ x_{2} \\ x_{3} \end{bmatrix} = \begin{bmatrix} 1 \\ 2 \\ 3 \\ 4 \end{bmatrix}
```

In this case, the set of solutions $x$ does not have zero vector. (Zero vector is not a solution.)<br>
<b>Vector spaces have to go though the origin.</b><br>
That's why the solutions for this system can't be a vector space.

<br><br><br>

# 📚 Lecture 7: Solving Ax = 0: pivot variables, special solutions

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

"Rank of $A$" = "# of pivot variables" = $r$ = $2$<br>
"# of free variables" = $n - r$ = $4 - 2$ = 2<br>

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

- Null Space

```math
\begin{align*}
Rx = 0 \\\\
→ \begin{bmatrix} I & F \end{bmatrix} \begin{bmatrix} x_{pivot} \\ x_{free} \end{bmatrix} = 0 \\\\
→ \begin{bmatrix} \underset{(n_{p}\times n_{p})}I & F \end{bmatrix} \begin{bmatrix} -F \\ \underset{(n_{f}\times n_{f})}I \end{bmatrix} = \underset{(n_{p}\times n_{f})}0 \quad\text{(Zero matrix.)}
\end{align*}
```

```math
\begin{align*}
N(R) \text{  (Null space of  } R  \text{ ) : The linear combinations of columns of  } \begin{bmatrix} -F \\ I \end{bmatrix} \\
N = \begin{bmatrix} -F \\ I \end{bmatrix}
\end{align*}
```

<br><br><br>

# 📚 Lecture 8: Solving Ax = b: row reduced form R

Solvability

- $Ax = b$ is solvable when $b$ is in $C(A)$.
- If a combination of rows of $A$ gives zero row, then same combination of entities of $b$ must give 0.

```math
\begin{align*}
\text{Augemented matrix :}\quad \begin{bmatrix} A & b \end{bmatrix}
= \begin{bmatrix} 1 & 2 & 2 & 2 & b_{1} \\ 2 & 4 & 6 & 8 & b_{2} \\ 3 & 6 & 8 & 10 & b_{3} \end{bmatrix} → \begin{bmatrix} 1 & 2 & 2 & 2 & b_{1} \\ 0 & 0 & 2 & 4 & b_{2}-2b_{1} \\ 0 & 0 & 0 & 0 & b_{3}-b_{2}-b_{1} \end{bmatrix} \\\\
b_{3}-b_{2}-b_{1} = 0
\end{align*}
```
$[1, 5, 6]$ satisfying $b_{3}-b_{2}-b_{1} = 0$ can be $b$.<br>

```math
b = \begin{bmatrix} b_{1} \\ b_{2} \\ b_{3} \end{bmatrix} = \begin{bmatrix} 1 \\ 5 \\ 6 \end{bmatrix}
```

To find complete solution to $Ax = b$.
1. $x_{particular} = x_{p}$
- Set all free variables to zero.
- Solve $Ax = b$ for pivot variables.

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
x_{p} = \begin{bmatrix} -2 \\ 0 \\ \frac{3}{2} \\ 0 \end{bmatrix} \quad
\begin{cases}
x_{2} = x_{4} = 0 \quad\text{(Set free variables zero.)} \\
2x_{1} + 2x_{3} = 1 \\ 2x_{3} = 3
\end{cases}
\end{align*}
```

2. $x_{nullspace} = x_{n}$

```math
\begin{align*}
\begin{bmatrix} 1 & 2 & 2 & 2 \\ 0 & 0 & 2 & 4 \\ 0 & 0 & 0 & 0 \end{bmatrix}
\begin{bmatrix} x_{1} \\ x_{2} \\ x_{3} \\ x_{4} \end{bmatrix}
= \begin{bmatrix} 0 \\ 0 \\ 0 \end{bmatrix} \\
\begin{cases}
\text{pivot variables :} \quad x_{1}, x_{3} \\
\text{free variables :} \quad x_{2}, x_{4}
\end{cases} \\\\
x_{n} = c_{1}x_{n1} + c_{2}x_{n2}
= c_{1}\begin{bmatrix} -2 \\ 1 \\ 0 \\ 0 \end{bmatrix} + c_{2}\begin{bmatrix} 2 \\ 0 \\ -2 \\ 1 \end{bmatrix} \quad
\begin{cases}
(x_{2}, x_{4}) = (1, 0) \quad\text{for}\quad x_{n1} \\
(x_{2}, x_{4}) = (0, 1) \quad\text{for}\quad x_{n2}
\end{cases}
\end{align*}
```

- $x_{complete}$

```math
\begin{align*}
x_{complete} = x_{particular} + x_{nullspace} {}
&= x_{p} + x_{n} \\\\
&= \begin{bmatrix} -2 \\ 0 \\ \frac{3}{2} \\ 0 \end{bmatrix} + c_{1}\begin{bmatrix} -2 \\ 1 \\ 0 \\ 0 \end{bmatrix} + c_{2}\begin{bmatrix} 2 \\ 0 \\ -2 \\ 1 \end{bmatrix}
\end{align*}
```
<br>

Plot all solutions $x_{complete}$ in $R_{4}$.<br>
Then "two-dimensional subspace (a plane) that doesn't go through the origin" comes out.

```math
\begin{align*}\begin{cases}
x_{n} \quad\text{: Two-dimensional subspace (a plane)} \\
x_{p} \quad\text{: Doesn't go through the origin}
\end{cases}\end{align*}
```

**Rank**
- $\Gamma$ : Rank of $(m \times n)$ matrix $A$.

- Num of pivot variables cannot be bigger than $n$ and $m$<br>
$(\Gamma <= m)$ and $(\Gamma <= n)$<br>

- Full column rank $(\Gamma = n < m)$<br>
In this case, there are no free variables.<br>
Null space $N(A) = 0$ → $x_{n} = 0$.<br>
$x_{complete} = x_{particular} + x_{nullspace} = x_{p}$<br>
Unique solution (only one) if it exists.<br>
(= This system has either $0$ or $1$ solution.)
```math
R = \begin{bmatrix} I \\ 0 \end{bmatrix}
```

- Full row rank $(\Gamma = m < n)$<br>
In this case, can solve $Ax = b$ for every $b$.<br>
Left with $(n - \Gamma) = (n - m)$ free variables.<br>
This system has $\infty$ solutions.
```math
R = \begin{bmatrix} I & F \end{bmatrix}
```

- Full rank $(\Gamma = m = n)$<br>
In this case, $A$ is invertible.<br>
$rref(A) = I$ (Reduced row echelon form of $A$ is $I$.)<br>
This system has only $1$ solution.

- $(\Gamma < m)$ and $(\Gamma < n)$<br>
This system has no solution or $\infty$ solutions.
```math
R = \begin{bmatrix} I & F \\ 0 & 0 \end{bmatrix}
```
