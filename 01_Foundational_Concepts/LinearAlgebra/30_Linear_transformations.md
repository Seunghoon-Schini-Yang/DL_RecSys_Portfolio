# 📚 Lecture 30: Linear transformations and their matrices

### ¶ Linear Transformations ¶

A linear transformation is a function
```math
T : R^{n} \rightarrow R^{m}
```
that satisfies two rules :
1. Additivity
```math
T(\vec{v}+\vec{w}) = T(\vec{v}) + T(\vec{w})
```
2. Homogeneity
```math
T(c\vec{v}) = cT(\vec{v})
```
- From 1 and 2,
```math
T(c\vec{v} + d\vec{w}) = cT(\vec{v}) + dT(\vec{w})
```
<br>

Examples of non-Linear transformation :
- Example 1 : Shift whole plane by $\vec{v}_{0}$.
```math
\begin{align}
T(\vec{v}+\vec{w}) = \vec{v}+\vec{w}+\vec{v}_{0} \not= \vec{v}+\vec{v}+2\vec{v}_{0} = T(\vec{v})+T(\vec{w}) \quad\text{: Additivity not satisfied} \\
T(c\vec{v}) = c\vec{v} + \vec{v}_{0} \not= c(\vec{v}+\vec{v}_{0}) = cT(\vec{v}) \quad\text{: Homogeneity not satisfied}
\end{align}
```
- Example 2 : Vector to its norm
```math
\begin{align}
T(\vec{v}+\vec{w}) = \lVert \vec{v}+\vec{w} \rVert^{2} \not= \lVert \vec{v} \rVert^{2} + \lVert \vec{w} \rVert^{2} = T(\vec{v})+T(\vec{w}) \quad\text{: Additivity not satisfied} \\
T(c\vec{v}) = \lVert c\vec{v} \rVert^{2} \not= c\lVert \vec{v} \rVert^{2} = cT(\vec{v}) \quad\text{: Homogeneity not satisfied}
\end{align}
```
<br>

Examples of Linear transformation :
- Example 1 : Projection
- Example 2 : Rotation
- Example 3 : For matrix $A$, $T(\vec{v}) = A\vec{v}$
```math
\begin{align}
T(\vec{v}+\vec{w}) = A(\vec{v}+\vec{w}) = A\vec{v}+A\vec{w} = T(\vec{v}) + T(\vec{w}) \quad\text{(Additivity)} \\
T(c\vec{v}) = A(c\vec{v}) = cA\vec{v} = cT(\vec{v}) \quad\text{(Homogeneity)}
\end{align}
```
```math
\text{example.}\quad T : R^{3} \rightarrow R^{2} ,\quad T(\vec{v}) = \underset{(2\times 3)}A \vec{\underset{(\in R^{3})}v}
```
<br>

**○ Coordinates**<br>
```math
\begin{align}
\text{For any}\: R^{n} \:\text{basis}\: \set{\vec{v}_{1}, \cdots, \vec{v}_{n}}, \\
\text{every}\: \vec{v} \in R^{n} \:\text{can be expressed with any basis in}\: R^{n}. \\
\vec{v} = x_{1}\vec{v}_{1} + \cdots + x_{n}\vec{v}_{n} \\
\text{Then}\: (x_{1}, \cdots, x_{n}) \:\text{are coordinates in basis}\: \set{\vec{v}_{1}, \cdots, \vec{v}_{n}}.
\end{align}
```
- example :
```math
\begin{align}
\vec{x} = \begin{bmatrix} 3 \\ 2 \\ 4 \end{bmatrix} {} &= x_{1}\vec{e}_{1}+x_{2}\vec{e}_{2}+x_{3}\vec{e}_{3} \\
&= 3\begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix} + 2\begin{bmatrix} 0 \\ 1 \\ 0 \end{bmatrix} + 4\begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix} \\
&= \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{bmatrix} \begin{bmatrix} 3 \\ 2 \\ 4 \end{bmatrix}
\end{align}
```
```math
(3, 2, 4) \:\text{are coordinates in standard basis}\: \set{\vec{e}_{1},\vec{e}_{2},\vec{e}_{3}}
```
<br>
