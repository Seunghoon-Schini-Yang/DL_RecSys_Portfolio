### ¶ Gauss-Jordan Elimination ¶ (from Lecture_03)

- Set $\quad AA^{-1} = I$
```math
\begin{align}
\begin{bmatrix} 1 & 3 \\ 2 & 7 \end{bmatrix}
\begin{bmatrix} c & d \\ a & b \end{bmatrix}
= \begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix}
\quad (\quad AA^{-1} = I \quad)
\end{align}
```

- Do elimination with $\quad E_{i}$
```math
\begin{align}
\begin{bmatrix} A & I \end{bmatrix} \quad→\quad \begin{bmatrix} 1 & 3 \\ 2 & 7 \end{bmatrix}\begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix} \\
E_{1}\begin{bmatrix} A & I \end{bmatrix} = \begin{bmatrix} E_{1}A & E_{1}I \end{bmatrix} \quad→\quad
\begin{bmatrix} 1 & 3 \\ 0 & 1 \end{bmatrix}\begin{bmatrix} 1 & 0 \\ -2 & 1 \end{bmatrix} \quad\text{(Elimination)} \\
E_{2}\begin{bmatrix} E_{1}A & E_{1}I \end{bmatrix}
= \begin{bmatrix} E_{2}E_{1}A & E_{2}E_{1}I \end{bmatrix}
\quad→\quad \begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix}
\begin{bmatrix} 7 & -3 \\ -2 & 1 \end{bmatrix} \quad\text{(Back substitution)}
\end{align}
```

- So, $\quad E = A^{-1}$
```math
\begin{align}
\begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix}\begin{bmatrix} 7 & -3 \\ -2 & 1 \end{bmatrix}
= \begin{bmatrix} EA & EI \end{bmatrix} = \begin{bmatrix} I & E \end{bmatrix}\quad
(\quad\text{where}\quad E = E_{2}E_{1} \quad) \\
\text{So,}\quad EA = I \quad↔\quad E = A^{-1}
\end{align}
```
