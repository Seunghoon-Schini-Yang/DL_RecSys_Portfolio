# 📚 Lecture 33: Left and right inverses; pseudoinverse

### ¶ Left and right inverses ¶

**○ 2-sided Inverse**<br>
- $A$ is full rank $(\Gamma = m = n)$
```math
A^{-1}A = I = AA^{-1}
```
<br>

**○ Left Inverse**<br>
When $A$ is
- full column rank $(\Gamma = n < m)$
- nullspace $N(A) = \set{\vec{0}}$
- $0$ or $1$ solutions to $A\vec{x} = \vec{b}$
- $A^{T}A$ is full rank and invertible
```math
\begin{align}
I_{n} {} &= (A^{T}A)^{-1}(A^{T}A) \\
&= ((A^{T}A)^{-1}A^{T})A \\
&= A_{left}^{-1}A
\end{align}
```
```math
\therefore\quad A_{left}^{-1} = (A^{T}A)^{-1}A^{T}
```
<br>

**○ Right Inverse**<br>
When $A$ is
- full row rank $(\Gamma = m < n)$
- nullspace $N(A^{T}) = \set{\vec{0}}$
- infinitely many solutions to $A\vec{x} = \vec{b}$
- $(n-m)$ free variables
- $AA^{T}$ is full rank and invertible
```math
\begin{align}
I_{m} {} &= (AA^{T})(AA^{T})^{-1} \\
&= A(A^{T}(AA^{T})^{-1}) \\
&= AA_{right}^{-1}
\end{align}
```
```math
\therefore\quad A_{right}^{-1} = A^{T}(AA^{T})^{-1}
```
<br>

**○ Projection and Left/Right Inverse**<br>
| - | Inverse | Projection |
| :-----: | :----: | :----: |
| Left | $I_{n} = A_{left}^{-1}A$ | $P = AA_{left}^{-1} = A(A^{T}A)^{-1}A^{T}$<br>< proj. onto $Col(A)$ > |
| Right | $I_{m} = AA_{right}^{-1}$ | $P = A_{right}^{-1}A = A^{T}(AA^{T})^{-1}A$<br>< proj. onto $Col(A^{T}) = Row(A)$ > |
<br>

**○ Injective $f(\vec{x}) = A\vec{x}$ for $\vec{x}\in$ Row($A$)**<br>
For $\vec{x}, \vec{y} \in Row(A)$,<br>
if $\vec{x} \not= \vec{y}$ then $A\vec{x} \not= A\vec{y}$.<br>
($\leftrightarrow$ Suppose $A\vec{x} = A\vec{y}$, then $\vec{x} = \vec{y}$.)

- Proof :<br>
```math
\begin{align}
\begin{cases}
(\vec{x} - \vec{y}) \in Row(A) \quad (\because\: \vec{x}, \vec{y} \in Row(A)) \\
(\vec{x} - \vec{y}) \in Ker(A) \quad (\because \: A(\vec{x} - \vec{y}) = \vec{0})
\end{cases} \\
(\vec{x} - \vec{y}) \:\text{is in Row(A) and Ker(A) at the same time.} \\
\text{Row}(A) \cap \text{Ker}(A) = \set{\vec{0}} \\
\therefore\quad \vec{x} - \vec{y} = \vec{0} \quad\leftrightarrow\quad \vec{x} = \vec{y}
\end{align}
```
<br>

**○ Find the pseudoinverse $A^{+}$**<br>
- Start from <b>SVD</b> : $A = U\Sigma V^{T}$
```math
\begin{align}
A^{+} = V\Sigma^{+}U^{T} \\\\\\
\begin{cases}
\text{left :}\quad \Sigma = \text{diag}{(\sigma_{1}, \cdots, \sigma_{n})} ,\quad \Sigma^{+} = \text{diag}{(\frac{1}{\sigma_{1}}, \cdots, \frac{1}{\sigma_{n}})} \\
\text{right :}\quad \Sigma = \text{diag}{(\sigma_{1}, \cdots, \sigma_{m})} ,\quad \Sigma^{+} = \text{diag}{(\frac{1}{\sigma_{1}}, \cdots, \frac{1}{\sigma_{m}})} \\
\end{cases} \\
\begin{cases}
\text{left :}\quad \Sigma^{+}\Sigma = \text{diag}{(\underbrace{1, \cdots, 1}_\text{n})} = I_{n} \\
\text{right :}\quad \Sigma\Sigma^{+} = \text{diag}{(\underbrace{1, \cdots, 1}_\text{m})} = I_{m}
\end{cases}
\end{align}
```