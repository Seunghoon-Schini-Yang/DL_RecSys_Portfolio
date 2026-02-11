### ¶ DFT Factorization ¶

```math
\begin{align}
\vec{X} {} &= F_{N}\vec{x} \\\\
&= \begin{bmatrix} I_{M} & D_{M} \\ I_{M} & -D_{M} \end{bmatrix}
\begin{bmatrix} F_{M} & 0 \\ 0 & F_{M} \end{bmatrix}P_{N}\vec{x}
\end{align}
```
<br>

- General proof for $N = 2M$<br>
Use the DFT definition with $w_{N} = e^{-\frac{i2\pi}{N}}$ (clockwise)

```math
\begin{align}
X_{k} = \sum_{n=0}^{N-1}x_{n}(w_{N})^{kn}, \quad (k = 0, 1, \cdots , N-1)
\end{align}
```

Split the sum into even and odd indices :<br>
(even) $n = 2m$ where $m = 0, 1, \cdots , M-1$<br>
(odd) $n = 2m+1$ where $m = 0, 1, \cdots , M-1$<br><br>

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

Since $\vec{X} = F_{N}\vec{x}$, for all the matrix identity is proven :
```math
\therefore\quad F_{N} = \begin{bmatrix} I_{M} & D_{M} \\ I_{M} & -D_{M} \end{bmatrix} \begin{bmatrix} F_{M} & 0 \\ 0 & F_{M} \end{bmatrix} P_{N} ,\quad(N = 2M)
```
<br><br><br>


**○ Time Complexity : From $O(N^{2})$ to $O(N\log_{2}{N})$**

That’s the full radix-2 decimation-in-time FFT factorization.

“Full radix-2 decimation-in-time (DIT) FFT factorization” means<br>
you apply that $N = 2M$ matrix identity repeatedly,<br>
halving the DFT size each time, until you reach $𝐹_{2}$ (or $F_{1}$).<br>
That turns the $𝑁$ point DFT into $\log_{2}{N}$ stages of butterflies + twiddles,<br>
with an initial bit-reversal permutation.
<br>

<p align="center">
    <img src="../images/lecture_26_01.jpg" alt="img_26_01" width="500">
</p><br>

1) Why the DFT is $O(N^{2})$
The DFT is
```math
X_{k} = \sum_{n=0}^{N-1}x_{n}w_{N}^{kn}
```

There are $N$ outputs $(k = 0, 1, \cdots, N-1)$.<br>
Each ouput is a sum of $N$ terms.<br>
So total multiplications and additions scale like :
```math
N \times N = N^{2}
```
<br>

2) The key FFT idea : split into two smaller DFTs<br>
For $N = 2M$, we proved :
```math
X_{k} = E_{k} + w_{N}^{k}O_{k} ,\quad X_{k+M} = E_{k} - w_{N}^{k}O_{k}
```
where $E_{k}$ and $O_{k}$ are DFTs of length $M$. (even and odd parts)

So one $N$ point DFT becomes :<br>
→ two $M$ point DFTs (recursive work)<br>
→ plus $N$ extra “combine” operations (butterflies)

That gives the recurrence :
```math
T(N) = 2T(N/2) + O(N)
```
<br>

3) Solve the recurrence → $O(NlogN)$<br>
Each stage costs O(N) because :<br>
there are $N/2$ butterflies<br>
each butterfly does constant work (1 multiply + 2 adds, roughly)

You keep <b>halving</b> until size 1.<br>
That takes $\log_{2}{N}$ stages.
```math
N \:\rightarrow\: \frac{N}{2} \:\rightarrow\: \frac{N}{4} \:\rightarrow\: \cdots \:\rightarrow\: 1
```

So total work costs :
```math
O(N) \times O(\log{N}) = O(N\log{N})
```
