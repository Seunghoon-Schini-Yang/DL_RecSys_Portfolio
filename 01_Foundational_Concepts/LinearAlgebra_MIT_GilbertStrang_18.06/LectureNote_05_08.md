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
A = \begin{bmatrix} 1 & 2 & 2 & 2 \\ 2 & 4 & 6 & 8 \\ 3 & 6 & 8 & 10 \end{bmatrix} → \begin{bmatrix} 1 & 2 & 2 & 2 \\ 0 & 0 & 2 & 4 \\ 0 & 0 & 2 & 4 \end{bmatrix} → \begin{bmatrix} 1 & 2 & 2 & 2 \\ 0 & 0 & 2 & 4 \\ 0 & 0 & 0 & 0 \end{bmatrix} = U \quad\text{(Echelon form)}
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