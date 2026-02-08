### ¶ Gaussian Elimination (From $A$ to $U$) ¶ (from Lecture_03)
Gaussian elimination transforms a $(m \times n)$ matrix $A$ into an <b>REF (row echelon form)</b> $U$<br>
using row operations <b>below the pivots only</b>.
```math
\begin{align}
PA = LU \\
\begin{cases}
P\: (m\times m) \quad:\quad \text{Permutation matrix} \\
L\: (m\times m) \quad:\quad\text{Lower Triangular matrix} \\
U\: (m\times n) \quad:\quad\text{REF (Row Echelon Form)}
\end{cases}
\end{align}
```

Exapmle :
```math
\text{Let}\quad A = \begin{bmatrix}
0 & 0 & 1 & 1 & 0 & 2 \\
1 & 0 & 0 & 1 & 0 & 1 \\
1 & 1 & 1 & 0 & 0 & -1 \\
1 & 1 & 1 & 1 & 0 & 0 \\
0 & 0 & 0 & 0 & 1 & 3 \end{bmatrix}
\quad\text{and initialize}\quad U = A
```

[Step 1]
- Permutation #1 (Swap $R_{1} \leftrightarrow R_{2}$)<br>
The first entry $a_{11} = 0$, so swap $row_{1}$ and $row_{2}$.<br>
```math
U = \begin{bmatrix}
1 & 0 & 0 & 1 & 0 & 1 \\
0 & 0 & 1 & 1 & 0 & 2 \\
1 & 1 & 1 & 0 & 0 & -1 \\
1 & 1 & 1 & 1 & 0 & 0 \\
0 & 0 & 0 & 0 & 1 & 3 \end{bmatrix}
,\quad P_{12}A = U
```
- Elimination #1<br>
Eliminate below pivots in column 1
```math
U = \begin{bmatrix}
1 & 0 & 0 & 1 & 0 & 1 \\
0 & 0 & 1 & 1 & 0 & 2 \\
0 & 1 & 1 & -1 & 0 & -2 \\
0 & 1 & 1 & 0 & 0 & -1 \\
0 & 0 & 0 & 0 & 1 & 3 \end{bmatrix}
,\quad E_{41}(1)E_{31}(1)P_{12}A = U
```

[Step 2]
- Permutation #2 (Swap $R_{2} \leftrightarrow R_{4}$)
```math
U = \begin{bmatrix}
1 & 0 & 0 & 1 & 0 & 1 \\
0 & 1 & 1 & 0 & 0 & -1 \\
0 & 1 & 1 & -1 & 0 & -2 \\
0 & 0 & 1 & 1 & 0 & 2 \\
0 & 0 & 0 & 0 & 1 & 3 \end{bmatrix}
,\quad P_{24}E_{41}(1)E_{31}(1)P_{12}A = U
```
- Elimination #2<br>
Eliminate below pivots in column 2
```math
U = \begin{bmatrix}
1 & 0 & 0 & 1 & 0 & 1 \\
0 & 1 & 1 & 0 & 0 & -1 \\
0 & 0 & 0 & -1 & 0 & -1 \\
0 & 0 & 1 & 1 & 0 & 2 \\
0 & 0 & 0 & 0 & 1 & 3 \end{bmatrix}
,\quad E_{32}(1)P_{24}E_{41}(1)E_{31}(1)P_{12}A = U
```

[Step 3]
- Permutation #3<br>
Swap $R_{3} \leftrightarrow R_{4}$<br>
```math
U = \begin{bmatrix}
1 & 0 & 0 & 1 & 0 & 1 \\
0 & 1 & 1 & 0 & 0 & -1 \\
0 & 0 & 1 & 1 & 0 & 2 \\
0 & 0 & 0 & -1 & 0 & -1 \\
0 & 0 & 0 & 0 & 1 & 3 \end{bmatrix}
,\quad P_{34}E_{32}(1)P_{24}E_{41}(1)E_{31}(1)P_{12}A = U
```
<br>

