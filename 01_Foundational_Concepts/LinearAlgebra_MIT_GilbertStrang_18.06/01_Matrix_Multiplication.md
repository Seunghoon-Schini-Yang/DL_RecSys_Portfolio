### ¶ Matrix Multiplication ¶ (from Lecture_03)

```math
\begin{align}
\text{Given}\quad \underset{(m\times n)}A\underset{(n\times p)}B = \underset{(m\times p)}C \\\\
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
& = \begin{bmatrix} 1 \begin{bmatrix} 1 \\ -2 \end{bmatrix} & 3 \begin{bmatrix} 1 \\ -2 \end{bmatrix} \end{bmatrix}
+ \begin{bmatrix} 3 \begin{bmatrix} 4 \\ 1 \end{bmatrix} & 4 \begin{bmatrix} 4 \\ 1 \end{bmatrix} \end{bmatrix}
+ \begin{bmatrix} -1 \begin{bmatrix} 2 \\ 5 \end{bmatrix} & 1 \begin{bmatrix} 2 \\ 5 \end{bmatrix} \end{bmatrix}
\end{align}
```

```math
\begin{align}
\quad\text{※ Each row (col) has same direction to other rows (cols) :} \\
\biggl(\quad
\begin{bmatrix} 1 * \begin{bmatrix} 1 & 3 \end{bmatrix} \\ -2 * \begin{bmatrix} 1 & 3 \end{bmatrix} \end{bmatrix}
= \begin{bmatrix} 1 * \begin{bmatrix} 1 \\ -2 \end{bmatrix} & 3 * \begin{bmatrix} 1 \\ -2 \end{bmatrix} \end{bmatrix}
\quad\biggr)
\end{align}
```

- Multiplication by Blocks
```math
\begin{align*}
\text{When}\quad\ AB
= \begin{bmatrix} A_1 & A_2 \\ A_3 & A_4 \end{bmatrix}\begin{bmatrix} B_1 & B_2 \\ B_3 & B_4 \end{bmatrix}
= \begin{bmatrix} C_1 & C_2 \\ C_3 & C_4 \end{bmatrix} = C \\\\
\text{then}\quad C_1 = A_1 B_1 + A_2 B_3 \\\\
(\text{ Each of}\quad A_i,\ B_i,\ C_i \quad\text{is matrix. })
\end{align*}
```
