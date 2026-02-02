# 📚 Lecture 3: Multiplication and Inverse matrices
<br>**○ Matrix Multiplication**

```math
\begin{align}
\underset{(m\times n)}A\underset{(n\times p)}B = \underset{(m\times p)}C \\\\
\Biggl(\quad
A = \begin{bmatrix}
a_{11} & a_{12} & \cdots & a_{1n} \\
a_{21} & a_{22} & \cdots & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{m1} & a_{m2} & \cdots & a_{mn}
\end{bmatrix} ,\quad
B = \begin{bmatrix}
b_{11} & b_{12} & \cdots & b_{1p} \\
b_{21} & b_{22} & \cdots & b_{2p} \\
\vdots & \vdots & \ddots & \vdots \\
b_{n1} & b_{n2} & \cdots & b_{np}
\end{bmatrix} ,\quad
C = \begin{bmatrix}
c_{11} & c_{12} & \cdots & c_{1p} \\
c_{21} & c_{22} & \cdots & c_{2p} \\
\vdots & \vdots & \ddots & \vdots \\
c_{m1} & c_{m2} & \cdots & c_{mp}
\end{bmatrix}
\quad\Biggr)
\end{align}
```

- Each element of $\mathbf{C}$
```math
c_{ij} = \vec{a}_{row_i}\cdot\vec{b}_{col_j}
= a_{i1} b_{1j} + a_{i2} b_{2j} + \cdots + a_{in} b_{nj}
= \sum_{k=1}^n a_{ik} b_{kj}
```

- Rows of $\mathbf{C}$ are combinations of rows of $B$
```math
\vec{c}_{row_k} = a_{k1} \vec{b}_{row_1} + a_{k2} \vec{b}_{row_2} + \cdots + a_{kn}\vec{b}_{row_n}
= \sum_{i=1}^n a_{ki} \vec{b}_{row_i}
```

- Cols of $C$ are combinations of cols of $A$
```math
\vec{c}_{col_k} = b_{1k} \vec{a}_{col_1} + b_{2k} \vec{a}_{col_2} + \cdots + b_{nk}\vec{a}_{col_n}
= \sum_{i=1}^n b_{ik} \vec{a}_{col_i}
```

- 4th way (cols of $A$ * rows of $B$)
```math
C = \sum_{k=1}^n \vec{a}_{col_k} \cdot \vec{b}_{row_k}
```

```math
\begin{align}
\text{Example :}\quad
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
\end{align}
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
- For square matrix $A$,
<br>if $A^{-1}$ exists, then $A$ is <b>invertible</b> and <b>non-singular</b>.

```math
A^{-1}A = I = AA^{-1}
```

- In below case, $\vec{x} \not= \vec{0}$.<br>
But at the same time, $\vec{x} = \vec{0}$.<br>
If some combinations of colums of $A$ give $\vec{0}$, then $A$ is <b>singular</b> and <b>not invertible</b>.

```math
\begin{align}
\text{When}\quad A = \begin{bmatrix} 1 & 3 \\ 2 & 6 \end{bmatrix} \quad
\text{and}\quad \vec{x} = \begin{bmatrix} 3 \\ -1 \end{bmatrix} \quad\text{, then}\quad A\vec{x} = \vec{0} \\\\
\text{if}\quad A^{-1} \quad\text{exists,}\quad\text{then}\quad A^{-1}A\vec{x} = A^{-1}0 \quad→\quad \vec{x} = \begin{bmatrix} 0 \\ 0 \end{bmatrix}
\end{align}
```

<br>**○ Gauss-Jordan Elimination**<br>

- Set $\quad AA^{-1} = I$
```math
\begin{align}
\begin{bmatrix} 1 & 3 \\ 2 & 7 \end{bmatrix}
\begin{bmatrix} c & d \\ a & b \end{bmatrix}
= \begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix}
\quad (\quad AA^{-1} = I \quad)
\end{align}
```

- Do elimination with $\quad E_{i}$
```math
\begin{align}
\begin{bmatrix} A & I \end{bmatrix} \quad→\quad \begin{bmatrix} 1 & 3 \\ 2 & 7 \end{bmatrix}\begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix} \\
E_{1}\begin{bmatrix} A & I \end{bmatrix} = \begin{bmatrix} E_{1}A & E_{1}I \end{bmatrix} \quad→\quad
\begin{bmatrix} 1 & 3 \\ 0 & 1 \end{bmatrix}\begin{bmatrix} 1 & 0 \\ -2 & 1 \end{bmatrix} \quad\text{(Elimination)} \\
E_{2}\begin{bmatrix} E_{1}A & E_{1}I \end{bmatrix}
= \begin{bmatrix} E_{2}E_{1}A & E_{2}E_{1}I \end{bmatrix}
\quad→\quad \begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix}
\begin{bmatrix} 7 & -3 \\ -2 & 1 \end{bmatrix} \quad\text{(Back substitution)}
\end{align}
```

- So, $\quad E = A^{-1}$
```math
\begin{align}
\begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix}\begin{bmatrix} 7 & -3 \\ -2 & 1 \end{bmatrix}
= \begin{bmatrix} EA & EI \end{bmatrix} = \begin{bmatrix} I & E \end{bmatrix}\quad
(\quad\text{where}\quad E = E_{2}E_{1} \quad) \\
\text{So,}\quad EA = I \quad↔\quad E = A^{-1}
\end{align}
```
