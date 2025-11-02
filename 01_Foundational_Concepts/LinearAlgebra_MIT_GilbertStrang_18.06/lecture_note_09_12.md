# 📚 Lecture 9: Independence, basis, and dimension

- Suppose $A$ is a $m \times n$ matrix with m < n. (More unknowns than equations.)<br>
Then there are non-zero solutions to Ax = 0.<br>
Reason : There will be free variables (at least one).<br>

**○ Independence**

- Vectors $x_{1}, x_{2}, \cdots , x_{n}$ are indepent,<br>
if no combination gives zero vector (except for the zero combination).

```math
c_{1}x_{1} + c_{2}x_{2} + \cdots + c_{n}x_{n} \not= 0 \quad ( \text{except for  } c_{1} = c_{2} = \cdots = c_{n} = 0 )
```

- If any $x_{i} (\in x)$ is zero vector, they are not independent.<br>

- when $v_{1}, v_{2}, \cdots , v_{n}$ are columns of $A$, <br>
they are independent if null space of $A$ is zero vector.<br>
($N(A) = 0$, no free variables)<br>

- They are dependent if $Ac = 0$ for some non-zero vector $c$.<br>
($N(A) \not= 0$, there will be free variables)<br><br>

**○ Span**

- Vectors $v_{1}, v_{2}, \cdots , v_{n}$ <b>span</b> a space means,<br>
The space consists of all combinations of these vectors.<br><br>

**○ Basis**

- Basis for a vector space is a sequence of vectors $v_{1}, v_{2}, \cdots , v_{n}$ with 2 properties below.<br>

1. They are <b>independent</b>.
2. They <b>span</b> the space.

- For $R^{3}$ space,<br>
Example 1)<br>
They are <b>independent</b> and <b>span</b> the $R^{3}$ space.

```math
\text{One of basis is}\quad
\begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix}, \begin{bmatrix} 0 \\ 1 \\ 0 \end{bmatrix}, \begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix}
```
<br>

Example 2)<br>
They are <b>independent</b>, but <b>do not span</b> the $R^{3}$ space.<br>
They can't be a basis of $R^{3}$.

```math
\begin{bmatrix} 1 \\ 1 \\ 2 \end{bmatrix}, \begin{bmatrix} 2 \\ 2 \\ 5 \end{bmatrix}
```

- n vectors in $R^{n}$ space give basis if the $(n \times n)$ matrix is <b>invertible</b>.<br><br>

**○ Dimension**

Every basis for the space has the same number of vectors,<br>
and this number is the <b>dimension</b> of the space.

