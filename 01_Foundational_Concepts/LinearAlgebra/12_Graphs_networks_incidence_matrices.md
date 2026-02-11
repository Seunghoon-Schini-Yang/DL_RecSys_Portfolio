# 📚 Lecture 12: Graphs, networks, incidence matrices

**○ Directed Graph**<br>

- $(m, n)$ = (# of edges, # of nodes)

```math
\begin{align*}
\begin{matrix} \text{node 1} & \text{node 2} & \text{node 3} & \text{node 4} \end{matrix} \\
\text{Incidence Matrix :}\quad A = \begin{bmatrix} -1 & 1 & 0 & 0 \\ 0 & -1 & 1 & 0 \\ -1 & 0 & 1 & 0 \\ -1 & 0 & 0 & 1 \\ 0 & 0 & -1 & 1 \end{bmatrix}
\begin{matrix} \text{edge 1 (node 1 to 2)} \\ \text{edge 2 (node 2 to 3)} \\ \text{edge 3 (node 1 to 3)} \\ \text{edge 4 (node 1 to 4)} \\ \text{edge 5 (node 3 to 4)} \end{matrix}
\end{align*}
```

The Incidence Matrix is a very <b>sparse</b> matrix.<br>
Every row has only two non-zero values.<br>

- Loops (<b>linearly dependent</b>)<br>
① edge 3 (1 → 3) = edge 1 (1 → 2) + edge 2 (2 → 3)<br>
② edge 4 (1 → 4) = edge 1 (1 → 2) + edge 2 (2 → 3) + edge 5 (3 → 4)<br>

- $N(A)$ : Null Space of $A$

```math
\begin{align*}
Ax = \begin{bmatrix} -1 & 1 & 0 & 0 \\ 0 & -1 & 1 & 0 \\ -1 & 0 & 1 & 0 \\ -1 & 0 & 0 & 1 \\ 0 & 0 & -1 & 1 \end{bmatrix} \begin{bmatrix} x_{1} \\ x_{2} \\ x_{3} \\ x{4} \end{bmatrix} = \begin{bmatrix} x_{2}-x_{1} \\ x_{3}-x_{2} \\ x_{3}-x_{1} \\ x_{4}-x_{1} \\ x_{4}-x_{3} \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \\ 0 \\ 0 \\ 0 \end{bmatrix} \\\\
\begin{cases}
x = \begin{bmatrix} x_{1} \\ x_{2} \\ x_{3} \\ x_{4} \end{bmatrix} \quad\text{: Potentials at nodes} \\
Ax = \begin{bmatrix} x_{2}-x_{1} \\ x_{3}-x_{2} \\ x_{3}-x_{1} \\ x_{4}-x_{1} \\ x_{4}-x_{3} \end{bmatrix} \quad\text{: Potential differences}
\end{cases}
\end{align*}
```

```math
\begin{align*}
x = c \begin{bmatrix} 1 \\ 1 \\ 1 \\ 1 \end{bmatrix},\quad dim(N(A)) = 1 \\\\
rank(A) = \Gamma = dim(C(A)) = n - dim(N(A)) = 4 - 1 = 3
\end{align*}
```

<b>Potential differences</b> make something move between nodes.<br>
Nothing will flow in this network with all nodes having same potential. $(x_{1} = x_{2} = x_{3} = x_{4} = 1)$<br>

To avoid this, we can fix one of the potentials to zero.<br>
Ex) $(x_{4} = 0)$

```math
\begin{align*}
\text{For}\quad \underset{(n \times m)}{A^{T}},  \underset{(m \times 1)}{y} \\
A^{T}y = \begin{bmatrix} -1 & 0 & -1 & -1 & 0 \\ 1 & -1 & 0 & 0 & 0 \\ 0 & 1 & 1 & 0 & -1 \\ 0 & 0 & 0 & 1 & 1 \end{bmatrix} \begin{bmatrix} y_{1} \\ y_{2} \\ y_{3} \\ y_{4} \\ y_{5} \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \\ 0 \\ 0 \end{bmatrix} \\
dim(N(A^{T})) = m - \Gamma = 5 - 3 = 2
\end{align*}
```

