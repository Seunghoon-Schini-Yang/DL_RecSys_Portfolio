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


<br><br><br>


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
\\
& = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & -2 & 1\end{bmatrix}\begin{bmatrix} 1 & 2 & 1 \\ 0 & 2 & -2 \\ 0 & 4 & 1\end{bmatrix}
\\
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


<br><br><br>

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
\mathbf{c_{ij}} = \vec{a}_{row_i}\cdot\vec{b}_{col_j}\text{ (dot product)}
= \mathbf{a_{i1}}\mathbf{b_{1j}} + \mathbf{a_{i2}}\mathbf{b_{2j}} + \cdots + \mathbf{a_{in}}\mathbf{b_{nj}}
= \sum_{k=1}^n \mathbf{a_{ik}}\mathbf{b_{kj}}
```

- rows of $\mathbf{C}$ are combinations of rows of $\mathbf{B}$
```math
\mathbf{\vec{c}_{row_k}} = \mathbf{a_{k1}}\mathbf{\vec{b}_{row_1}} + \mathbf{a_{k2}}\mathbf{\vec{b}_{row_2}} + \cdots + \mathbf{a_{kn}}\mathbf{\vec{b}_{row_n}}
= \sum_{i=1}^n \mathbf{a_{ki}}\mathbf{\vec{b}_{row_i}}
```

- cols of $\mathbf{C}$ are combinations of cols of $\mathbf{A}$
```math
\mathbf{\vec{c}_{col_k}} = \mathbf{b_{1k}}\mathbf{\vec{a}_{col_1}} + \mathbf{b_{2k}}\mathbf{\vec{a}_{col_2}} + \cdots + \mathbf{b_{nk}}\mathbf{\vec{a}_{col_n}}
= \sum_{i=1}^n \mathbf{b_{ik}}\mathbf{\vec{a}_{col_i}}
```

- 4th way (cols of $\mathbf{A}$ * rows of $\mathbf{B}$)
```math
\mathbf{C} = \sum_{k=1}^n \vec{a}_{col_k} \cdot \vec{b}_{row_k}
```

```math
\begin{align*}
\text{Example)}\quad
\begin{bmatrix} 1 & 4 & 2 \\ -2 & 1 & 5 \end{bmatrix}
\begin{bmatrix} 1 & 3 \\ 3 & 4 \\ -1 & 1 \end{bmatrix}{}
& = \begin{bmatrix} 1 \\ -2 \end{bmatrix}\begin{bmatrix} 1 & 3 \end{bmatrix}
+ \begin{bmatrix} 4 \\ 1 \end{bmatrix}\begin{bmatrix} 3 & 4 \end{bmatrix}
+ \begin{bmatrix} 2 \\ 5 \end{bmatrix}\begin{bmatrix} -1 & 1 \end{bmatrix} \\
& = \begin{bmatrix} 1 * \begin{bmatrix} 1 & 3 \end{bmatrix} \\ -2 * \begin{bmatrix} 1 & 3 \end{bmatrix} \end{bmatrix}
+ \begin{bmatrix} 4 * \begin{bmatrix} 3 & 4 \end{bmatrix} \\ 1 * \begin{bmatrix} 3 & 4 \end{bmatrix} \end{bmatrix}
+ \begin{bmatrix} 2 * \begin{bmatrix} -1 & 1 \end{bmatrix} \\ 5 * \begin{bmatrix} -1 & 1 \end{bmatrix} \end{bmatrix}
\end{align*}
```

```math
\begin{align*}\biggl(\quad
\begin{bmatrix} 1 * \begin{bmatrix} 1 & 3 \end{bmatrix} \\ -2 * \begin{bmatrix} 1 & 3 \end{bmatrix} \end{bmatrix}
\quad\text{: each row (col) has same direction to other rows (cols)}
\quad\biggr)\end{align*}
```

<!-- matrix divided by blocks
[A1 A2 [B1 B2     [C1 C2
 A3 A4] B3 B4] =   C3 C4]
C1 = A1*B1 + A2*B3

For square matrix A, if A^-1 exists
A^-1 * A = I = A * A^-1
then A is invertible and non-singular

A = [1 2 \\ 3 6]
Ax = 0 >>> x = [3 -1]
A^-1*A*x = A^-1*0
x = 0

Gauss-Jordan Elimination
[1 3 // 2 7][a b // c d] = [1 0 // 0 1]
[1 3 // 2 7][1 0 // 0 1]
[1 3 // 0 1][1 0 // -2 1]
[1 0 // 0 1][7 -3 // -2 1]

<br><br><br>

# 📚 Lecture 4: Factorization into A = LU
A = LU
A = LDU -->
