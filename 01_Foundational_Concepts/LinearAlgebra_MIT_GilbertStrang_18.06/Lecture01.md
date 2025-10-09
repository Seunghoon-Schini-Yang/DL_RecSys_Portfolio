# 📚 Lecture 1: The geometry of linear equations

```math
\mathbf{A} = \begin{bmatrix} 2 & -1 & 0 \\ -1 & 2 & -1 \\ 0 & -3 & 4\end{bmatrix}, \quad \mathbf{b} = \begin{bmatrix} 1 \\ 1 \\ -3 \end{bmatrix}
```

**Row Picture**
* Three planes meet in a point, and that's the solution.\
(Unless parallels or something exist.)
```math
\begin{eqnarray}
2\mathbf{x} - \mathbf{y} = 1 \\
-\mathbf{x} + 2\mathbf{y} -\mathbf{z} = 1 \\
-3\mathbf{y} + 4\mathbf{z} = -3
\end{eqnarray}
```

**Column Picture**
* Linear combination of three vectors.

```math
\mathbf{x} \begin{bmatrix} 2 \\ -1 \\ 0\end{bmatrix} + \mathbf{y} \begin{bmatrix} -1 \\ 2 \\ -3\end{bmatrix} + \mathbf{z} \begin{bmatrix} 0 \\ -1 \\ 4\end{bmatrix} = \begin{bmatrix} 1 \\ 1 \\ -3\end{bmatrix}
```

### 🧩 Key Points
💡 Can I solve $\mathbf{A}\mathbf{x} = \mathbf{b}$ for every $\mathbf{b}$ ?\
💡 Do the linear combinations of the columns fill 3-D space?
