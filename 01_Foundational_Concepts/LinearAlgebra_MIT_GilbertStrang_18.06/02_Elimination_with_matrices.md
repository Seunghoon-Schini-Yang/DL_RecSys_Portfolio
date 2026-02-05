### ¶ Elimination with matrices ¶ (from Lecture_02)

**○ Add (or subtract) rows from other rows**
```math
\begin{align}
\mathbf{E_{21}}
= \begin{bmatrix} 1 & 0 & 0 \\ -3 & 1 & 0 \\ 0 & 0 & 1\end{bmatrix}
\quad(\text{Substract}\: 3*row_{1} \:\text{from}\: row_{2})
\end{align}
```

```math
\begin{align}
E_{32} = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & -2 & 1\end{bmatrix}
\quad(\text{Substract}\: 2*row_{2} \:\text{from}\: row_{3})
\end{align}
```
<br>

- Transform $A$ into <b>upper triangular matrix</b> $U$
```math
\begin{align*}
U = E_{32}E_{21}A{}
& = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & -2 & 1\end{bmatrix}\begin{bmatrix} 1 & 0 & 0 \\ -3 & 1 & 0 \\ 0 & 0 & 1\end{bmatrix}\begin{bmatrix} 1 & 2 & 1 \\ 3 & 8 & 1 \\ 0 & 4 & 1\end{bmatrix}
\\\\
& = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & -2 & 1\end{bmatrix}\begin{bmatrix} 1 & 2 & 1 \\ 0 & 2 & -2 \\ 0 & 4 & 1\end{bmatrix}
\\\\
& = \begin{bmatrix} 1 & 2 & 1 \\ 0 & 2 & -2 \\ 0 & 0 & 5\end{bmatrix}
\end{align*}
```
<br>

**○ Inverses**
```math
E_{21}^{-1}E_{21}
= \begin{bmatrix} 1 & 0 & 0 \\ 3 & 1 & 0 \\ 0 & 0 & 1\end{bmatrix}
\begin{bmatrix} 1 & 0 & 0 \\ -3 & 1 & 0 \\ 0 & 0 & 1\end{bmatrix}
= \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1\end{bmatrix} = I
```
<br>

**○ Permutations**<br>
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
