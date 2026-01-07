# 📚 Lecture 24: Markov matrices; Fourier series

### ¶ Markov matrices ¶

**○ Properties of Markov matrices**

For $(n \times n)$ <b>Markov</b> matrix $A$,

① All entries of $A$ are greater than or equal to $0$. $(a_{ij} >= 0)$<br>
② Sum of each column equals $1$. $(\sum_{j=1}^{n}a_{ij} = 1)$<br>

**○ Eigenvalues of Markov matrices**

① One of eigenvalues $\lambda_{k} = 1$.<br>
Proof) Sum of each column of $(A-I)$ equals to zero.<br>
→ Sum of all rows of $(A-I)$ equals to zero vector.<br>
```math
(A-I)^{T}\begin{bmatrix} 1 \\ \vdots \\ 1 \end{bmatrix} = \vec{0} \quad\rightarrow\quad \begin{bmatrix} 1 \\ \vdots \\ 1 \end{bmatrix} \in N((A-I)^{T})
```
→ rows of $(A-I)$ are linearly dependent.<br>
$\therefore\quad det(A-I) = 0 \quad\leftrightarrow\quad \lambda = 1$

② All other eigenvalues are $|\lambda_{j}| < 1$. $(j \not= k)$<br>

Exception : $I$ (= Identity Matrix)<br>
<br>

**○ Steady State**

As $k \to \infty$, the system of Markov matrix goes into <b>steady state</b>.
```math
\begin{align}
\lim_{k\to\infty} \vec{u}_{k} {} &= \lim_{k\to\infty} A^{k}\vec{u}_{0} \\
&= \lim_{k\to\infty} (c_{1}\lambda_{1}^{k}\vec{v}_{1} + c_{2}\lambda_{2}^{k}\vec{v}_{2} + \cdots + c_{n}\lambda_{n}^{k}\vec{v}_{n}) \\
&= c_{1}\vec{v}_{1} \quad(\because\: \lambda_{1} = 1 \quad\text{and}\quad |\lambda_{i}| < 1 \quad(i \not= 1))
\end{align}
```
<br>

**○ Exapmle**

```math
\text{For}\quad A = \begin{bmatrix}
0.1 & 0.5 & 0.5 \\
0.3 & 0.1 & 0.2 \\
0.6 & 0.4 & 0.3 \end{bmatrix} \quad\text{and}\quad \vec{u}_{0} = \begin{bmatrix} 21 \\ 21 \\ 21 \end{bmatrix}
```
<br>

```math
\begin{align}
\lambda_{1} = 1,\quad \lambda_{2} = -\frac{2}{5},\quad \lambda_{3} = -\frac{1}{10} \\
\vec{v}_{1} = \begin{bmatrix} \frac{5}{6} \\ \frac{1}{2} \\ 1 \end{bmatrix},\quad \vec{v}_{2} = \begin{bmatrix} -\frac{3}{2} \\ \frac{1}{2} \\ 1 \end{bmatrix},\quad \vec{v}_{3} = \begin{bmatrix} 0 \\ -1 \\ 1 \end{bmatrix} \\
\therefore\quad S = \begin{bmatrix}
\frac{5}{6} & -\frac{3}{2} & 0 \\
\frac{1}{2} & \frac{1}{2} & -1 \\
1 & 1 & 1 \end{bmatrix},\quad S^{-1} = \begin{bmatrix}
\frac{3}{7} & \frac{3}{7} & \frac{3}{7} \\
-\frac{3}{7} & \frac{5}{21} & \frac{5}{21} \\
0 & -\frac{2}{3} & \frac{1}{3} \end{bmatrix}
\end{align}
```
<br>

```math
\begin{align}
\vec{u}_{0} = c_{1}\vec{v}_{1} + c_{2}\vec{v}_{2} + c_{3}\vec{v}_{3} = S\begin{bmatrix} c_{1} \\ c_{2} \\ c_{3} \end{bmatrix} \\
\therefore\quad \begin{bmatrix} c_{1} \\ c_{2} \\ c_{3} \end{bmatrix} = S^{-1}\vec{u}_{0} = \begin{bmatrix}
\frac{3}{7} & \frac{3}{7} & \frac{3}{7} \\
-\frac{3}{7} & \frac{5}{21} & \frac{5}{21} \\
0 & -\frac{2}{3} & \frac{1}{3} \end{bmatrix} \begin{bmatrix} 21 \\ 21 \\ 21 \end{bmatrix} = \begin{bmatrix} 27 \\ 1 \\ -7 \end{bmatrix}
\end{align}
```
<br>

