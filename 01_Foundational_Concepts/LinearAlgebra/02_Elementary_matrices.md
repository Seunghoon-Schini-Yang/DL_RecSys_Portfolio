### ¶ Elementary matrices ¶ (from Lecture_02)

**(a) Exchange rows $(R_{i} \leftrightarrow R_{j})$**<br>
We need to do row exchanges <b>when zero shows up in the pivot position</b>.

- Permutation matrix<br>
Permutation matrices $P$ are <b>orthonormal</b>. $(P^{-1} = P^{T})$<br>
$(n \times n)$ sized permutation matrix has $n!$ cases.
```math
(3 \times 3)\: P's \quad : \quad
\begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{bmatrix} \quad
\begin{bmatrix} 1 & 0 & 0 \\ 0 & 0 & 1 \\ 0 & 1 & 0 \end{bmatrix} \quad
\begin{bmatrix} 0 & 1 & 0 \\ 1 & 0 & 0 \\ 0 & 0 & 1 \end{bmatrix} \quad
\begin{bmatrix} 0 & 1 & 0 \\ 0 & 0 & 1 \\ 1 & 0 & 0 \end{bmatrix} \quad
\begin{bmatrix} 0 & 0 & 1 \\ 1 & 0 & 0 \\ 0 & 1 & 0 \end{bmatrix} \quad
\begin{bmatrix} 0 & 0 & 1 \\ 0 & 1 & 0 \\ 1 & 0 & 0 \end{bmatrix}
```
<br>

- Exchange rows (: Permutation matrix $P_{ij}$ swaps the rows $i$ and $j$.)<br>
```math
\begin{align}
\text{Example :}\quad P_{12} = \begin{bmatrix} 0 & 1 & 0 \\ 1 & 0 & 0 \\ 0 & 0 & 1 \end{bmatrix} \quad\text{(Swaps row 1 and 2)} \\\\
P_{12} \begin{bmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9 \end{bmatrix} = \begin{bmatrix} 0 & 1 & 0 \\ 1 & 0 & 0 \\ 0 & 0 & 1\end{bmatrix} \begin{bmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9 \end{bmatrix} = \begin{bmatrix} 4 & 5 & 6 \\ 1 & 2 & 3 \\ 7 & 8 & 9 \end{bmatrix}
\end{align}
```
- Exchange columns
```math
\begin{bmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9 \end{bmatrix} P_{12} = \begin{bmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9 \end{bmatrix} \begin{bmatrix} 0 & 1 & 0 \\ 1 & 0 & 0 \\ 0 & 0 & 1\end{bmatrix} = \begin{bmatrix} 2 & 1 & 3 \\ 5 & 4 & 6 \\ 8 & 7 & 9 \end{bmatrix}
```
<br>

**(b) Row scailing ($R_{i} \leftarrow cR_{j}$, $c \not= 0$)**<br>
- Diagonal elementary matrix $D_{i}(c)$ multiplies $c$ on row $i$.
```math
\begin{align}
\text{Example :}\quad D_{2}(5) = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 5 & 0 \\ 0 & 0 & 1 \end{bmatrix} \quad\text{(Scale row 2 by 5)} \\\\
D_{2}(5) \begin{bmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9 \end{bmatrix} = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 5 & 0 \\ 0 & 0 & 1 \end{bmatrix} \begin{bmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9 \end{bmatrix} = \begin{bmatrix} 1 & 2 & 3 \\ 20 & 25 & 30 \\ 7 & 8 & 9 \end{bmatrix}
\end{align}
```
- Multiply columns
```math
\begin{bmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9 \end{bmatrix} D_{2}(5) = \begin{bmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9 \end{bmatrix} \begin{bmatrix} 1 & 0 & 0 \\ 0 & 5 & 0 \\ 0 & 0 & 1 \end{bmatrix} = \begin{bmatrix} 1 & 10 & 3 \\ 4 & 25 & 6 \\ 7 & 40 & 9 \end{bmatrix}
```
<br>

**(c) Row subtraction with other row $(R_{i} \leftarrow R_{i} - cR_{j})$**<br>
- $E_{ij}(c) = I - c\vec{e}_{i}\vec{e}_{j}^{T}$
```math
\begin{align}
\text{Example :}\quad E_{31}(c) = I - c\vec{e}_{3}\vec{e}_{1}^{T} {} &= \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{bmatrix} - c \begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix} \begin{bmatrix} 1 & 0 & 0 \end{bmatrix} \\
&= \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{bmatrix} - \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ c & 0 & 1 \end{bmatrix} \\
&= \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ -c & 0 & 1 \end{bmatrix} \quad(\text{subtract}\: c * row_{1} \:\text{onto}\: row_{3})
\end{align}
```
```math
E_{31}(c) \begin{bmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9 \end{bmatrix} = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ -c & 0 & 1 \end{bmatrix} \begin{bmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9 \end{bmatrix} = \begin{bmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \\ 7-1c & 8-2c & 9-3c \end{bmatrix}
```
- Column subtraction
```math
\begin{bmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9 \end{bmatrix} E_{31}(c) = \begin{bmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9 \end{bmatrix} \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ -c & 0 & 1 \end{bmatrix} = \begin{bmatrix} 1-3c & 2 & 3 \\ 4-6c & 5 & 6 \\ 7-9c & 8 & 9 \end{bmatrix} \quad(\text{subtract}\: c * col_{3} \:\text{onto}\: col_{1})
```
<br>

**○ Inverse of Elementary matrices**
| Type | Original | Inverse |
| :-----: | :----: | :----: |
| (a) | $P_{ij}$ | $P_{ji} = P_{ij}^{T}$ |
| (b) | $D_{i}(c)$ | $D_{i}(\frac{1}{c})$ |
| (c) | $E_{ij}(c)$ | $E_{ij}(-c)$ |
