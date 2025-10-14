# 📚 Lecture 1: The geometry of linear equations

```math
\mathbf{A} = \begin{bmatrix} 2 & -1 & 0 \\ -1 & 2 & -1 \\ 0 & -3 & 4\end{bmatrix}, \quad \mathbf{b} = \begin{bmatrix} 1 \\ 1 \\ -3 \end{bmatrix}
```

**○ Row Picture**
* Three planes meet in a point, and that's the solution.\
(Unless parallels or something exist.)
```math
\begin{eqnarray}
2\mathbf{x} - \mathbf{y} = 1 \\
-\mathbf{x} + 2\mathbf{y} -\mathbf{z} = 1 \\
-3\mathbf{y} + 4\mathbf{z} = -3
\end{eqnarray}
```

**○ Column Picture**
* Linear combination of three vectors.

```math
\mathbf{x} \begin{bmatrix} 2 \\ -1 \\ 0\end{bmatrix} + \mathbf{y} \begin{bmatrix} -1 \\ 2 \\ -3\end{bmatrix} + \mathbf{z} \begin{bmatrix} 0 \\ -1 \\ 4\end{bmatrix} = \begin{bmatrix} 1 \\ 1 \\ -3\end{bmatrix}
```

### 🧩 Key Points
💡 Can I solve $\mathbf{A}\mathbf{x} = \mathbf{b}$ for every $\mathbf{b}$ ?\
💡 Do the linear combinations of the columns fill 3-D space?


<br><br><hr>


# 📚 Lecture 2: Elimination with matrices

```math
\begin{align*}
\mathbf{E_{21}}
= \begin{bmatrix} 1 & 0 & 0 \\ -3 & 1 & 0 \\ 0 & 0 & 1\end{bmatrix}
\quad\text{(Substract 3*row1 from row2)}
\end{align*}
```

```math
\begin{align*}
\mathbf{E_{32}}
= \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & -2 & 1\end{bmatrix}
\quad\text{(Substract 2*row2 from row3)}
\end{align*}
```

```math
\begin{align*}
\mathbf{U} = \mathbf{E_{32}}\mathbf{E_{21}}\mathbf{A}{}
& = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & -2 & 1\end{bmatrix}\begin{bmatrix} 1 & 0 & 0 \\ -3 & 1 & 0 \\ 0 & 0 & 1\end{bmatrix}\begin{bmatrix} 1 & 2 & 1 \\ 3 & 8 & 1 \\ 0 & 4 & 1\end{bmatrix}
\\\\
& = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & -2 & 1\end{bmatrix}\begin{bmatrix} 1 & 2 & 1 \\ 0 & 2 & -2 \\ 0 & 4 & 1\end{bmatrix}
\\\\
& = \begin{bmatrix} 1 & 2 & 1 \\ 0 & 2 & -2 \\ 0 & 0 & 5\end{bmatrix}
\end{align*}
```

<br>**○ Inverses**
```math
\mathbf{E_{21}^{-1}}\mathbf{E_{21}}
= \begin{bmatrix} 1 & 0 & 0 \\ 3 & 1 & 0 \\ 0 & 0 & 1\end{bmatrix}
\begin{bmatrix} 1 & 0 & 0 \\ -3 & 1 & 0 \\ 0 & 0 & 1\end{bmatrix}
= \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1\end{bmatrix}
= \mathbf{I}
```

<br>**○ Permutations**
- Exchange rows
```math
\begin{align}
\begin{bmatrix} 0 & 1 \\ 1 & 0\end{bmatrix}
\begin{bmatrix} a & b \\ c & d\end{bmatrix}
= \begin{bmatrix} c & d \\ a & b\end{bmatrix}
\end{align}
```
- Exchange columns
```math
\begin{bmatrix} a & b \\ c & d\end{bmatrix}
\begin{bmatrix} 0 & 1 \\ 1 & 0\end{bmatrix}
= \begin{bmatrix} b & a \\ d & c\end{bmatrix}
```

<br><br><hr>

# 📚 Lecture 3: Multiplication and Inverse matrices
<br>**○ Matrix Multiplication**