```math
\begin{align}
\vec{u}_{k} {} &= c_{1}\lambda_{1}^{k}\vec{v}_{1} + c_{2}\lambda_{2}^{k}\vec{v}_{2} + c_{3}\lambda_{3}^{k}\vec{v}_{3} \\\\
&= 27\begin{bmatrix} \frac{5}{6} \\ \frac{1}{2} \\ 1 \end{bmatrix} + (-\frac{2}{5})^{k}\begin{bmatrix} -\frac{3}{2} \\ \frac{1}{2} \\ 1 \end{bmatrix} + (-7)(-\frac{1}{10})^{k}\begin{bmatrix} 0 \\ -1 \\ 1 \end{bmatrix}
\end{align}
```

```math
\therefore\quad \lim_{k\to\infty} \vec{u}_{k} = 27\begin{bmatrix} \frac{5}{6} \\ \frac{1}{2} \\ 1 \end{bmatrix} = \begin{bmatrix} 22.5 \\ 13.5 \\ 27 \end{bmatrix}
```
<br>

```math
\therefore\quad\text{As time goes by,}\quad \vec{u}_{0} = \begin{bmatrix} 21 \\ 21 \\ 21 \end{bmatrix} \quad\text{become}\quad \lim_{k\to\infty} \vec{u}_{k} = \begin{bmatrix} 22.5 \\ 13.5 \\ 27 \end{bmatrix}
```
<br>

### ¶ Fourier series ¶

**○ Projections with orthonormal basis**

```math
\begin{align}
\vec{v} {} &= x_{1}\vec{q}_{1} + x_{2}\vec{q}_{2} + \cdots + x_{n}\vec{q}_{n} \\
&= \begin{bmatrix} \vec{q}_{1} & \vec{q}_{2} & \cdots & \vec{q}_{n} \end{bmatrix} \begin{bmatrix} x_{1} \\ x_{2} \\ \vdots \\ x_{n} \end{bmatrix} \\
&= Q\vec{x}
\end{align}
```

```math
\therefore\quad \vec{x} = Q^{-1}\vec{v} = Q^{T}\vec{v} = \begin{bmatrix} \vec{q}^{T}_{1}\vec{v} \\ \vec{q}^{T}_{2}\vec{v} \\ \vdots \\ \vec{q}^{T}_{n}\vec{v} \end{bmatrix} = \begin{bmatrix} x_{1} \\ x_{2} \\ \vdots \\ x_{n} \end{bmatrix}
```

```math
\begin{pmatrix}
\begin{align}
\vec{q}^{T}_{1}\vec{v} {} &= x_{1}\vec{q}^{T}_{1}\vec{q}_{1} + x_{2}\vec{q}^{T}_{2}\vec{q}_{2} + \cdots + x_{n}\vec{q}^{T}_{n}\vec{q}_{n} \\\\
&= x_{1} + 0 + \cdots + 0 \\\\
&= x_{1}
\end{align}
\end{pmatrix}
```
<br>

**○ Fourier Series**

- What's the dot product of functions?

  - Vectors
    ```math
    \vec{v}^{T}\vec{w} = v_{1}w_{1} + v_{2}w_{2} + \cdots + v_{n}w_{n}
    ```

  - Functions

For example, as similar as vectors,<br>
dot product of functions could be expressed in this way.
```math
\begin{align}
\vec{f}^{T}\vec{g} {} &= \begin{bmatrix} f(0) & f(1) & f(2) & \cdots & f(9) & f(10) \end{bmatrix} \begin{bmatrix} g(0) \\ g(1) \\ g(2) \\ \vdots \\ g(9) \\ g(10) \end{bmatrix} \\
&= f(0)g(0) + f(1)g(1) + f(2)g(2) + \cdots + f(9)g(9) + f(10)g(10) \\\\
&= \sum_{x=0}^{10} f(x)g(x) \Delta x
\end{align}
```
<br>