Now $U$ is <b>REF (row echelon form)</b> and
```math
\begin{cases}
U = P_{34}E_{32}(1)P_{24}E_{41}(1)E_{31}(1)P_{12}A \quad\leftrightarrow\\
A = P_{12}^{T}L_{31}(1)L_{41}(1)P_{24}^{T}L_{32}(1)P_{34}^{T}U
\end{cases}
```
<br><br>

**○ Work with $L$ instead of $E$**<br>
In case of matrix $E$, entries of $E$ gets complicated,<br>
while $L$ comes out with <b>much simpler form</b>.<br>
Multipliers go directly into $L$.<br>

Example :

```math
\begin{align}
\text{Let}\quad
E_{1} = \begin{bmatrix} 1 & 0 & 0 & 0 \\ -e_{1} & 1 & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & 1 \end{bmatrix} , \quad
E_{2} = \begin{bmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ -e_{2} & 0 & 1 & 0 \\ 0 & 0 & 0 & 1 \end{bmatrix} , \quad
E_{3} = \begin{bmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 1 & 0 & 1 & 0 \\ -e_{3} & 0 & 0 & 1 \end{bmatrix} \\
E_{4} = \begin{bmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & -e_{4} & 1 & 0 \\ 0 & 0 & 0 & 1 \end{bmatrix} , \quad
E_{5} = \begin{bmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 0 & -e_{5} & 0 & 1 \end{bmatrix} , \quad
E_{6} = \begin{bmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & -e_{6} & 1 \end{bmatrix} \\\\
\text{then}\quad E = E_{6}E_{5}E_{4}E_{3}E_{2}E_{1} = \begin{bmatrix} 1 & 0 & 0 & 0 \\ -e_{1} & 1 & 0 & 0 \\ e_{1}e_{4}-e_{2} & -e_{4} & 1 & 0 \\ e_{1}e_{5}-e_{3}-e_{1}e_{4}e_{6}+e_{2}e_{6} & e_{4}e_{6}-e_{5} & -e_{6} & 1 \end{bmatrix} \quad\text{(complicated)} \\
\text{while}\quad L = E^{-1} = E_{1}^{-1}E_{2}^{-1}E_{3}^{-1}E_{4}^{-1}E_{5}^{-1}E_{6}^{-1}
= \begin{bmatrix} 1 & 0 & 0 & 0 \\ e_{1} & 1 & 0 & 0 \\ e_{2} & e_{4} & 1 & 0 \\ e_{3} & e_{5} & e_{6} & 1 \end{bmatrix} \quad\text{(simple)}
\end{align}
```
<br>

**○ $PA = LU$ Factorization**

[Swap rows in $L$ switching with $P$]<br>
- When swapping rows, swap rows in $L$ <b>only in the already filled columns</b>.

```math
▶\quad A = P_{12}^{T}\underbrace{L_{31}(1)L_{41}(1)}_{\text{Step 1}}P_{24}^{T}\underbrace{L_{32}(1)}_{\text{Step 2}}P_{34}^{T}U
```
```math
L_{\text{Step 1}} = \underbrace{L_{31}(1)L_{41}(1)}_{\text{Step 1}} = \begin{bmatrix}
1 & 0 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 & 0 \\
1 & 0 & 1 & 0 & 0 \\
1 & 0 & 0 & 1 & 0 \\
0 & 0 & 0 & 0 & 1 \end{bmatrix}
```
```math
L_{\text{Step 1}}P_{24}^{T} = P_{24}^{T}\hat{L}_{\text{Step 1}} \quad\text{where}\quad
\hat{L}_{\text{Step 1}} = \begin{bmatrix}
1 & 0 & 0 & 0 & 0 \\
1 & 1 & 0 & 0 & 0 \\
1 & 0 & 1 & 0 & 0 \\
0 & 0 & 0 & 1 & 0 \\
0 & 0 & 0 & 0 & 1 \end{bmatrix}
```
<br>

