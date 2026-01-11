# 📚 Lecture 26: Complex matrices; fast fourier transform

### ¶ Complex matrices ¶

|  | Real | Complex | |
| :----: | :-----: | :----: | :----: |
| Symmetric | $A = A^{T}$ | $A = (\overline{A})^{T} = A^{H}$ | Hermitian |
| Orthogonal | $Q^{-1} = Q^{T}$ | $U^{-1} = U^{H}$ | Unitary |


\vec{z} = \begin{bmatrix} z_{1} \\ z_{2} \\ \vdots \\ z_{n} \end{bmatrix} (\in C^{n})

\vec{z}^{T}\vec{z} is no good.

\begin{bmatrix} z_{1} & z_{2} & \vdots & z_{n} \end{bmatrix} \begin{bmatrix} z_{1} \\ z_{2} \\ \vdots \\ z_{n} \end{bmatrix}

(length)^{2} should be postive, but \vec{z}^{T}\vec{z} is not.

(example)
\vec{z}^{T}\vec{z} \begin{bmatrix} 1 & i \end{bmatrix} \begin{bmatrix} 1 \\ i \end{bmatrix} = 1 - 1 = 0

(conjugate)
H stands for Hermitian.
\vec{z}^{H}\vec{z} is always positive. (except \vec{0})

\vec{z}^{H}\vec{z} = \vec{(\overline{z})}^{T}\vec{z} = \begin{bmatrix} \overline{z}_{1} & \overline{z}_{2} & \vdots & \overline{z}_{n} \end{bmatrix} \begin{bmatrix} z_{1} \\ z_{2} \\ \vdots \\ z_{n} \end{bmatrix} = |z_{1}|^{2} + |z_{2}|^{2} + \cdots + |z_{n}|^{2}

(example)
\vec{z}^{H}\vec{z} = \begin{bmatrix} 1 & -i \end{bmatrix} \begin{bmatrix} 1 \\ i \end{bmatrix} = 1 + 1 = 2


### ¶ Fast Fourier Transform ¶

Fourier Matrix (The most important complex matrix)

Time complexity : from $O(n^{2})$ to $O(n\log_{2}n)$

**○ DFT matrix** <a href="https://en.wikipedia.org/wiki/DFT_matrix">(Wikipedia)</a>

```math
\begin{align}
F_{n} = \begin{bmatrix}
1 & 1 & 1 & \cdots & 1 \\
1 & w^{1} & w^{2} & \cdots & w^{n-1} \\
1 & w^{2} & w^{4} & \cdots & w^{2(n-1)} \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
1 & w^{n-1} & w^{2(n-1)} & \cdots & w^{(n-1)^{2}}
\end{bmatrix} \\\\\\
\therefore\quad (F_{n})_{ij} = w^{ij} \quad(\text{where}\: i, j \in \set{0, 1, \cdots, n-1})
\end{align}
```

```math
\begin{align}
w^{n} = 1 \\
w = \begin{cases}
e^{\frac{i2\pi}{n}} = \cos{\frac{2\pi}{n}} + i\sin{\frac{2\pi}{n}} \quad\text{(counter-clockwise)} \\
e^{\frac{-i2\pi}{n}} = \cos{\frac{2\pi}{n}} - i\sin{\frac{-2\pi}{n}} \quad\text{(clockwise)}
\end{cases}
\end{align}
```

if $n = 4$,<br>
then $w = e^{\frac{i2\pi}{4}} = \cos{\frac{2\pi}{4}} + i\sin{\frac{2\pi}{4}} = i$

```math
\begin{align}
F_{4} = \begin{bmatrix}
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

```math
\begin{align}
F_{64} =
\begin{bmatrix} I_{32} & D_{32} \\ I_{32} & -D_{32} \end{bmatrix}
\begin{bmatrix} F_{32} & O_{32} \\ O_{32} & F_{32} \end{bmatrix}

\\

D_{n} = \begin{bmatrix}
1 & & & & \\
& w & & & \\
& & w^{2} & & \\
& & & \ddots & \\
& & & & w^{n-1}
\end{bmatrix}
\end{align}
```


```math
\begin{align}

\end{align}
```


① If all entries of Symmetric matrix are <b>real</b>, then all the eigenvalues are also <b>real</b>.<br>
② The eigenvectors are <b>perpendicular</b> to each other.
