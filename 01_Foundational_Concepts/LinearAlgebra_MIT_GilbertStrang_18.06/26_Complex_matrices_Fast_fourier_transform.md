# 📚 Lecture 26: Complex matrices; fast fourier transform

### ¶ Complex matrices ¶

|  | Real | Complex | |
| :----: | :-----: | :----: | :----: |
| Symmetric | $A = A^{T}$ | $A = (\overline{A})^{T} = A^{H}$ | Hermitian |
| Orthogonal | $Q^{-1} = Q^{T}$ | $U^{-1} = U^{H}$ | Unitary |

```math
\text{For}\quad \vec{z} = \begin{bmatrix} z_{1} \\ z_{2} \\ \vdots \\ z_{n} \end{bmatrix} \quad(\in C^{n})
```
<br>

$\vec{z}^{T}\vec{z}$ $(\text{length}^{2})$ should be postive, but it's not.
```math
\text{Example : } \vec{z}^{T}\vec{z} = \begin{bmatrix} 1 & 2i \end{bmatrix} \begin{bmatrix} 1 \\ 2i \end{bmatrix} = 1 - 4 = -3
```
<br>

- Hermitian<br>
$H$ stands for Hermitian.<br>
$\vec{z}^{H}\vec{z}$ is always positive. (except $\vec{z} = \vec{0}$)
```math
\text{For}\quad z_{k}=a_{k}+ib_{k} \quad\text{and}\quad \overline{z}_{k}=a_{k}-ib_{k}
```
```math
\begin{align}
\vec{z}^{H}\vec{z} = \vec{(\overline{z})}^{T}\vec{z} {} &= \begin{bmatrix} \overline{z}_{1} & \overline{z}_{2} & \cdots & \overline{z}_{n} \end{bmatrix} \begin{bmatrix} z_{1} \\ z_{2} \\ \vdots \\ z_{n} \end{bmatrix} \\
&= (a_{1}^{2}+b_{1}^{2}) + (a_{2}^{2}+b_{2}^{2}) + \cdots + (a_{n}^{2}+b_{n}^{2}) \:\ge\: 0
\end{align}
```
<br>

```math
\text{Example : } \vec{(\overline{z})}^{T}\vec{z} = \begin{bmatrix} 1 & -2i \end{bmatrix} \begin{bmatrix} 1 \\ 2i \end{bmatrix} = 1+4 = 5
```
<br><br>


### ¶ Fast Fourier Transform ¶

Fourier Matrix (The most important complex matrix)

Time complexity : from $O(N^{2})$ to $O(N\log_{2}{N})$

**○ DFT matrix** <a href="https://en.wikipedia.org/wiki/DFT_matrix">(Wikipedia)</a>

```math
\begin{align}
F_{N} = \begin{bmatrix}
1 & 1 & 1 & \cdots & 1 \\
1 & w_{N}^{1} & w_{N}^{2} & \cdots & w_{N}^{N-1} \\
1 & w_{N}^{2} & w_{N}^{4} & \cdots & w_{N}^{2(N-1)} \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
1 & w_{N}^{N-1} & w_{N}^{2(N-1)} & \cdots & w_{N}^{(N-1)^{2}}
\end{bmatrix} \\\\\\
\rightarrow\quad (F_{N})_{ij} = w_{N}^{ij} \quad(\text{where}\: i, j \in \set{0, 1, \cdots, (N-1)})
\end{align}
```

```math
\begin{align}
(w_{N})^{N} = 1 \\
w_{N}= \begin{cases}
e^{\frac{i2\pi}{N}} = \cos{\frac{2\pi}{N}} + i\sin{\frac{2\pi}{N}} \quad\text{(counter-clockwise)} \\
e^{\frac{-i2\pi}{N}} = \cos{\frac{2\pi}{N}} - i\sin{\frac{-2\pi}{N}} \quad\text{(clockwise)}
\end{cases}
\end{align}
```

When $N = 4$,<br>
$w_{4} = e^{\frac{i2\pi}{4}} = \cos{\frac{2\pi}{4}} + i\sin{\frac{2\pi}{4}} = i$

