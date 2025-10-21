# 📚 Lecture 5: Transposes, permutations, spaces $R^n$

<br>**○ Symmetric**

```math
\begin{align*}
R = \begin{bmatrix} a & b & c \\ d & e & f \end{bmatrix} \\
RR^{T} \quad \text{: Why symmetric?} \\
(RR^{T})^{T} = RR^{T} \quad \text{: This is why.}
\end{align*}
```

<br>**○ Vector Spaces**

Vector Space has to be closed under <b>multiplication and addition<b> of vectors.
In other words, <b>linear combinations<b>.

Ex1) The first quadrant is not a vector space.
It's not closed under multiplication by all real numbers.
(-1) * (3, 2) → (-3, -2)

Ex2) $R^2$ Space is a vector space.


<br>**○ Subpaces**

Ex1) Subspace of $R^2$ (a vector space inside $R^2$)
A line in $R^2$ through zero vector.

Every subspace has got to contain zero vector.

- Subspaces of $R^2$
1. All of $R^2$
2. Any line through zero vector
3. Zero vector

<br>**○ Column Space**

$A = \begin{bmatrix} 1 & 3 \\ 2 & 3 \\ 4 & 1 \end{bmatrix}$
columns in $R^3$ : all their combinations form a subspace called columns space $C(A)$.
$C(A) = R^2$ : 
\begin{bmatrix} 1 \\ 2 \\ 4 \end{bmatrix}
\begin{bmatrix} 3 \\ 3 \\ 1 \end{bmatrix}
Take all their linear combinations, we can fill out the whole plane