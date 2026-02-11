### ¶ Column Space ¶
- All linear combinations from columns of $A$ form a subspace called <b>column space</b>.

```math
A = \begin{bmatrix} 1 & 3 \\ 2 & 3 \\ 4 & 1 \end{bmatrix}
\quad\text{→} \quad C(A) \quad(\text{Column space of } A)
```
<br>

- Take all their linear combinations, we can fill out the whole plane.

```math
C(A) = R^{2} \quad : \quad
c_{1}\begin{bmatrix} 1 \\ 2 \\ 4 \end{bmatrix} + c_{2}\begin{bmatrix} 3 \\ 3 \\ 1 \end{bmatrix}
```
```math
\begin{align}
A = \begin{bmatrix} 1 & 1 & 2 \\ 2 & 1 & 3 \\ 3 & 1 & 4 \\ 4 & 1 & 5 \end{bmatrix} \\
C(A) = \begin{cases}
\text{Column Space of  } A \\
\text{All linear combinations of columns of  } A
\end{cases}
\end{align}
```
<br>

- Does $C(A)$ fill the full 4-dimensional space $R^{4}$ ?<br>
- Does $A\vec{x} = \vec{b}$ have a solution for every $\vec{b} \in R^{4}$ ?<br>
- Which $\vec{b}$'s allow this system to be solved?<br>
→ Can solve $A\vec{x} = \vec{b}$ exactly when $\vec{b} \in C(A)$.<br>

```math
A\vec{x} = \begin{bmatrix} 1 & 1 & 2 \\ 2 & 1 & 3 \\ 3 & 1 & 4 \\ 4 & 1 & 5 \end{bmatrix}\begin{bmatrix} x_{1} \\ x_{2} \\ x_{3} \end{bmatrix} = \begin{bmatrix} b_{1} \\ b_{2} \\ b_{3} \\ b_{4} \end{bmatrix} = \vec{b}
```
<br>

### ¶ Null Space ¶

- Null Space is a vector space.
```math
\begin{align}
A\vec{x} = \begin{bmatrix} 1 & 1 & 2 \\ 2 & 1 & 3 \\ 3 & 1 & 4 \\ 4 & 1 & 5 \end{bmatrix}\begin{bmatrix} x_{1} \\ x_{2} \\ x_{3} \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \\ 0 \\ 0 \end{bmatrix} \\
\text{In this system,}\quad \vec{x} \quad\text{can be}\quad \begin{bmatrix} 0 \\ 0 \\ 0 \end{bmatrix} \quad\text{or}\quad \begin{bmatrix} 1 \\ 1 \\ -1 \end{bmatrix} \quad\text{or else.}
\end{align}
```

Solutions to $A\vec{x} = \vec{0}$ always give a subspace. (Contains zero vector at least.)<br>
$N(A)$ (Null space of $A$) always contains zero vector.
```math
\begin{align}
\text{If}\: A\vec{v} = \vec{0} \quad\text{and}\quad A\vec{w} = \vec{0}, \\
\text{then} \quad
\begin{cases}
A(\vec{v}+\vec{w}) = \vec{0} \quad\text{(Addition)} \\
A(c\vec{v}) = \vec{0} \quad\text{(Multiplication)}
\end{cases} \\
\therefore\text{ null space is a vector space.}
\end{align}
```
<br>

- When $\vec{b} \not= \vec{0}$, the set of solutions is not a vector space.
```math
A\vec{x} = \begin{bmatrix} 1 & 1 & 2 \\ 2 & 1 & 3 \\ 3 & 1 & 4 \\ 4 & 1 & 5 \end{bmatrix}\begin{bmatrix} x_{1} \\ x_{2} \\ x_{3} \end{bmatrix} = \begin{bmatrix} 1 \\ 2 \\ 3 \\ 4 \end{bmatrix}
```

In this case, the set of solutions $x$ does not have zero vector. (Zero vector is not a solution.)<br>
<b>Vector spaces have to go though the origin.</b><br>
That's why the solutions for this system can't be a vector space.