```math
\begin{align}
\therefore\quad F_{4} = \begin{bmatrix}
1 & 1 & 1 & 1 \\
1 & i^{1} & i^{2} & i^{3} \\
1 & i^{2} & i^{4} & i^{6} \\
1 & i^{3} & i^{6} & i^{9}
\end{bmatrix}
= \begin{bmatrix}
1 & 1 & 1 & 1 \\
1 & i & -1 & -i \\
1 & -1 & 1 & -1 \\
1 & -i & -1 & i
\end{bmatrix}
\end{align}
```
<br>

**○ DFT Factorization**
<a href="https://github.com/Seunghoon-Schini-Yang/DL_RecSys_Portfolio/blob/main/01_Foundational_Concepts/LinearAlgebra_MIT_GilbertStrang_18.06/Proofs/26_DFT_factorization.md">(See proof)</a>


Let $N = 2M$, then
```math
\begin{align}
\vec{X} {} &= F_{N}\vec{x} \\\\
&= \begin{bmatrix} I_{M} & D_{M} \\ I_{M} & -D_{M} \end{bmatrix}
\begin{bmatrix} F_{M} & 0 \\ 0 & F_{M} \end{bmatrix}P_{N}\vec{x}
\end{align}
```
<br>

```math
\therefore\quad F_{N} = \begin{bmatrix} I_{M} & D_{M} \\ I_{M} & -D_{M} \end{bmatrix}
\begin{bmatrix} F_{M} & 0 \\ 0 & F_{M} \end{bmatrix}P_{N}
```

where
```math
\begin{align}
F_{M} = \begin{bmatrix}
1 & 1 & 1 & \cdots & 1 \\
1 & w_{M}^{1} & w_{M}^{2} & \cdots & w_{M}^{M-1} \\
1 & w_{M}^{2} & w_{M}^{4} & \cdots & w_{M}^{2(M-1)} \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
1 & w_{M}^{M-1} & w_{M}^{2(M-1)} & \cdots & w_{M}^{(M-1)^{2}}
\end{bmatrix} \quad,\quad
D_{M} = \begin{bmatrix}
1 & & & & \\
& w_{N} & & & \\
& & (w_{N})^{2} & & \\
& & & \ddots & \\
& & & & (w_{N})^{M-1}
\end{bmatrix} \\\\\\
P_{N} \text{ : even-odd permutation matrix} \\
0 \text{ : } (M \times M) \:\text{zero matrix.}
\end{align}
```

For Example,
```math
\begin{align}
F_{4} {} &=  \begin{bmatrix} I_{2} & D_{2} \\ I_{2} & -D_{2} \end{bmatrix}
\begin{bmatrix} F_{2} & 0 \\ 0 & F_{2} \end{bmatrix}P_{4} \\
&= \begin{bmatrix}
1 & 0 & 1 & 0 \\
0 & 1 & 0 & w_{4} \\
1 & 0 & 1 & 0 \\
0 & 1 & 0 & w_{4}
\end{bmatrix} \begin{bmatrix}
1 & 1 & 0 & 0 \\
1 & w_{2} & 0 & 0 \\
0 & 0 & 1 & 1 \\
0 & 0 & 1 & w_{2}
\end{bmatrix} \begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 0 & 1
\end{bmatrix} \\
&= \begin{bmatrix}
1 & 0 & 1 & 0 \\
0 & 1 & 0 & i \\
1 & 0 & 1 & 0 \\
0 & 1 & 0 & i
\end{bmatrix} \begin{bmatrix}
1 & 1 & 0 & 0 \\
1 & -1 & 0 & 0 \\
0 & 0 & 1 & 1 \\
0 & 0 & 1 & -1
\end{bmatrix} \begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 0 & 1
\end{bmatrix} \\
&= \begin{bmatrix}
1 & 1 & 1 & 1 \\
1 & i & -1 & -i \\
1 & -1 & 1 & -1 \\
1 & -i & -1 & i
\end{bmatrix} = F_{4}
\end{align}
```