```math
\begin{align*}
\mathbf{A}\mathbf{B} = \mathbf{C}\quad
\biggl(\quad\text{where}\quad
A = \begin{bmatrix}
a_{11} & a_{12} & \cdots & a_{1n} \\
a_{21} & a_{22} & \cdots & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{m1} & a_{m2} & \cdots & a_{mn}
\end{bmatrix}
= \begin{bmatrix}\vec{a}_{col_1} & \vec{a}_{col_2} & \cdots & \vec{a}_{col_n}\end{bmatrix}
,\quad
B = \begin{bmatrix}
b_{11} & b_{12} & \cdots & b_{1p} \\
b_{21} & b_{22} & \cdots & b_{2p} \\
\vdots & \vdots & \ddots & \vdots \\
b_{n1} & b_{n2} & \cdots & b_{np}
\end{bmatrix}
= \begin{bmatrix}\vec{b}_{row_1} \\ \vec{b}_{row_2} \\ \vdots \\ \vec{b}_{row_n}\end{bmatrix}
\\\text{and}\quad
C = \begin{bmatrix}
c_{11} & c_{12} & \cdots & c_{1p} \\
c_{21} & c_{22} & \cdots & c_{2p} \\
\vdots & \vdots & \ddots & \vdots \\
c_{m1} & c_{m2} & \cdots & c_{mp}
\end{bmatrix}
= \begin{bmatrix}\vec{c}_{col_1} & \vec{c}_{col_2} & \cdots & \vec{c}_{col_p}\end{bmatrix}
= \begin{bmatrix}\vec{c}_{row_1} \\ \vec{c}_{row_2} \\ \vdots \\ \vec{c}_{row_m}\end{bmatrix}
\quad\biggr)
\end{align*}
```

- each element of $\mathbf{C}$
```math
c_{ij} = \vec{a}_{row_i}\cdot\vec{b}_{col_j}\text{ (dot product)}
= a_{i1} b_{1j} + a_{i2} b_{2j} + \cdots + a_{in} b_{nj}
= \sum_{k=1}^n a_{ik} b_{kj}
```

- rows of $\mathbf{C}$ are combinations of rows of $\mathbf{B}$
```math
\vec{c}_{row_k} = a_{k1} \vec{b}_{row_1} + a_{k2} \vec{b}_{row_2} + \cdots + a_{kn}\vec{b}_{row_n}
= \sum_{i=1}^n a_{ki} \vec{b}_{row_i}
```

- cols of $\mathbf{C}$ are combinations of cols of $\mathbf{A}$
```math
\vec{c}_{col_k} = b_{1k} \vec{a}_{col_1} + b_{2k} \vec{a}_{col_2} + \cdots + b_{nk}\vec{a}_{col_n}
= \sum_{i=1}^n b_{ik} \vec{a}_{col_i}
```

- 4th way (cols of $\mathbf{A}$ * rows of $\mathbf{B}$)
```math
C = \sum_{k=1}^n \vec{a}_{col_k} \cdot \vec{b}_{row_k}
```

```math
\begin{align*}
\text{Example)}\quad
\begin{bmatrix} 1 & 4 & 2 \\ -2 & 1 & 5 \end{bmatrix}
\begin{bmatrix} 1 & 3 \\ 3 & 4 \\ -1 & 1 \end{bmatrix}{}
& = \begin{bmatrix} 1 \\ -2 \end{bmatrix}\begin{bmatrix} 1 & 3 \end{bmatrix}
+ \begin{bmatrix} 4 \\ 1 \end{bmatrix}\begin{bmatrix} 3 & 4 \end{bmatrix}
+ \begin{bmatrix} 2 \\ 5 \end{bmatrix}\begin{bmatrix} -1 & 1 \end{bmatrix} \\\\
& = \begin{bmatrix} 1 * \begin{bmatrix} 1 & 3 \end{bmatrix} \\ -2 * \begin{bmatrix} 1 & 3 \end{bmatrix} \end{bmatrix}
+ \begin{bmatrix} 4 * \begin{bmatrix} 3 & 4 \end{bmatrix} \\ 1 * \begin{bmatrix} 3 & 4 \end{bmatrix} \end{bmatrix}
+ \begin{bmatrix} 2 * \begin{bmatrix} -1 & 1 \end{bmatrix} \\ 5 * \begin{bmatrix} -1 & 1 \end{bmatrix} \end{bmatrix} \\\\
& = \begin{bmatrix} 1 * \begin{bmatrix} 1 \\ -2 \end{bmatrix} & 3 * \begin{bmatrix} 1 \\ -2 \end{bmatrix} \end{bmatrix}
+ \begin{bmatrix} 3 * \begin{bmatrix} 4 \\ 1 \end{bmatrix} & 4 * \begin{bmatrix} 4 \\ 1 \end{bmatrix} \end{bmatrix}
+ \begin{bmatrix} -1 * \begin{bmatrix} 2 \\ 5 \end{bmatrix} & 1 * \begin{bmatrix} 2 \\ 5 \end{bmatrix} \end{bmatrix}
\end{align*}
```

