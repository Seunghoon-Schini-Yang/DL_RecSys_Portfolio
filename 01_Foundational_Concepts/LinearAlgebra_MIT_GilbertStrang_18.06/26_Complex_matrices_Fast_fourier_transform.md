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

if $N = 4$,<br>
then $w_{4} = e^{\frac{i2\pi}{4}} = \cos{\frac{2\pi}{4}} + i\sin{\frac{2\pi}{4}} = i$

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

Let $N = 2M$,

```math
\begin{align}
\text{then}\quad \vec{X} {} &= F_{N}\vec{x} \\
&= \begin{bmatrix} I_{M} & D_{M} \\ I_{M} & -D_{M} \end{bmatrix}
\begin{bmatrix} F_{M} & O_{M} \\ O_{M} & F_{M} \end{bmatrix}P_{N}\vec{x}
\end{align}
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
P_{N} permutation \quad\text{and}\: O_{M} \:\text{is}\: (M \times M) \:\text{zero matrix.}
\end{align}
```

General proof for $N = 2M$,<br>
Use the DFT definition with $w_{N} = e^{-\frac{i2\pi}{N}}$ (counter-clockwise)

```math
\begin{align}
X_{k} = \sum_{n=0}^{N-1}x_{n}(w_{N})^{kn}, \quad (k = 0, 1, \cdots , N-1)
\end{align}
```

Split the sum into even and odd indices :<br>
even: $n = 2m$ where $m = 0, 1, \cdots , M-1$<br>
odd: $n = 2m+1$ where $m = 0, 1, \cdots , M-1$<br><br>

Then
```math
\begin{align}
X_{k} {} &= \sum_{m=0}^{M-1}x_{2m}(w_{N})^{k(2m)} + \sum_{m=0}^{M-1}x_{2m+1}(w_{N})^{k(2m+1)} \\\\\\
&= \Big(\sum_{m=0}^{M-1}x_{2m}(w_{N}^{2})^{km}\Big) + w_{N}^{k}\Big(\sum_{m=0}^{M-1}x_{2m+1}(w_{N}^{2})^{km}\Big) \\\\\\
&= \Big(\sum_{m=0}^{M-1}x_{2m}(w_{M})^{km}\Big) + w_{N}^{k}\Big(\sum_{m=0}^{M-1}x_{2m+1}(w_{M})^{km}\Big) \quad(\because\: w_{N}^{2} = e^{-\frac{i4\pi}{N}} = e^{-\frac{i2\pi}{M}} = w_{M})
\end{align}
```
<br>

So define the two length $M$ DFTs :
```math
E_{k} := \sum_{m=0}^{M-1}x_{2m}(w_{M})^{km} ,\quad O_{k} := \sum_{m=0}^{M-1}x_{2m+1}(w_{M})^{km}
```
<br>

Then for all $k$ :
```math
X_{k} = E_{k} + w_{N}^{k}O_{k} \quad\text{----}\quad\text{(1)}
```
<br>

Now use periodicity of length $M$ DFT outputs :
```math
E_{k+M} = E_{k} ,\quad O_{k+M} = O_{k}
```
<br>

Compute the “upper half” outputs $(k = 0, 1, \cdots, M-1)$<br>
and the "lower half" $(k+M)$ :
```math
\begin{align}
X_{k+M} {} &= E_{k+M} + w_{N}^{k+M}O_{k+M} \\\\
&= E_{k+M} + w_{N}^{M}w_{N}^{k}O_{k+M} \\\\
&= E_{k} + w_{N}^{k}w_{N}^{M}O_{k} \\\\
&= E_{k} - w_{N}^{k}O_{k} \quad(\because\: w_{N}^{M} = -1) \quad\text{----}\quad\text{(2)}
\end{align}
```
<br>

Combine equations (1)-(2) into a block system. Let
```math
\vec{E} = \begin{bmatrix} E_{0} \\ E_{1} \\ \vdots \\ E_{M-1} \end{bmatrix}, \quad
\vec{O} = \begin{bmatrix} O_{0} \\ O_{1} \\ \vdots \\ O_{M-1} \end{bmatrix}, \quad
\vec{X} = \begin{bmatrix} X_{0} \\ X_{1} \\ \vdots \\ X_{M-1} \end{bmatrix}
```
<br>

