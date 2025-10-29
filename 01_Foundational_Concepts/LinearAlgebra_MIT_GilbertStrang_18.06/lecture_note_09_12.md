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