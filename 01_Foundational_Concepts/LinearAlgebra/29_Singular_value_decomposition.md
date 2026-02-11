# 📚 Lecture 29: Singular value decomposition

### ¶ SVD ¶ <a href="https://en.wikipedia.org/wiki/Singular_value_decomposition">(Wikipedia)</a><br>

Let $U, V$ are <b>unitary (orthonormal)</b> matrices.
```math
\begin{align}
A\vec{v}_{i} {} &= \sigma_{i}\vec{u}_{i} \quad(\sigma\text{ : singular values}) \\\\
AV &= A \begin{bmatrix} \vec{v}_{1} & \cdots & \vec{v}_{r} & \vec{v}_{r+1} & \cdots & \vec{v}_{n} \end{bmatrix} \\
&= \begin{bmatrix} \vec{u}_{1} & \cdots & \vec{u}_{r} & \vec{u}_{r+1} & \cdots & \vec{u}_{m} \end{bmatrix} \: \text{diag}(\sigma_{1}, \cdots, \sigma_{r}, 0, \cdots) \\
&= U\Sigma
\end{align}
```
```math
\begin{align}
\therefore\: A = U\Sigma V^{*} = \sum_{i=1}^{r} \sigma_{i}\vec{u}_{i}\vec{v}_{i}^{*} \\
\Big(\underset{(m\times n)}A, \underset{(n\times n)}V, \underset{(m\times m)}U, \underset{(m\times n)}\Sigma\Big)
\end{align}
```
<br>

- $r =$ rank($A$) : The number of positive(=non-zero) singular values.
```math
\begin{cases} A\vec{v}_{i} = \sigma_{i}\vec{u}_{i} \quad(\text{for}\: i \le r) \\
A\vec{v}_{i} = 0\vec{u}_{i} = 0 \quad(\text{for}\: i > r) \end{cases}
```
<br>

$A^{T}A$ and $AA^{T}$ are <b>symmetric and positive semi-definite</b>.<br>
$\therefore\: \lambda_{i,A^{T}A}, \lambda_{i,AA^{T}} \ge 0$
```math
\begin{align}
A^{T}A {} &= (U\Sigma V^{T})^{T}(U\Sigma V^{T}) \\
&= (V\Sigma^{T}U^{T})(U\Sigma V^{T}) \\
&= V(\Sigma^{T}\Sigma)V^{T} = V\Lambda_{(A^{T}A)}V^{T} \\\\\\
AA^{T} &= (U\Sigma V^{T})(U\Sigma V^{T})^{T} \\
&= (U\Sigma V^{T})(V\Sigma^{T}U^{T}) \\
&= U(\Sigma\Sigma^{T})U^{T} = U\Lambda_{(AA^{T})}U^{T}
\end{align}
```
<p align="center">
→ $(\Sigma^{T}\Sigma, V)$ : (eigenvalues, eigenvectors) of $A^{T}A$<br>
→ $(\Sigma\Sigma^{T}, U)$ : (eigenvalues, eigenvectors) of $AA^{T}$</p>
<br>

$\therefore\: \Sigma^{T}\Sigma = \Lambda_{(A^{T}A)}$ and $\Sigma\Sigma^{T} = \Lambda_{(AA^{T})}$


```math
\begin{align}\begin{cases}
\Sigma^{T}\Sigma = \text{diag}(\sigma_{1}^{2}, \cdots, \sigma_{r}^{2}, \underbrace{0, \cdots, 0}_\text{n-r}) = \text{diag}(\lambda_{1}, \cdots, \lambda_{n}) = \Lambda_{A^{T}A} \\
\Sigma\Sigma^{T} = \text{diag}(\sigma_{1}^{2}, \cdots, \sigma_{r}^{2}, \underbrace{0, \cdots, 0}_\text{m-r}) = \text{diag}(\lambda_{1}, \cdots, \lambda_{m}) = \Lambda_{A^{T}A}
\end{cases}\end{align}
```
```math
\therefore\quad \lambda_{i} = \sigma_{i}^{2} \quad\leftrightarrow\quad \sigma_{i} = \sqrt{\lambda_{i}}
```
<p align="center">→ $A^{T}A$ and $AA^{T}$ have <b>same non-zero eigenvalues</b> $\lambda$.</p><br>

**○ $U, V$ and 4 Fundamental Subspaces of $A$**<br>
<b>SVD organizes all four fundamental subspaces simultaneously.</b><br>
This is one of the deepest reasons SVD is so powerful.<br>

- $V$ = [ONB(Row($A$)) | ONB(ker($A$))]<br>
- $U$ = [ONB(Col($A$)) | ONB(ker($A^{T}$))]<br>

| Symbols | 4 Fundamental Subspaces | Basis |
| :-----: | :----: | :----: |
| Row($A$) = Range($A^{T}$) | Row space of $A$ | First $r$ columns of $V$ |
| $\ker(A)$ = Null($A$) | Null space of $A$ | Last $(n-r)$ columns of $V$ |
| Col($A$) = Range($A$) | Column space of $A$ | First $r$ columns of $U$ |
| $\ker(A^{T})$ = Null($A^{T}$) | Null space of $A^{T}$ | Last $(m-r)$ columns of $U$ |
<br>