```math
\begin{align*}\biggl(\quad
\begin{bmatrix} 1 * \begin{bmatrix} 1 & 3 \end{bmatrix} \\ -2 * \begin{bmatrix} 1 & 3 \end{bmatrix} \end{bmatrix}
= \begin{bmatrix} 1 * \begin{bmatrix} 1 \\ -2 \end{bmatrix} & 3 * \begin{bmatrix} 1 \\ -2 \end{bmatrix} \end{bmatrix}
\quad\text{: Each row (col) has same direction to other rows (cols)} \quad\biggr) \\
\\
\end{align*}
```

- Multiplication by Blocks
```math
\begin{align*}
\text{When}\quad\ AB
= \begin{bmatrix} A_1 & A_2 \\ A_3 & A_4 \end{bmatrix}\begin{bmatrix} B_1 & B_2 \\ B_3 & B_4 \end{bmatrix}
= \begin{bmatrix} C_1 & C_2 \\ C_3 & C_4 \end{bmatrix} = C \\\\
\text{then}\quad C_1 = A_1 B_1 + A_2 B_3 \\\\
\text{( Each of}\quad A_i,\ B_i,\ C_i \quad\text{is matrix. )}
\end{align*}
```

<br>**○ Inverse matrices**<br>
<br>For square matrix $A$,
<br>if $\mathbf{A^{-1}}$ exists, then $\mathbf{A}$ is <b>invertible</b> and <b>non-singular</b>.

```math
A^{-1}A = I = AA^{-1}
```

<br>In below case, $\mathbf{x}$ is not $\mathbf{0}$.
<br>But at the same time, $\mathbf{x}$ is $\mathbf{0}$.
<br>If some combinations of colums of $\mathbf{A}$ give $\mathbf{0}$, then $\mathbf{A}$ is <b>not invertible</b> and <b>singular</b>.

```math
\begin{align}
\text{When}\quad A = \begin{bmatrix} 1 & 3 \\ 2 & 6 \end{bmatrix} \quad
\text{and}\quad x = \begin{bmatrix} 3 \\ -1 \end{bmatrix} \quad\text{,} \quad\text{then}\quad Ax = 0 \\\\
\text{if}\quad A^{-1} \quad\text{exists,}\quad\text{then}\quad A^{-1}Ax
= A^{-1}0 \quad→\quad x = \begin{bmatrix} 0 \\ 0 \end{bmatrix}
\end{align}
```

<br>**○ Gauss-Jordan Elimination**<br>

```math
\begin{align}
\text{Set}\quad \begin{bmatrix} 1 & 3 \\ 2 & 7 \end{bmatrix}
\begin{bmatrix} c & d \\ a & b \end{bmatrix}
= \begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix}
\quad (\quad AA^{-1} = I \quad)
\end{align}
```

- Do elimination
```math
\begin{align}
\begin{bmatrix} A & I \end{bmatrix} \quad→\quad \begin{bmatrix} 1 & 3 \\ 2 & 7 \end{bmatrix}\begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix} \\ E_{1}\begin{bmatrix} A & I \end{bmatrix}
= \begin{bmatrix} E_{1}A & E_{1}I \end{bmatrix}
\quad→\quad
\begin{bmatrix} 1 & 3 \\ 0 & 1 \end{bmatrix}\begin{bmatrix} 1 & 0 \\ -2 & 1 \end{bmatrix} \\
E_{2}\begin{bmatrix} E_{1}A & E_{1}I \end{bmatrix}
= \begin{bmatrix} E_{2}E_{1}A & E_{2}E_{1}I \end{bmatrix}
\quad→\quad \begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix}
\begin{bmatrix} 7 & -3 \\ -2 & 1 \end{bmatrix}
\end{align}
```

- $\mathbf{E = A^{-1}}$
```math
\begin{align}
\begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix}\begin{bmatrix} 7 & -3 \\ -2 & 1 \end{bmatrix}
= \begin{bmatrix} EA & EI \end{bmatrix} = \begin{bmatrix} I & E \end{bmatrix}\quad
(\quad\text{where}\quad E = E_{2}E_{1} \quad) \\
\text{So,}\quad EA = I \quad↔\quad E = A^{-1}
\end{align}
```

<br><br><br>

<!-- 
# 📚 Lecture 4: Factorization into A = LU
A = LU
A = LDU -->