- Kirchoff's Current law

```math
\begin{align*}
Ax = \begin{bmatrix} x_{2}-x_{1} \\ x_{3}-x_{2} \\ x_{3}-x_{1} \\ x_{4}-x_{1} \\ x_{4}-x_{3} \end{bmatrix} \quad\text{: (Voltage) Potential Differenes on the edges between nodes} \\
y = \begin{bmatrix} y_{1} \\ y_{2} \\ y_{3} \\ y_{4} \\ y_{5} \end{bmatrix} \quad\text{: (Current) Currents on the edges}
\end{align*}
```

```math
\begin{align*}
A^{T}y = \begin{bmatrix} -1 & 0 & -1 & -1 & 0 \\ 1 & -1 & 0 & 0 & 0 \\ 0 & 1 & 1 & 0 & -1 \\ 0 & 0 & 0 & 1 & 1 \end{bmatrix} \begin{bmatrix} y_{1} \\ y_{2} \\ y_{3} \\ y_{4} \\ y_{5} \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \\ 0 \\ 0 \end{bmatrix} \\
\begin{cases}
-y_{1}-y_{3}-y_{4} = 0 \quad\text{(Node 1 : Currents coming out add to zero.)} \\
y_{1}-y_{2} = 0 \quad\text{(Node 2 : Current in equals current out.)} \\
y_{2}+y_{3}-y_{5} = 0 \quad\text{(Node 3 : Currents coming in and going out has to balance.)} \\
y_{4}+y_{5} = 0 \quad\text{(Node 4 : Currents coming in add to zero.)}
\end{cases}
\end{align*}
```
<br>

To find basis for $N(A^{T})$, Take a look at each loop.

```math
\begin{align*}
\text{Loop 1 :}\quad \begin{bmatrix} 1 \\ 1 \\ -1 \\ 0 \\ 0 \end{bmatrix}, \quad
\text{Loop 2 :}\quad \begin{bmatrix} 0 \\ 0 \\ 1 \\ -1 \\ 1 \end{bmatrix} \\\\
\text{Basis for  } N(A^{T}) \text{  :} \quad y = c_{1} \begin{bmatrix} 1 \\ 1 \\ -1 \\ 0 \\ 0 \end{bmatrix} + c_{2} \begin{bmatrix} 0 \\ 0 \\ 1 \\ -1 \\ 1 \end{bmatrix}
\end{align*}
```
<br>

All the dependencies come from loops.<br>
Edges (1, 2, 4) have no loop.<br>
That's why they can be pivot columns.<br>

- Euler's Formula<br>
There are at least $n-1$ edges in network having $n$ nodes.<br>
(Any nodes should be reached to any other nodes through the edges.)<br>
A network with $n-1$ edges have no loop (= Tree).<br>
Adding a new edge into this network makes a new loop.<br>

```math
\text{That's why}\quad dim(N(A)) = 1 \quad\text{satifies.}
```
<br>

```math
\begin{align*}
\begin{cases}
\Gamma = n - dim(N(A)) = m - dim(N(A^{T})) \\
\text{(num of nodes) - 1 = (num of edges) - (num of loops)}
\end{cases} \\
\text{Euler's formula : (num of nodes) - (num of edges) + (num of loops) = 1}
\end{align*}
```
<br>

- Basic equation of applied math

```math
\begin{align*}
\begin{cases}
e = Ax \quad\text{(Potential Differencces)} \\
y = Ce \quad\text{(Currunces come from potential differences)} \\
A^{T}y = 0 \quad\text{(Currences satisfies Kirchoff's Current Low)}
\end{cases} \\\\\\
A^{T}CAx = f \quad (f \text{  : Current sources}) \\
(A^{T}CA \quad\text{: Symmetric})
\end{align*}
```
<br>

**○ Tree : Graph with no loops**
