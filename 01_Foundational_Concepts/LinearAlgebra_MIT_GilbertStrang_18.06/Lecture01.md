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

**○ Inverses**
```math
\mathbf{E_{21}^{-1}}\mathbf{E_{21}}
= \begin{bmatrix} 1 & 0 & 0 \\ 3 & 1 & 0 \\ 0 & 0 & 1\end{bmatrix}
\begin{bmatrix} 1 & 0 & 0 \\ -3 & 1 & 0 \\ 0 & 0 & 1\end{bmatrix}
= \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1\end{bmatrix}
= \mathbf{I}
```

**○ Exchange rows**
```math
\begin{align}
\begin{bmatrix} 0 & 1 \\ 1 & 0\end{bmatrix}
\begin{bmatrix} a & b \\ c & d\end{bmatrix}
= \begin{bmatrix} c & d \\ a & b\end{bmatrix}
\end{align}
```

**○ Exchange columns**
```math
\begin{bmatrix} a & b \\ c & d\end{bmatrix}
\begin{bmatrix} 0 & 1 \\ 1 & 0\end{bmatrix}
= \begin{bmatrix} b & a \\ d & c\end{bmatrix}
```
