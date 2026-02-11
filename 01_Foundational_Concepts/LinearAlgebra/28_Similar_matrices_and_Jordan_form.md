# 📚 Lecture 28: Similar matrices and Jordan form

### ¶ Similar matrices ¶

$(n \times n)$ matrices $A$ and $B$ are <b>similar</b> means
- for some $M$, $B = M^{-1}AM$

Example :
- $S^{-1}AS = \Lambda$ : $A$ is similar to $\Lambda$.

<b>Similar matrices have same eigenvalues!</b> (and same # of eigenvectors.)<br>
For $B = M^{-1}AM$,

```math
\begin{align}
A\vec{x} = \lambda\vec{x} \\
A(MM^{-1})\vec{x} = \lambda\vec{x} \\
(M^{-1}AM)M^{-1}\vec{x} = \lambda M^{-1}\vec{x} \\
B(M^{-1}\vec{x}) = \lambda (M^{-1}\vec{x})
\end{align}
```

$\therefore$ eigenvalues of $A$ and $B$ are same<br>
and (eigenvectors of $B$) = $M^{-1}\vec{x}$<br>
<br>

**○ Jordan form** <a href="https://en.wikipedia.org/wiki/Jordan_normal_form">(Wikipedia)</a><br>
Every square matrix $A$ is similar to a <b>Jordan matrix</b> $J$.

GOOD CASE : None of eigenvalues are repeated.
```math
M^{-1}AM = J \quad\leftrightarrow\quad S^{-1}AS = \Lambda \quad\text{(diagonalizable)}
```
<br>

BAD CASE : $\lambda_{1} = \lambda_{2} = 4$ (repeated eigevalues)
- Small one family
```math
\begin{align}
\begin{bmatrix} 4 & 0 \\ 0 & 4 \end{bmatrix} \quad\rightarrow\quad S = \begin{bmatrix} \vec{x}_{1} & \vec{x}_{2} \end{bmatrix} = \begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix} \quad\text{(diagonalizable)} \\
M^{-1}\begin{bmatrix} 4 & 0 \\ 0 & 4 \end{bmatrix}M = 4I(M^{-1}M) =  \begin{bmatrix} 4 & 0 \\ 0 & 4 \end{bmatrix}
\end{align}
```
- Big family includes<br>
```math
\begin{align}
\text{Jordan form : }J = \begin{bmatrix} \lambda & 1 \\ 0 & \lambda \end{bmatrix} = \begin{bmatrix} 4 & 1 \\ 0 & 4 \end{bmatrix} \quad\text{(not diagonalizable)}\\
\text{More members of family : } \begin{bmatrix} 5 & 1 \\ -1 & 3 \end{bmatrix}, \begin{bmatrix} 4 & 0 \\ 17 & 4 \end{bmatrix},\cdots \quad\text{(trace = 8 and det = 16)} \\\\
\text{example :}\quad M^{-1}\begin{bmatrix} 5 & 1 \\ -1 & 3 \end{bmatrix}M = \begin{bmatrix} 4 & 1 \\ 0 & 4 \end{bmatrix} = J
\end{align}
```
