# 📚 Lecture 31: Change of basis; image compression

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