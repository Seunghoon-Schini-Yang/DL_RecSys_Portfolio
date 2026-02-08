### ¶ The geometry of linear equations ¶ (from Lecture_01)

```math
A = \begin{bmatrix} 2 & -1 & 0 \\ -1 & 2 & -1 \\ 0 & -3 & 4\end{bmatrix},
\quad \vec{b} = \begin{bmatrix} 1 \\ 1 \\ -3 \end{bmatrix}
```

**○ Row Picture**
* Three planes meet in a point, and that's the solution.\
(Unless parallels or something exist.)
```math
\begin{cases}
2x - y = 1 \\
-x + 2y -z = 1 \\
-3y + 4z = -3
\end{cases}
```

**○ Column Picture**
* Linear combination of three vectors.

```math
x \begin{bmatrix} 2 \\ -1 \\ 0 \end{bmatrix}
+ y \begin{bmatrix} -1 \\ 2 \\ -3 \end{bmatrix}
+ z \begin{bmatrix} 0 \\ -1 \\ 4 \end{bmatrix}
= \begin{bmatrix} 1 \\ 1 \\ -3\end{bmatrix}
```
<br>

**○ Inverse matrix**<br>
- For square matrix $A$,<br>$A^{-1}$ is <b>inverse</b> of $A$ only if $A^{-1}A = AA^{-1} = I$.
<br>if $A^{-1}$ exists, then $A$ is <b>invertible</b> and <b>non-singular</b>.
```math

```

- If some linear combinations of colums of $A$ give $\vec{0}$,<br>
then $A$ is <b>singular</b> and <b>not invertible</b>.<br>
In below case, $\vec{x} \not= \vec{0}$ and $\vec{x} = \vec{0}$ at the same time.<br>

```math
\begin{align}
\text{When}\quad A = \begin{bmatrix} 1 & 3 \\ 2 & 6 \end{bmatrix} \quad
\text{and}\quad \vec{x} = \begin{bmatrix} 3 \\ -1 \end{bmatrix} \quad\text{, then}\quad A\vec{x} = 3 \begin{bmatrix} 1 \\ 2 \end{bmatrix} + (-1) \begin{bmatrix} 3 \\ 6 \end{bmatrix} = \vec{0} \\\\
\text{if}\quad A^{-1} \quad\text{exists,}\quad\text{then}\quad A^{-1}A\vec{x} = A^{-1}\vec{0} \quad→\quad \vec{x} = \begin{bmatrix} 0 \\ 0 \end{bmatrix}
\end{align}
```
<br>

### 🧩 Key Points
💡 Can I solve $A\vec{x} = \vec{b}$ for every $\vec{b}$ ?<br>
💡 Do the linear combinations of the columns fill 3-D space?