- (dimension of $C(A)$ ) = (# of pivot variables) = (rank of $A$)
- (dimension of $N(A)$ ) = (# of free variables)


<br><br><br>

# 📚 Lecture 10: The four fundamental subspaces

**○ 4 Subspaces**<br>
$C(A)$ : Column space<br>
$N(A)$ : Null space<br>
$C(A^{T})$ : Row space (All combs of rows of $A$ = All combs of columns of $A^{T}$)<br>
$N(A^{T})$ : Null space of $A^{T}$ (Left Null space)<br>

- $A$ is $(m \times n)$.<br>
$C(A)$ is in $R^{m}$.<br>
$N(A)$ is in $R^{n}$.<br>
$C(A^{T})$ is in $R^{n}$.<br>
$N(A^{T})$ is in $R^{m}$.<br>

- Dimension of row space and columns space are equal.<br>
$dim(C(A)) = dim(C(A^{T}))$<br>

- $R^{n}$ : Row space, Null space<br>
$dim(C(A)) = \Gamma =$ (Num of pivot variables)<br>
$dim(N(A^{T})) = m - \Gamma$<br>
$m = dim(C(A)) + dim(N(A^{T}))$<br>

- $R^{m}$ : Column space, Left Null space<br>
$dim(C(A^{T})) = dim(C(A)) = \Gamma$<br>
$dim(N(A)) = n - \Gamma =$ (Num of free variables)<br>
$n = dim(C(A^{T})) + dim(N(A))$<br>


**○ Null space of $A^{T}$**

```math
\begin{align*}
\underset{(m\times m)}E[\underset{(m\times n)}A \underset{(m\times m)}I] = [\underset{(m\times n)}R \underset{(m\times m)}E] \\
→ EA = R
\end{align*}
```
If $A$ is <b>square and invertible</b>, $EA = I$.

- Example)
```math
\begin{align*}
A = \begin{bmatrix} 1 & 2 & 3 & 1 \\ 1 & 1 & 2 & 1 \\ 1 & 2 & 3 & 1 \end{bmatrix} \\\\
\text{Augmented Matrix :}\quad \begin{bmatrix} A & I \end{bmatrix}
= \begin{bmatrix} 1 & 2 & 3 & 1 \\ 1 & 1 & 2 & 1 \\ 1 & 2 & 3 & 1 \end{bmatrix}
\begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{bmatrix} \\
→ \text{Augmented Matrix :}\quad \begin{bmatrix} R & E \end{bmatrix}
= \begin{bmatrix} 1 & 0 & 1 & 1 \\ 0 & 1 & 1 & 0 \\ 0 & 0 & 0 & 0 \end{bmatrix}
\begin{bmatrix} -1 & 2 & 0 \\ 1 & -1 & 0 \\ -1 & 0 & 1 \end{bmatrix} \\\\
EA = R \\
→ \begin{bmatrix} -1 & 2 & 0 \\ 1 & -1 & 0 \\ -1 & 0 & 1 \end{bmatrix} \begin{bmatrix} 1 & 2 & 3 & 1 \\ 1 & 1 & 2 & 1 \\ 1 & 2 & 3 & 1 \end{bmatrix} = \begin{bmatrix} 1 & 0 & 1 & 1 \\ 0 & 1 & 1 & 0 \\ 0 & 0 & 0 & 0 \end{bmatrix}
\end{align*}
```
$E$ is on the <b>left</b> side of $A$. (Tht's why it's called "Left Null space")<br>
The linear combination of the "third row of $E$" and the "rows of $A$" becomes the "zero row of R".<br>
(Rows of $A$ = Columns of $A^{T}$)<br>
It means that the third row of $E$ is a special solution to $A^{T}x = 0$.

```math
N(A^{T}) = c\begin{bmatrix} -1 \\ 0 \\ 1 \end{bmatrix} \\
,\quad dim(N(A^{T})) = 1
```

<br><br><br>

# 📚 Lecture 11: Matrix spaces; rank 1; small world graphs

**○ Matrix spaces**<br>
Space $M$ = All $(3 \times 3)$ matrices.
```math
\begin{align*}
\text{One of basis for  } M : \begin{bmatrix} 1 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 0 \end{bmatrix}, \begin{bmatrix} 0 & 1 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 0 \end{bmatrix}, \begin{bmatrix} 0 & 0 & 1 \\ 0 & 0 & 0 \\ 0 & 0 & 0 \end{bmatrix}, \cdots, \begin{bmatrix} 0 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 1 & 0 \end{bmatrix}, \begin{bmatrix} 0 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 1 \end{bmatrix} \\\\
dim(M) = 9
\end{align*}
```

- Subspace $S$ = All $(3 \times 3)$ <b>sysmmetric</b> matrices.<br>
$dim(S) = 6$<br>
- Subspace $U$ = All $(3 \times 3)$ <b>upper triangular</b> matrices.<br>
$dim(U) = 6$<br>
- $S \cap U$ = $D$ = All $(3 \times 3)$ <b>diagonal</b> matrices.<br>
$dim(S \cap U) = dim(D) = 3$<br>
- $S + U$ = (Any element of $S$) + (Any element of $U$) = All $(3 \times 3)$ matrices = $M$<br><br>

- $dim(S \cap U) + dim(S + U) = 3 + 9 = 12 = 6 + 6 = dim(S) + dim(U)$<br><br>

**○ Linear Differential Equation**<br>
```math
\begin{align*}
\frac{d^{2}y}{dx^{2}} + y = 0 \\\\
y = c_{1}cos(x) + c_{2}sin(x) \\
\begin{cases}
\text{Basis :} \quad cos(x), sin(x) \\
\text{Dimension :} \quad 2
\end{cases}
\end{align*}
```
<br>

**○ Rank 1 matrix**
- Every Rank $1$ marix $A$ has the form of <b>some column times some row</b>.
```math
A = uv^{T} =  \begin{bmatrix} u_{1} \\ u_{2} \\ \vdots \\ u{_m} \end{bmatrix} \begin{bmatrix} v_{1} & v_{2} & \cdots & v_{n} \end{bmatrix}
```

Example)
```math
\text{(Rank 1 matrix)}\quad A = \begin{bmatrix} 1 & 4 & 5 \\ 2 & 8 & 10 \end{bmatrix} = \begin{bmatrix} 1 \\ 2 \end{bmatrix}\begin{bmatrix} 1 & 4 & 5 \end{bmatrix} = uv^{T}
```