```math
▶\quad A = P_{12}^{T}P_{24}^{T}\hat{L}_{\text{Step 1}}\underbrace{L_{32}(1)}_{\text{Step 2}}P_{34}^{T}U
```
```math
L_{\text{Step 2}} = \hat{L}_{\text{Step 1}}\underbrace{L_{32}(1)}_{\text{Step 2}} = \begin{bmatrix}
1 & 0 & 0 & 0 & 0 \\
1 & 1 & 0 & 0 & 0 \\
1 & 1 & 1 & 0 & 0 \\
0 & 0 & 0 & 1 & 0 \\
0 & 0 & 0 & 0 & 1 \end{bmatrix}
```
```math
L_{\text{Step 2}}P_{34}^{T} = P_{34}^{T}\hat{L}_{\text{Step 2}} \quad\text{where}\quad
\hat{L}_{\text{Step 2}} = \begin{bmatrix}
1 & 0 & 0 & 0 & 0 \\
1 & 1 & 0 & 0 & 0 \\
0 & 0 & 1 & 0 & 0 \\
1 & 1 & 0 & 1 & 0 \\
0 & 0 & 0 & 0 & 1 \end{bmatrix}
```
<br>

```math
▶\quad A = (P_{12}^{T}P_{24}^{T}P_{34}^{T})\hat{L}_{\text{Step 2}}U
```
<br>

```math
\begin{align}
\text{Let}\quad \hat{L}_{\text{Step 2}} = L \quad
\text{and}\quad P = P_{34}P_{24}P_{12} \\\\
\text{then}\quad P_{12}^{T}P_{24}^{T}P_{34}^{T} = (P_{34}P_{24}P_{12})^{T} = P^{T} = P^{-1}
\end{align}
```
<br>

```math
\therefore\quad A = P^{-1}LU \quad\leftrightarrow\quad PA = LU
```
```math
\underbrace{\begin{bmatrix}
0 & 1 & 0 & 0 & 0 \\
0 & 0 & 0 & 1 & 0 \\
1 & 0 & 0 & 0 & 0 \\
0 & 0 & 1 & 0 & 0 \\
0 & 0 & 0 & 0 & 1 \end{bmatrix}}_{P} \underbrace{\begin{bmatrix}
0 & 0 & 1 & 1 & 0 & 2 \\
1 & 0 & 0 & 1 & 0 & 1 \\
1 & 1 & 1 & 0 & 0 & -1 \\
1 & 1 & 1 & 1 & 0 & 0 \\
0 & 0 & 0 & 0 & 1 & 3 \end{bmatrix}}_{A} = \underbrace{\begin{bmatrix}
1 & 0 & 0 & 0 & 0 \\
1 & 1 & 0 & 0 & 0 \\
0 & 0 & 1 & 0 & 0 \\
1 & 1 & 0 & 1 & 0 \\
0 & 0 & 0 & 0 & 1 \end{bmatrix}}_{L} \underbrace{\begin{bmatrix}
1 & 0 & 0 & 1 & 0 & 1 \\
0 & 1 & 1 & 0 & 0 & -1 \\
0 & 0 & 1 & 1 & 0 & 2 \\
0 & 0 & 0 & -1 & 0 & -1 \\
0 & 0 & 0 & 0 & 1 & 3 \end{bmatrix}}_{U}
```
<br>

**○ $PLU$ Decomposition**<br>
Permutation matrix $P$ is always <b>orthonormal</b>.<br>
$\rightarrow\quad P^{-1} = P^{T}$<br>
$\therefore\quad PA = LU \quad\leftrightarrow\quad A = P^{T}LU = P^{-1}LU$<br>
<br>

