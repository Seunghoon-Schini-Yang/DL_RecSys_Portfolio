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
- Vector spaces has to be closed under <b>multiplication and addition</b> of vectors.
<br>In other words, <b>linear combinations</b>.

Ex1) The first quadrant ($Q1$) is not a vector space.
<br>It's not closed under multiplication by all real numbers.<br>$(-1) * (3, 2) = (-3, -2) \not\in Q1$ 

Ex2) $R^{2}$ Space is a vector space.


<br>**○ Subpaces**

- Subspaces of $R^{2}$
1. All of $R^{2}$
2. Any line through zero vector
3. Zero vector

Every subspace has got to contain zero vector.

<br>**○ Column Space**

- All linear combinations from columns of A form a subspace called <b>column space</b>.

```math
A = \begin{bmatrix} 1 & 3 \\ 2 & 3 \\ 4 & 1 \end{bmatrix}
\quad\text{→} \quad C(A) \quad\text{(Column space of A)} 
```
<br>

- Take all their linear combinations, we can fill out the whole plane.

```math
C(A) = R^{2} \quad : \quad
a\begin{bmatrix} 1 \\ 2 \\ 4 \end{bmatrix} + b\begin{bmatrix} 3 \\ 3 \\ 1 \end{bmatrix}
```

