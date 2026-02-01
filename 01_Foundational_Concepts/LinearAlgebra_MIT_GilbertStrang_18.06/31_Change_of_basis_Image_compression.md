# 📚 Lecture 31: Change of basis; image compression

### ¶ Change of basis ¶

**○ Mapping coordinates to other coordinates**<br>
```math
\begin{align}
(\text{In standard basis}\: \set{\vec{e}_{1}, \cdots,\vec{e}_{n}})\quad \vec{x} = V[\vec{x}]_{B} \quad(\text{in basis}\: \set{\vec{v}_{1},\cdots,\vec{v}_{n}})
\end{align}
```
```math
\therefore\quad \begin{cases} \vec{x} = V[\vec{x}]_{B} \quad(V \:\text{maps coordinates in basis}\: B \:\text{→ standard coordinates}) \\
[\vec{x}]_{B} = V^{-1}\vec{x} \quad(V^{-1} \:\text{maps standard coordinates → coordinates in basis}\: B) \end{cases}
```
<br>

- Input : Standard coordinates $\vec{x} \in R^{n}$
- Output : Standard coordinates $\vec{y} \in R^{m}$
```math
\begin{align}
\vec{y} = T(\vec{x}) {} &= T(x_{1}\vec{e}_{1} + \cdots + x_{n}\vec{e}_{n}) \\
&= x_{1}T(\vec{e}_{1}) + \cdots + x_{n}T(\vec{e}_{n}) \\
&= \begin{bmatrix} T(\vec{e}_{1}) & \cdots & T(\vec{e}_{n}) \end{bmatrix} \begin{bmatrix} x_{1} \\ \vdots \\ x_{n} \end{bmatrix} \\
&= A\vec{x}
\end{align}
```

- Input : $B$-coords $[\vec{x}]_{B} \in R^{n}$
- Output : $C$-coords $[\vec{y}]_{C} \in R^{m}$
```math
\begin{cases}
\text{For standard matrix}\: T :\quad \vec{y} = T(\vec{x}) = A\vec{x} \\
\text{and coords}\: [\vec{x}]_{B}\: \text{in basis}\: B = \set{\vec{v}_{1}, \cdots, \vec{v}_{n}} \\
\text{and coords}\: [\vec{y}]_{C}\: \text{in basis}\: C = \set{\vec{u}_{1}, \cdots, \vec{u}_{m}},
\end{cases}
```
```math
\begin{align}
\vec{y} = U[\vec{y}]_{C} = T(\vec{x}) {} &= T(x_{b1}\vec{v}_{1} + \cdots + x_{bn}\vec{v}_{n}) \\
&= x_{b1}T(\vec{v}_{1}) + \cdots + x_{bn}T(\vec{v}_{n}) \\
&= \begin{bmatrix} T(\vec{v}_{1}) & \cdots & T(\vec{v}_{n}) \end{bmatrix} \begin{bmatrix} x_{b1} \\ \vdots \\ x_{bn} \end{bmatrix} \\
&= \begin{bmatrix} A\vec{v}_{1} & \cdots & A\vec{v}_{n} \end{bmatrix} [\vec{x}]_{B} \\
&= AV[\vec{x}]_{B}
\end{align}
```
```math
\begin{align}
\therefore\quad [\vec{y}]_{C} = (U^{-1}AV)[\vec{x}]_{B} \quad\leftrightarrow\quad [T(\vec{x})]_{C} = [T]_{C\leftarrow B}[\vec{x}]_{B} \\
\therefore\quad [T]_{C\leftarrow B} = U^{-1}AV
\end{align}
```
<br>

### ¶ Image Compression ¶

Represent the image <b>in a better basis so most information is captured</b> by few numbers.

Image compression step-by-step,
1. Original image = Matrix of pixel intensities
2. Choose a basis that captures patterns (not pixels)
3. Transform image into that basis
4. Keep only the most important coefficients
5. Reconstruct an approximation of the image

That basis is usually given by <b>SVD</b>.
```math
A = U\Sigma V^{*} = \sum_{i=1}^{r} \sigma_{i}\vec{u}_{i}\vec{v}_{i}^{*}
```
From SVD, keep only the biggest $k$ singular values.
```math
A_{k} = U_{k}\Sigma_{k}V_{k}^{*} = \sum_{i=1}^{k} \sigma_{i}\vec{u}_{i}\vec{v}_{i}^{*}
```

- Example :
```math
\text{With}\quad \sigma_{1} = 4, \sigma_{2} = 2, \sigma_{3} = 1,
```
```math
\begin{align}
\text{Rank-1}\:(k=1)\quad A_{1} {} &= \sigma_{1}\vec{u}_{1}\vec{v}_{1}^{*} \\
&= 4\vec{u}_{1}\vec{v}_{1}^{*} \quad\text{(most compressed)} \\\\
\text{Rank-2}\:(k=2)\quad A_{2} &= \sigma_{1}\vec{u}_{1}\vec{v}_{1}^{*} + \sigma_{2}\vec{u}_{2}\vec{v}_{2}^{*} \\
&= 4\vec{u}_{1}\vec{v}_{1}^{*} + 2\vec{u}_{2}\vec{v}_{2}^{*} \\\\
\text{Rank-3}\:(k=3)\quad A_{3} {} &= \sigma_{1}\vec{u}_{1}\vec{v}_{1}^{*} + \sigma_{2}\vec{u}_{2}\vec{v}_{2}^{*} + \sigma_{3}\vec{u}_{3}\vec{v}_{3}^{*} \\
&= 4\vec{u}_{1}\vec{v}_{1}^{*} + 2\vec{u}_{2}\vec{v}_{2}^{*} + 1\vec{u}_{3}\vec{v}_{3}^{*} \\
\end{align}
```