- Rank 1 matrices are like the building blocks for all matrices.<br>
Break matrix $A$ down as a combination of $\Gamma$ matrices of rank $1$.

```math
A = u_{1}v_{1}^{T} + u_{2}v_{2}^{T} + \cdots + u_{\Gamma}v_{\Gamma}^{T} = \sum_{i=1}^{\Gamma} u_{i}v_{i}^{T}
```

Example) $A$ : $(5 \times 17)$ matrix of rank $4$.<br>

```math
A = u_{1}v_{1}^{T} + u_{2}v_{2}^{T} + u_{3}v_{3}^{T} + u_{4}v_{4}^{T} = \sum_{i=1}^{4} u_{i}v_{i}^{T}
```
<br>

**○ Subspaces**<br>

Question 1)
- Does $(4 \times 4)$ matrices of rank $3$ form a subspace?<br>

```math
\begin{align*}
A = \begin{bmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & 0 \end{bmatrix},\quad B = \begin{bmatrix} 0 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & 1 \end{bmatrix} \\
A + B = \begin{bmatrix} 1 & 0 & 0 & 0 \\ 0 & 2 & 0 & 0 \\ 0 & 0 & 2 & 0 \\ 0 & 0 & 0 & 1 \end{bmatrix} \\\\
\begin{cases}
rank(A) = rank(B) = 3 \\
rank(A+B) = 4 \not= 3 = rank(A) = rank(B)
\end{cases} \\\\
(4 \times 4) \text{  matrices of rank 3 do not form a subspace.}
\end{align*}
```
<br>

Question 2)

```math
\text{Subspace  } S \text{  : All  } v = \begin{bmatrix} v_{1} \\ v_{2} \\ v_{3} \\ v_{4} \end{bmatrix} \in R^{4} \text{  with  } (v_{1} + v_{2} + v_{3} + v_{4} = 0)
```

- What's the dimentsion of $S$?
- What's the basis for $S$?

```math
\begin{align*}
Av = \begin{bmatrix} 1 & 1 & 1 & 1 \end{bmatrix} \begin{bmatrix} v_{1} \\ v_{2} \\ v_{3} \\ v_{4} \end{bmatrix} = 0 \\\\\\
\begin{cases}
dim(C(A)) = Rank(A) = \Gamma = 1 \\
dim(N(A)) = dim(S) = n - \Gamma = 4 - 1 = 3 \\
dim(C(A^{T})) = \Gamma = 1 \\
dim(N(A^{T})) = m - \Gamma = 1 - 1 = 0
\end{cases} \\\\\\
\text{One of basis for  } S : \quad \begin{bmatrix} -1 \\ 1 \\ 0 \\ 0 \end{bmatrix}, \begin{bmatrix} -1 \\ 0 \\ 1 \\ 0 \end{bmatrix}, \begin{bmatrix} -1 \\ 0 \\ 0 \\ 1 \end{bmatrix}
\end{align*}
```
<br>

**○ Small World Graphs**<br>
 Graph = {nodes, edges}


