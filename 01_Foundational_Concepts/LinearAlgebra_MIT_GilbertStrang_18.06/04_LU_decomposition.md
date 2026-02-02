# 📚 Lecture 4: Factorization into A = LU

<br>**○ LU & LDU Decomposition**

- Example

```math
\begin{align}
& \begin{bmatrix} 1 & 0 \\ -4 & 1 \end{bmatrix}
\begin{bmatrix} 2 & 1 \\ 8 & 7 \end{bmatrix}
= \begin{bmatrix} 2 & 1 \\ 0 & 3 \end{bmatrix}
\quad ( \quad E_{21}A = U \quad ) \\
& \begin{bmatrix} 2 & 1 \\ 8 & 7 \end{bmatrix}
= \begin{bmatrix} 1 & 0 \\ 4 & 1 \end{bmatrix}
\begin{bmatrix} 2 & 1 \\ 0 & 3 \end{bmatrix}
\quad ( \quad A = LU \text{ ,} \quad\text{where}\quad L = E_{21}^{-1} \quad ) \\
& = \begin{bmatrix} 1 & 0 \\ 4 & 1 \end{bmatrix}
\begin{bmatrix} 2 & 0 \\ 0 & 3 \end{bmatrix}
\begin{bmatrix} 1 & \frac{1}{2} \\ 0 & 1 \end{bmatrix}
\quad\text{(}\quad LDU \quad\text{:}\quad \text{Lower Triangular, Diagonal, Upper Triangular Matrix} \quad\text{)}
\end{align}
```
<br>

- if no row exchanges, multipliers go directly into L.
<br>$L$ comes out with much simpler form,
<br>while $E$ gets complicated.

```math
\begin{align}
E = E_{6}E_{5}E_{4}E_{3}E_{2}E_{1} \\\\
\biggl(\quad
E_{1} = \begin{bmatrix} 1 & 0 & 0 & 0 \\ e_{1} & 1 & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & 1 \end{bmatrix} , \quad
E_{2} = \begin{bmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ e_{2} & 0 & 1 & 0 \\ 0 & 0 & 0 & 1 \end{bmatrix} , \quad
E_{3} = \begin{bmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 1 & 0 & 1 & 0 \\ e_{3} & 0 & 0 & 1 \end{bmatrix} \\
E_{4} = \begin{bmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & e_{4} & 1 & 0 \\ 0 & 0 & 0 & 1 \end{bmatrix} , \quad
E_{5} = \begin{bmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 0 & e_{5} & 0 & 1 \end{bmatrix} , \quad
E_{6} = \begin{bmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & e_{6} & 1 \end{bmatrix} \quad\biggr) \\\\
L = E^{-1} = E_{1}^{-1}E_{2}^{-1}E_{3}^{-1}E_{4}^{-1}E_{5}^{-1}E_{6}^{-1}
= \begin{bmatrix} 1 & 0 & 0 & 0 \\ -e_{1} & 1 & 0 & 0 \\ -e_{2} & -e_{4} & 1 & 0 \\ -e_{3} & -e_{5} & -e_{6} & 1 \end{bmatrix}
\end{align}
```
<br>

- How may operations on (n x n) matrix?
<br>Time complexity : $\frac{1}{3}n^{3} \approx n^{2} + (n-1)^{2} + \cdots + 1^{2}$


<br>**○ Transposes and Permutations**
<br>We need to do row exchanges when zero shows up in the pivot position.<br>
- Permutations ($3$ x $3$) : $3! = 6$<br>
- Permutations ($n$ x $n$) : $n!$

```math
\begin{align}
P^{-1} = P^{T} \\\\
P's \quad : \quad
\begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{bmatrix} \quad
\begin{bmatrix} 1 & 0 & 0 \\ 0 & 0 & 1 \\ 0 & 1 & 0 \end{bmatrix} \quad
\begin{bmatrix} 0 & 1 & 0 \\ 1 & 0 & 0 \\ 0 & 0 & 1 \end{bmatrix} \quad
\begin{bmatrix} 0 & 1 & 0 \\ 0 & 0 & 1 \\ 1 & 0 & 0 \end{bmatrix} \quad
\begin{bmatrix} 0 & 0 & 1 \\ 1 & 0 & 0 \\ 0 & 1 & 0 \end{bmatrix} \quad
\begin{bmatrix} 0 & 0 & 1 \\ 0 & 1 & 0 \\ 1 & 0 & 0 \end{bmatrix}
\end{align}
```

<br>**○ PLU Decomposition**

```math
\begin{align*}
P^{’}A = LU \quad(P^{’} = P_{3}P_{2}P_{1})
\end{align*}
```

```math
\begin{align*}
A = (P^{’})^{-1}LU {}
&= (P_{1}^{-1}P_{2}^{-1}P_{3}^{-1})LU \\\\
&= (P_{1}^{T}P_{2}^{T}P_{3}^{T})LU \\\\
&= PLU \quad(P = P_{1}^{T}P_{2}^{T}P_{3}^{T})
\end{align*}
```