1) $\ker(A)$ : Null space of $A$
```math
\text{For } i > r ,\quad A^{T}A\vec{v}_{i} = \vec{0} \quad\leftrightarrow\quad \vec{v}_{i} \in \ker(A^{T}A) \quad\leftrightarrow\quad \vec{v}_{i} \in \ker(A)
```
```math
\therefore\quad \ker(A) = \text{span}\set{\vec{v}_{r+1},\cdots,\vec{v}_{n}}
```
```math
\begin{align}
\text{(Proof) For any } \vec{x},\quad \vec{x} \in \ker(A^{T}A) \quad\leftrightarrow\quad A^{T}A\vec{x} = \vec{0} \quad\leftrightarrow\quad \vec{x}^{T}A^{T}A\vec{x} = 0 \\
\leftrightarrow\quad \lVert A\vec{x} \rVert^{2} = 0 \quad\leftrightarrow\quad A\vec{x} = \vec{0} \quad\leftrightarrow\quad \vec{x} \in \ker(A) \\\\
\therefore\quad \vec{x} \in \ker(A^{T}A) \quad\leftrightarrow\quad \vec{x} \in \ker(A)
\end{align}
```

2) $\ker(A^{T})$
```math
\text{For } i > r ,\quad AA^{T}\vec{u}_{i} = \vec{0} \quad\leftrightarrow\quad \vec{u}_{i} \in \ker(AA^{T}) \quad\leftrightarrow\quad \vec{u}_{i} \in \ker(A^{T})
```
```math
\therefore\quad \ker(A^{T}) = \text{span}\set{\vec{u}_{r+1},\cdots,\vec{u}_{m}}
```
<p align="center">(Proof) Same idea as the case of $\ker(A)$</p>

3) Row($A$) = Range($A^{T}$)<br>
- Since $V$ is orthogonal,
```math
\text{span}\set{\vec{v}_{1},\cdots,\vec{v}_{r}} = (\text{span}\set{\vec{v}_{r+1},\cdots,\vec{v}_{n}})^{\perp} = (\ker(A))^{\perp}
```
- Fundamental theorem of linear algebra says,
```math
\begin{align}
(\ker(A))^{\perp} = \text{Range}(A^{T}) = \text{Row}(A) \\\\
\therefore\quad \text{Row}(A) = \text{span}\set{\vec{v}_{1},\cdots,\vec{v}_{r}}
\end{align}
```

4) Col($A$) = Range($A$)<br>
- Since $U$ is orthogonal,
```math
\text{span}\set{\vec{u}_{1},\cdots,\vec{u}_{r}} = (\text{span}\set{\vec{u}_{r+1},\cdots,\vec{u}_{m}})^{\perp} = (\ker(A^{T}))^{\perp} = \text{Range}(A) = \text{Col}(A)
```
```math
\therefore\quad \text{Col}(A) = \text{span}\set{\vec{u}_{1},\cdots,\vec{u}_{r}}
```
<br><br>

**○ If $A$ is full-column-rank, every $\sigma_{i} > 0$**<br>
1) Full-column-rank<br>
If $A$ is <b>full-column-rank</b>, $A^{T}A$ is <b>positive definte</b>.
```math
\begin{align}
\text{As null space of }A = \set{\vec{0}},\quad A\vec{x} \not= \vec{0} \quad\text{for every} \:\vec{x} \not= \vec{0} \\
\therefore\quad \vec{x}^{T}(A^{T}A)\vec{x} = \lVert A\vec{x} \rVert^{2} > 0 \quad\text{for every} \:\vec{x} \not= \vec{0} \\
\text{→ Positive definite}
\end{align}
```
```math
\therefore\quad \lambda_{i} > 0 \quad\rightarrow\quad \sigma_{i} > 0
```

2) Rank-deficient<br>
```math
\text{Example :}\quad A = \begin{bmatrix} 1 & 0 \\ 0 & 0 \end{bmatrix},\quad\text{then}\quad A^{T}A = \begin{bmatrix} 1 & 0 \\ 0 & 0 \end{bmatrix}
```
<p align="center">→ $(\lambda_{1}, \lambda_{2}) = (1, 0)$<br>
→ $(\sigma_{1}, \sigma_{2}) = (1, 0)$</p><br>


**○ Geometric meaning**<br>
Singular values are the <b>stretch factors</b> of $A$.
```math
\begin{align}
\lVert A\vec{v}_{i} \rVert^{2} = \vec{v}^{T}_{i}(A^{T}A\vec{v}_{i}) = \vec{v}^{T}_{i}(\lambda_{i}\vec{v}_{i}) = \lambda_{i}\lVert\vec{v}_{i}\rVert^{2} \\
\text{If}\quad \lVert\vec{v}_{i}\rVert^{2} = 1 ,\quad \lVert A\vec{v}_{i} \rVert^{2} = \lambda_{i} = \sigma_{i}^{2} \\
\therefore\quad \lVert A\vec{v}_{i} \rVert = \sqrt{\lambda_{i}} = \sigma_{i}
\end{align}
```
- If $\sigma_{i} = 0$ : that direction is collapsed to zero.
- If $\sigma_{i} > 0$ : that direction is stretched (or shrunk, but not killed).
<br>