```math
\therefore\quad f^{T}g = \int f(x)g(x) dx
```
<br>

- Periodic Functions : $f(x) = f(x+T)$<br>
$(\sin{mx}, \cos{nx})$ are periodic functions having $(\frac{2\pi}{m}, \frac{2\pi}{n})$ periods.

```math
f^{T}g = \int_{0}^{2\pi} f(x)g(x) dx = \int_{-\pi}^{\pi} f(x)g(x) dx
```
<br>

- Orthogonality

```math
\begin{align}
\int_{-\pi}^{\pi} \sin{(nx)}\cos{(mx)} dx
{} &= \int_{-\pi}^{\pi} \frac{1}{2}(\sin{(n+m)x}+\sin{(n-m)x}) dx \\
&= \frac{1}{2}[-\frac{1}{n+m}\cos{(n+m)x} - \frac{1}{n-m}\cos{(n-m)x}]\big|_{-\pi}^{\pi} \\\\
&= 0 \\\\
& \therefore\: \sin{(nx)} \:\text{and}\: \cos{(mx)} \:\text{are orthogonal.}
\end{align}
```
<br>

```math
\begin{align}
\int_{-\pi}^{\pi} \sin{(nx)}\sin{(mx)} dx
{} &= \int_{-\pi}^{\pi} \frac{1}{2}(\cos{(n-m)x}-\cos{(n+m)x}) dx \\
&= \frac{1}{2}[\frac{1}{n-m}\sin{(n-m)x} - \frac{1}{n+m}\sin{(n+m)x}]\big|_{-\pi}^{\pi} \\\\
&= 0 \quad(n \not= m) \\\\
& \therefore\: \sin{(nx)} \:\text{and}\: \sin{(mx)} \:\text{are orthogonal.}
\end{align}
```
<br>

```math
\begin{align}
\int_{-\pi}^{\pi} \cos{(nx)}\cos{(mx)} dx
{} &= \int_{-\pi}^{\pi} \frac{1}{2}(\cos{(n+m)x}+\cos{(n-m)x}) dx \\
&= \frac{1}{2}[\frac{1}{n+m}\sin{(n+m)x} - \frac{1}{n-m}\sin{(n-m)x}]\big|_{-\pi}^{\pi} \\\\
&= 0 \quad(n \not= m) \\\\
& \therefore\: \cos{(nx)} \:\text{and}\: \cos{(mx)} \:\text{are orthogonal.}
\end{align}
```
<br>

- Fourier Series

```math
f(x) = a_{0} + a_{1}\cos{x} + b_{1}\sin{x} + a_{2}\cos{2x} + b_{2}\sin{2x} + \cdots
```
<br>

Constants $(a_{0}, a_{1}, b_{1}, \cdots)$

```math
\begin{align}
\int_{0}^{2\pi} f(x) dx = [a_{0}x]\big|_{0}^{2\pi} = 2\pi a_{0} \\\\
\therefore\: a_{0} = \frac{1}{2\pi} \int_{0}^{2\pi} f(x) dx
\end{align}
```
<br>

```math
\begin{align}
\int_{0}^{2\pi} f(x)\cos{x} dx &= \int_{0}^{2\pi} a_{1}(\cos{x})^{2} dx \\
&= a_{1} \int_{0}^{2\pi} \frac{1+\cos{2x}}{2} dx \\
&= a_{1} [\frac{2x+\sin{2x}}{4}]|_{0}^{2\pi} \\\\
&= \pi a_{1}
\end{align}
```
```math
\therefore\: a_{1} = \frac{1}{\pi} \int_{0}^{2\pi} f(x)\cos{x} dx
```
<br>

```math
\begin{align}
\int_{0}^{2\pi} f(x)\sin{x} dx &= \int_{0}^{2\pi} b_{1}(\sin{x})^{2} dx \\
&= b_{1} \int_{0}^{2\pi} \frac{1-\cos{2x}}{2} dx \\
&= b_{1} [\frac{2x-\sin{2x}}{4}]|_{0}^{2\pi} \\\\
&= \pi b_{1}
\end{align}
```
```math
\therefore\: b_{1} = \frac{1}{\pi} \int_{0}^{2\pi} f(x)\sin{x} dx
```
