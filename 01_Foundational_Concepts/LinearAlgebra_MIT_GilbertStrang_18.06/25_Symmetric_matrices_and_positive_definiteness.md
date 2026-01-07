# 📚 Lecture 25: Symmetric matrices and positive definiteness

### ¶ Symmetric matrices $(A = A^{T})$ ¶

① If all entries of Symmetric matrix are <b>real</b>, then all the eigenvalues are also <b>real</b>.<br>
② The eigenvectors are <b>perpendicular</b> to each other.

- Why real eigenvalues?<br>
From $A\vec{x} = \lambda\vec{x}$,

```math
\begin{align}
\overline{A}\overline{x} = \overline{\lambda}\overline{x} \\
A\overline{x} = \overline{\lambda}\overline{x} \quad(A = \overline{A} \quad\because\: A \:\text{is a real matrix.}) \\
\text{→}\: (\overline{\lambda}, \overline{x}) \:\text{are also eigenvalues and eigenvectors of}\: A \\\\\\

\overline{x}^{T}A^{T} = \overline{\lambda}\overline{x}^{T} \\
\overline{x}^{T}A^{T}x = \overline{\lambda}\overline{x}^{T}x \\
\overline{x}^{T}Ax = \overline{\lambda}\overline{x}^{T}x \quad(\because\: A \:\text{is symmetric.}) \\\\\\

\lambda\overline{x}^{T}x = \overline{\lambda}\overline{x}^{T}x \\
\therefore\: \lambda = \overline{\lambda} \quad(\rightarrow\: \lambda\: \text{is real.}) \\\\\\

\overline{x}^{T}x = \begin{bmatrix} \overline{x}_{1} & \overline{x}_{2} & \cdots & \overline{x}_{n} \end{bmatrix} \begin{bmatrix} x_{1} \\ x_{2} \\ \vdots \\ x_{n} \end{bmatrix} = \overline{x}_{1}x_{1} + \overline{x}_{2}x_{2} + \cdots + \overline{x}_{n}x_{n} \\
\\
(a+ib)(a-ib) = a^{2}+b^{2} \\
\therefore\: \overline{x}^{T}x \:\text{is real.}
\end{align}
```
<br>

- If $A$ is an Hermitian matrix $(A = \overline{A}^{T})$,
```math
\begin{align}
\overline{A}\overline{x} = \overline{\lambda}\overline{x} \\
\overline{x}^{T}\overline{A}^{T} = \overline{\lambda}\overline{x}^{T} \\
\overline{x}^{T}\overline{A}^{T}x = \overline{\lambda}\overline{x}^{T}x \\\\\\

\overline{x}^{T}Ax = \overline{\lambda}\overline{x}^{T}x \quad(\because\: A \:\text{is Hermitian.}) \\
\lambda\overline{x}^{T}x = \overline{\lambda}\overline{x}^{T}x \\
\therefore\: \lambda = \overline{\lambda} \quad(\rightarrow\: \lambda\: \text{is real.}) \\
\end{align}
```
<br>

**○ Spectral theorem** <a href="https://en.wikipedia.org/wiki/Spectral_theorem">(Wikipedia)</a><br>
: If matrix $A$ is <b>Hermitian</b> on $V$, then there exists an <b>orthonormal basis</b> of $V$ consisting of eigenvectors of $A$. Each eigenvalue of $A$ is <b>real</b>.

Usual case : $A = S\Lambda S^{-1}$<br>
Symmetric case : $A = Q\Lambda Q^{-1} = Q\Lambda Q^{T}$<br>
$\therefore\: (Q\Lambda Q^{T})^{T} = Q\Lambda Q^{T}$ (→ Symmetric)<br>

- Every symmetric matrix is a combination of perpendicular projection matrices.
```math
\begin{align}
A = Q\Lambda Q^{T} {} &= 
\begin{bmatrix} \vec{q}_{1} & \vec{q}_{2} & \cdots & \vec{q}_{n} \end{bmatrix} \begin{bmatrix} \lambda_{1} & \cdots & 0 \\ \vdots & \ddots & \vdots \\ 0 & \cdots & \lambda_{n} \end{bmatrix} \begin{bmatrix} \vec{q}^{T}_{1} \\ \vec{q}^{T}_{2} \\ \vdots \\ \vec{q}^{T}_{n} \end{bmatrix} \\
&= \lambda_{1}\vec{q}_{1}\vec{q}^{T}_{1} + \cdots + \lambda_{n}\vec{q}_{n}\vec{q}^{T}_{n}
\end{align}
```
<br><br>


### ¶ Positive-definite matrix ¶ <a href="https://en.wikipedia.org/wiki/Definite_matrix">(Wikipedia)</a>

- For symmetric matrices,<br>
the signs of pivots are the same as the signs of $\lambda$'s<br>
('# of positive pivots = # of positive $\lambda$'s)

- Definition :<br>
A Hermitian matrix $M$ (that is, a complex matrix equal to its conjugate transpose) is <b>positive-definite</b> if the real number 
$\vec{z}^{H}M\vec{z}$ is positive for every nonzero complex column vector $\vec{z}$, where $\vec{z}^{H}$ denotes the conjugate transpose of $\vec{z}$.

```math
M \:\text{positive-definite} \quad\leftrightarrow\quad \vec{z}^{H}M\vec{z} > 0 \:\text{for all}\: \vec{z} \in C^{n} \setminus \set{\vec{0}}
```

- Positive-definite matrices are<br>

    1. All the eigenvalues are positive.
    2. All the pivots are positive.
    3. All the sub-determinants are positive.