Then (1)–(2) for $k = 0, 1, \cdots, M-1$ is exactly :
```math
\vec{X} = \begin{bmatrix} \vec{X}_{0:M-1} \\ \vec{X}_{M:N-1} \end{bmatrix}
= \begin{bmatrix} I_{M} & D_{M} \\ I_{M} & -D_{M} \end{bmatrix} \begin{bmatrix} \vec{E} \\ \vec{O} \end{bmatrix} \quad\text{----}\quad\text{(3)}
```
<br>

Next, recognize $E$ and $O$ are DFTs of the even/odd subsequences:
```math
\vec{E} = F_{M}\vec{x}_{even} ,\quad \vec{O} = F_{M}\vec{x}_{odd}
```
where
```math
\vec{x}_{even} = \begin{bmatrix} x_{0} \\ x_{2} \\ \vdots \\ x_{N-2} \end{bmatrix}, \quad
\vec{x}_{odd} = \begin{bmatrix} x_{1} \\ x_{3} \\ \vdots \\ x_{N-1} \end{bmatrix}
```
Stack them :
```math
\begin{bmatrix} \vec{E} \\ \vec{O} \end{bmatrix}
= \begin{bmatrix} F_{M} & 0 \\ 0 & F_{M} \end{bmatrix} \begin{bmatrix} \vec{x}_{even} \\ \vec{x}_{odd} \end{bmatrix} \quad\text{----}\quad\text{(4)}
```
<br>

Finally, define the permutation $P_{N}$ that reorders the input into evens then odds :
```math
\begin{bmatrix} \vec{x}_{even} \\ \vec{x}_{odd} \end{bmatrix} = P_{N}\vec{x} ,\quad
P_{N} = \begin{bmatrix}
1 & 0 & 0 & 0 & \cdots & 0 & 0 \\
0 & 0 & 1 & 0 & \cdots & 0 & 0 \\
\vdots & \vdots & \vdots & \vdots & \ddots & \vdots & \vdots \\
0 & 0 & 0 & 0 & \cdots & 1 & 0 \\
0 & 1 & 0 & 0 & \cdots & 0 & 0 \\
0 & 0 & 0 & 1 & \cdots & 0 & 0 \\
\vdots & \vdots & \vdots & \vdots & \ddots & \vdots & \vdots \\
0 & 0 & 0 & 0 & \cdots & 0 & 1
\end{bmatrix} \quad\text{----}\quad\text{(5)}
```
<br>

Substitute (4) and (5) into (3) :
```math
\begin{align}
\vec{X} = \begin{bmatrix} \vec{X}_{0:M-1} \\ \vec{X}_{M:N-1} \end{bmatrix} {} &= \begin{bmatrix} I_{M} & D_{M} \\ I_{M} & -D_{M} \end{bmatrix} \begin{bmatrix} \vec{E} \\ \vec{O} \end{bmatrix} \\\\
&= \begin{bmatrix} I_{M} & D_{M} \\ I_{M} & -D_{M} \end{bmatrix} \begin{bmatrix} F_{M} & 0 \\ 0 & F_{M} \end{bmatrix} \begin{bmatrix} \vec{x}_{even} \\ \vec{x}_{odd} \end{bmatrix} \\\\
&= \begin{bmatrix} I_{M} & D_{M} \\ I_{M} & -D_{M} \end{bmatrix} \begin{bmatrix} F_{M} & 0 \\ 0 & F_{M} \end{bmatrix} P_{N}\vec{x}
\end{align}
```
<br>

Since $\vec{X} = F_{N}\vec{x}$, for all the matrix identity is proven:
```math
\therefore\quad F_{N} = \begin{bmatrix} I_{M} & D_{M} \\ I_{M} & -D_{M} \end{bmatrix} \begin{bmatrix} F_{M} & 0 \\ 0 & F_{M} \end{bmatrix} P_{N} ,\quad(N = 2M)
```
<br>

That’s the full radix-2 decimation-in-time FFT factorization.

“Full radix-2 decimation-in-time (DIT) FFT factorization” means you apply that $N = 2M$ matrix identity repeatedly, halving the DFT size each time, until you reach $𝐹_{2}$ (or $F_{1}$). That turns the 
$𝑁$ point DFT into $\log_{2}{N}$ stages of butterflies + twiddles, with an initial bit-reversal permutation.

