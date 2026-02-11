# 📚 Lecture 9: Independence, basis, and dimension

**○ Independence**

- Vectors $\vec{x}_{1}, \vec{x}_{2}, \cdots , \vec{x}_{n}$ are <b>independent</b>,<br>
if no combination gives zero vector (except for the zero combination).

```math
c_{1}\vec{x}_{1} + c_{2}\vec{x}_{2} + \cdots + c_{n}\vec{x}_{n} \not= \vec{0} \quad ( \text{except for  } c_{1} = c_{2} = \cdots = c_{n} = 0 )
```

- If any $\vec{x} = \vec{0}$, they are not independent.<br>

- when $\vec{v}_{1}, \vec{v}_{2}, \cdots , \vec{v}_{n}$ are columns of $A$, <br>
they are independent if $\ker(A) = \set{\vec{0}}$.<br>
($\ker(A) = \set{\vec{0}}$, there is no free variables.)<br>

- They are dependent if $A\vec{x} = \vec{0}$ for some non-zero vector $\vec{x}$.<br>
($\ker(A) \not= \set{\vec{0}}$, there will be free variables.)<br><br>

**○ Span**

- Vectors $[\vec{v}_{1}, \vec{v}_{2}, \cdots , \vec{v}_{n}]$ <b>span</b> a space,<br>
when the space consists of all their linear combinations.<br><br>

**○ Basis**

- Basis for a vector space is a sequence of vectors $[\vec{v}_{1}, \vec{v}_{2}, \cdots , \vec{v}_{n}]$ with $2$ properties below.<br>
1. They are <b>independent</b>.
2. They <b>span</b> the space.

- For $R^{3}$ space,<br>
Example 1 :<br>
They are <b>independent</b> and <b>span</b> the $R^{3}$ space.

```math
\text{One of basis is}\quad
\begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix}, \begin{bmatrix} 0 \\ 1 \\ 0 \end{bmatrix}, \begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix}
```
<br>

Example 2 :<br>
They are <b>independent</b>, but <b>do not span</b> the $R^{3}$ space.<br>
They can't be a basis of $R^{3}$.

```math
\begin{bmatrix} 1 \\ 1 \\ 2 \end{bmatrix}, \begin{bmatrix} 2 \\ 2 \\ 5 \end{bmatrix}
```

- $n$ vectors in $R^{n}$ space give basis if the $(n \times n)$ matrix is <b>invertible</b>.<br><br>

**○ Dimension**

Every basis for the space has the same number of vectors,<br>
and this number is the <b>dimension</b> of the space.

- (dimension of $C(A)$ ) = (# of pivot variables) = (rank of $A$)
- (dimension of $N(A)$ ) = (# of free variables)