**○ $LDU$ Decomposition**<br>
Suppose we already have $PA = LU^{'}$, with
```math
U^{'} = \begin{bmatrix} u_{11} & * & *  \\ 0 & u_{22} & *  \\ 0 & 0 & u_{33} \end{bmatrix}
```
Then <b>pivots could be seperated</b> into $U^{'} = DU$ where
```math
D = \text{diag}(u_{11}, u_{22}, u_{33}) \quad\text{and}\quad U = \begin{bmatrix} 1 & * & *  \\ 0 & 1 & *  \\ 0 & 0 & 1 \end{bmatrix}
```
$\therefore\quad PA = LU^{'} = LDU$
<br><br><br>

### ¶ Gauss-Jordan Elimination ¶ (from Lecture_03)
An algorithm that uses elementary row operations (swapping, scaling, adding/subtracting rows)<br>
to transform a matrix into <b>RREF (reduced row echelon form)</b>.

Starting from the <b>REF</b> $U$ (from example used in Gauss elimination) :

[Step 1] : Make all the pivots positive $1$<br>
- Scale $R_{4} \leftarrow -R_{4}$
```math
U = \begin{bmatrix}
1 & 0 & 0 & 1 & 0 & 1 \\
0 & 1 & 1 & 0 & 0 & -1 \\
0 & 0 & 1 & 1 & 0 & 2 \\
0 & 0 & 0 & 1 & 0 & 1 \\
0 & 0 & 0 & 0 & 1 & 3 \end{bmatrix}
,\quad D_{4}(-1)EPA = U
```
<br>

[Step 2] : Clear above the pivots<br>
- Eliminate $R_{1} \leftarrow R_{1}-R_{4}$
- Eliminate $R_{3} \leftarrow R_{3}-R_{4}$
```math
U = \begin{bmatrix}
1 & 0 & 0 & 0 & 0 & 0 \\
0 & 1 & 1 & 0 & 0 & -1 \\
0 & 0 & 1 & 0 & 0 & 1 \\
0 & 0 & 0 & 1 & 0 & 1 \\
0 & 0 & 0 & 0 & 1 & 3 \end{bmatrix}
,\quad (E_{34}(1)E_{14}(1)D_{4}(-1)EP)A = U
```
- Eliminate $R_{2} \leftarrow R_{2}-R_{3}$
```math
U = \begin{bmatrix}
1 & 0 & 0 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 & 0 & -2 \\
0 & 0 & 1 & 0 & 0 & 1 \\
0 & 0 & 0 & 1 & 0 & 1 \\
0 & 0 & 0 & 0 & 1 & 3 \end{bmatrix}
,\quad (E_{23}(1)E_{34}(1)E_{14}(1)D_{4}(-1)EP)A = U
```
<br>

Now $U$ is <b>RREF (reduced row echelon form)</b>.
<br><br>

**○ Make inverse through elimination**<br>
If $A$ is <b>square and invertible</b>,<br>
we can get the <b>inverse matrix</b> $A^{-1}$ through Gauss-Jordan elimination.

Example :
```math
\text{Let}\quad A = \begin{bmatrix} 1 & 3 \\ 2 & 7 \end{bmatrix}
```

- Run Gauss-Jordan elimination
```math
\begin{align}
\begin{bmatrix} A & I \end{bmatrix} \quad→\quad \begin{bmatrix} 1 & 3 \\ 2 & 7 \end{bmatrix}\begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix} \\
\begin{bmatrix} E_{21}(2)A & E_{21}(2) \end{bmatrix} \quad→\quad \begin{bmatrix} 1 & 3 \\ 0 & 1 \end{bmatrix}\begin{bmatrix} 1 & 0 \\ -2 & 1 \end{bmatrix} \\
\begin{bmatrix} E_{12}(3)E_{21}(2)A & E_{12}(3)E_{21}(2) \end{bmatrix} \quad→\quad \begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix}\begin{bmatrix} 7 & -3 \\ -2 & 1 \end{bmatrix} \\\\
\therefore\quad (E_{12}(3)E_{21}(2))A = I \quad\leftrightarrow\quad A^{-1} = E_{12}(3)E_{21}(2) = \begin{bmatrix} 7 & -3 \\ -2 & 1 \end{bmatrix}
\end{align}
```
