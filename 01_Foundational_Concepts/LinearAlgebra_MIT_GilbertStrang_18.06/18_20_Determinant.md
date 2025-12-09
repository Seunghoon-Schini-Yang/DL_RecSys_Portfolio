# 📚 Lecture 18: Properties of determinants

**○ For square matrix $A$,**

1. $\det I = 1$
<br>

2. Exchange rows : Reverse the sign of $det A$
```math
\begin{vmatrix} a & b \\ c & d \end{vmatrix} = k , \quad
\begin{vmatrix} c & d \\ a & b \end{vmatrix} = -k
```
<br>

3. ⓐ
```math
\begin{vmatrix} ta & tb \\ c & d \end{vmatrix} = t\begin{vmatrix} a & b \\ c & d \end{vmatrix} = tk
```

3. ⓑ Linear for each row
```math
\begin{vmatrix} a+a^{'} & b+b^{'} \\ c & d \end{vmatrix} = \begin{vmatrix} a & b \\ c & d \end{vmatrix} + \begin{vmatrix} a^{'} & b^{'} \\ c & d \end{vmatrix}
```
<br>

4. If $A$ has 2 equal rows : $\det A = 0$<br>
```math
\begin{vmatrix} a & b \\ a & b \end{vmatrix} = k = -k = 0 \quad\text{(property 2)}
```
<br>

5. Substract $l * row_{i}$ from $row_{j}$ : $\det A$ doesn't change.
```math
\begin{align}
\begin{vmatrix} a & b \\ c-la & d-lb \end{vmatrix} {} &= \begin{vmatrix} a & b \\ c & d \end{vmatrix} + \begin{vmatrix} a & b \\ -la & -lb \end{vmatrix} \quad\text{(property 3-ⓑ)} \\
&= \begin{vmatrix} a & b \\ c & d \end{vmatrix} + (-l)\begin{vmatrix} a & b \\ a & b \end{vmatrix} \quad\text{(property 3-ⓐ)} \\
&= \begin{vmatrix} a & b \\ c & d \end{vmatrix} + (-1)*0 \quad\text{(property 4)} \\
&= \begin{vmatrix} a & b \\ c & d \end{vmatrix}
\end{align}
```
<br>

6. If $A$ has a row of zeros : $\det A = 0$
```math
\begin{vmatrix} 0 & 0 \\ c & d \end{vmatrix} = \begin{vmatrix} 0*a & 0*b \\ c & d \end{vmatrix} = 0*\begin{vmatrix} a & b \\ c & d \end{vmatrix} = 0 \quad\text{(property 3-ⓐ)}
```
<br>

7. Triangular Matrix : Product of pivots<br>
```math
\begin{align}
U {} &= \begin{vmatrix}
d_{1} & * & * & \cdots & * \\
0 & d_{2} & * & \cdots & * \\
0 & 0 & d_{3} & \cdots & * \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
0 & 0 & 0 & \cdots & d_{n}
\end{vmatrix} \\
& \text{(Eliminate non-pivot elements from bottom rows to upper rows.)} \\
&= \begin{vmatrix}
d_{1} & 0 & 0 & \cdots & 0 \\
0 & d_{2} & 0 & \cdots & 0 \\
0 & 0 & d_{3} & \cdots & 0 \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
0 & 0 & 0 & \cdots & d_{n} \\
\end{vmatrix} \quad\text{(property 5)} \\
&= (d_{1} d_{2} d_{3} \cdots d_{n})
\begin{vmatrix}
1 & 0 & 0 & \cdots & 0 \\
0 & 1 & 0 & \cdots & 0 \\
0 & 0 & 1 & \cdots & 0 \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
0 & 0 & 0 & \cdots & 1
\end{vmatrix} \quad\text{(property 3-ⓐ)} \\\\
&= (d_{1} d_{2} d_{3} \cdots d_{n}) * 1 \quad\text{(property 1)} \\\\
&= d_{1} d_{2} d_{3} \cdots d_{n} \quad\text{(: Product of pivots)}
\end{align}
```
<br>

8. $\det A = 0$, when $A$ is <b>singular</b>.<br>
($\det A \not= 0$, when $A$ is <b>invertible</b>.)

A is invertible, when elimination produces a full setup non-zero pivots.<br>
(from Lecture 2)

```math
\begin{align*}
U {} &= (E_{1} E_{2} \cdots E_{k}) A \quad(E_{i} \:\text{: apply property 2 or 5}) \\\\
&= (E_{1} E_{2} \cdots E_{k}) \begin{bmatrix}
a_{11} & a_{12} & \cdots & a_{1n} \\
a_{21} & a_{22} & \cdots & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{n1} & a_{n2} & \cdots & a_{nn}
\end{bmatrix} \\\\
&= \begin{bmatrix}
p_{1} & * & \cdots & * \\
0 & p_{2} & \cdots & * \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \cdots & p_{n}
\end{bmatrix} \quad(p_{j} \:\text{: pivot of each row})
\end{align*}
```

If $A$ is <b>singular</b>,<br>
then at least one of $p$ in $U$ becomes zero.<br>
$\therefore \det U = p_{1} p_{2} \cdots p_{n} = 0$<br>
→ $\det A = 0$

If $A$ is <b>invertible</b>,<br>
then none of $p$ in $U$ is zero.<br>
$\therefore \det U = p_{1} p_{2} \cdots p_{n} \not= 0$<br>
→ $\det A \not= 0$

Example 1)
```math
\begin{align}
\begin{vmatrix} a & b \\ c & d \end{vmatrix} {} &= \begin{vmatrix} a & b \\ 0 & d-\frac{b}{a}c \end{vmatrix} \quad\text{(property 5)} \\
&= a(d-\frac{b}{a}c) \quad\text{(property 7)} \\
&= ad-bc
\end{align}
```

Example 2) singular case
```math
\begin{align}
\begin{vmatrix} a & b \\ a & b \end{vmatrix} {} &= \begin{vmatrix} a & b \\ 0 & 0 \end{vmatrix} \quad\text{(property 5)} \\
&= a*0 \quad\text{(property 7)} \\
&= 0
\end{align}
```
<br>

9. $\det AB = (\det A)(\det B)$
- $\det A^{-1}$
```math
\begin{align}
A^{-1}A = I \\
\det A^{-1}A = (\det A^{-1})(\det A) = \det I = 1 \\
\therefore \det A^{-1} = \frac{1}{\det A}
\end{align}
```

- $\det A^{2} = (\det A)(\det A) = (\det A)^{2}$

- $\det 2A = (\det 2I)(\det A) = 2^{n}(\det A)\quad$ (property 3-ⓐ)
<br>

10. $\det A^{T} = \det A$<br>
(Based on this property, <b>all other properties can work with columns!</b>)

- Proof)
```math
\begin{align}
\quad\text{(property 9)}\quad \begin{cases}
\det A = \det LU = (\det L)(\det U) \\
\det A^{T} = \det (LU)^{T} = \det U^{T}L^{T} = (\det U^{T})(\det L^{T})
\end{cases}
\end{align}
```
<br>

We can make all diagonal elements of $L$ to be $1$ through elimination.<br>
(from Lecture 4)
```math
\det L = \det L^{T}
= \begin{vmatrix}
1 & 0 & 0 & \cdots & 0 \\
* & 1 & 0 & \cdots & 0 \\
* & * & 1 & \cdots & 0 \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
* & * & * & \cdots & 1
\end{vmatrix} = 1
```
<br>

```math
\begin{align}
{} & \det A^{T} = \det A \\
\text{→}\quad & (\det U^{T})(\det L^{T}) = (\det L)(\det U) \\
\text{→}\quad & (\det U^{T}) = (\det U) \quad(\therefore \: \text{proved!})
\end{align}
```

<br><br><br>

# 📚 Lecture 19: Determinant formulas and cofactors

- In case of $(2 \times 2)$,
```math
\begin{align}
\begin{vmatrix} a & b \\ c & d \end{vmatrix} {} &= \begin{vmatrix} a & 0 \\ c & d \end{vmatrix} + \begin{vmatrix} 0 & b \\ c & d \end{vmatrix} \quad\text{(property 3-ⓑ)} \\
&= (\cancelto{0}{\begin{vmatrix} a & 0 \\ c & 0 \end{vmatrix}} + \begin{vmatrix} a & 0 \\ 0 & d \end{vmatrix}) + (\begin{vmatrix} 0 & b \\ c & 0 \end{vmatrix} + \cancelto{0}{\begin{vmatrix} 0 & b \\ 0 & d \end{vmatrix}} \quad\text{(property 3-ⓑ)}) \\
&= \begin{vmatrix} a & 0 \\ 0 & d \end{vmatrix} - \begin{vmatrix} c & 0 \\ 0 & b \end{vmatrix} \quad\text{(property 2)} \\
&= ad - bc \quad\text{(property 7)}
\end{align}
```
<br>

- In case of $(3 \times 3)$,
```math
\begin{align}
\begin{vmatrix} a_{11} & a_{12} & a_{13} \\ a_{21} & a_{22} & a_{23} \\ a_{31} & a_{32} & a_{33} \end{vmatrix} {}
&= \begin{vmatrix} a_{11} & 0 & 0 \\ a_{21} & a_{22} & a_{23} \\ a_{31} & a_{32} & a_{33} \end{vmatrix}
+ \begin{vmatrix} 0 & a_{12} & 0 \\ a_{21} & a_{22} & a_{23} \\ a_{31} & a_{32} & a_{33} \end{vmatrix}
+ \begin{vmatrix} 0 & 0 & a_{13} \\ a_{21} & a_{22} & a_{23} \\ a_{31} & a_{32} & a_{33} \end{vmatrix} \quad\text{(property 3-ⓑ)} \\
&= \begin{vmatrix} a_{11} & 0 & 0 \\ 0 & a_{22} & a_{23} \\ 0 & a_{32} & a_{33} \end{vmatrix}
+ \begin{vmatrix} 0 & a_{12} & 0 \\ a_{21} & 0 & a_{23} \\ a_{31} & 0 & a_{33} \end{vmatrix}
+ \begin{vmatrix} 0 & 0 & a_{13} \\ a_{21} & a_{22} & 0 \\ a_{31} & a_{32} & 0 \end{vmatrix} \quad\text{(property 4)} \\
&= a_{11} \begin{vmatrix} a_{22} & a_{23} \\ a_{32} & a_{33} \end{vmatrix}
- a_{12} \begin{vmatrix} a_{21} & a_{23} \\ a_{31} & a_{33} \end{vmatrix}
+ a_{13} \begin{vmatrix} a_{21} & a_{22} \\ a_{31} & a_{32} \end{vmatrix} \quad\text{(property 2, 7, 10)} \\
\end{align}
```
<br>

- In case of $(n \times n)$ matrix $A$,<br>
(Minor of $a_{ij}$) : $M_{ij}$ is determinant of $(n-1) \times (n-1)$ matrix with $row_{i}$ and $col_{j}$ erased.<br>
(Cofactor of $a_{ij}$) : $C_{ij} = (-1)^{(i+j)}M_{ij}$<br>

```math
\det A = \begin{cases}
\sum_{i=1}^{n} (-1)^{(i+j)} a_{ij} M_{ij} = \sum_{i=1}^{n} a_{ij} C_{ij} \quad \langle \: j \in {1, 2, \cdots, n} \: \rangle \\\\
\sum_{j=1}^{n} (-1)^{(i+j)} a_{ij} M_{ij} = \sum_{j=1}^{n} a_{ij} C_{ij} \quad \langle \: i \in {1, 2, \cdots, n} \: \rangle
\end{cases}
```
<br>

- $C$ : Cofactor Matrix

```math
C = \begin{bmatrix}
C_{11} & C_{12} & C_{13} & \cdots & C_{1n} \\
C_{21} & C_{22} & C_{23} & \cdots & C_{2n} \\
C_{31} & C_{32} & C_{33} & \cdots & C_{3n} \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
C_{n1} & C_{n2} & C_{n3} & \cdots & C_{nn}
\end{bmatrix}
```

<br><br><br>

# 📚 Lecture 20: Cramer's rule, inverse matrix, and volume

**○ Inverse Matrix $(A^{-1} = \frac{1}{\det A}C^{T})$**

- In case of $(2 \times 2)$ matrix,

```math
\begin{align}
\begin{bmatrix} a & b \\ c & d \end{bmatrix}^{-1} {}
&= (\frac{1}{ad-bc}) \begin{vmatrix} d & -b \\ -c & a \end{vmatrix} \\
&= (\frac{1}{\det A}) \begin{bmatrix} C_{11} & C_{12} \\ C_{21} & C_{22} \end{bmatrix}^{T} \\
& = (\frac{1}{\det A}) C^{T}
\end{align}
```
<br>

- In case of $(n \times n)$ matrix,

```math
\sum_{j=1}^{n} a_{xj} C_{yj} = \begin{cases}
\det A \quad \langle \: x = y \: \rangle \\
0 \quad \langle \: x \not= y \: \rangle
\end{cases}
```
<br>

```math
\begin{align}
AC^{T} {} &= \begin{bmatrix}
a_{11} & a_{12} & \cdots & a_{1n} \\
a_{21} & a_{22} & \cdots & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{n1} & a_{n2} & \cdots & a_{nn}
\end{bmatrix} \begin{bmatrix}
C_{11} & C_{21} & \cdots & C_{n1} \\
C_{12} & C_{22} & \cdots & C_{n2} \\
\vdots & \vdots & \ddots & \vdots \\
C_{1n} & C_{2n} & \cdots & C_{nn}
\end{bmatrix} \\\\
&= \begin{bmatrix}
\sum_{j=1}^{n} a_{1j}C_{1j} & \sum_{j=1}^{n} a_{1j}C_{2j} & \cdots & \sum_{j=1}^{n} a_{1j}C_{nj} \\
\sum_{j=1}^{n} a_{2j}C_{1j} & \sum_{j=1}^{n} a_{2j}C_{2j} & \cdots & \sum_{j=1}^{n} a_{2j}C_{nj} \\
\vdots & \vdots & \ddots & \vdots \\
\sum_{j=1}^{n} a_{nj}C_{1j} & \sum_{j=1}^{n} a_{nj}C_{2j} & \cdots & \sum_{j=1}^{n} a_{nj}C_{nj}
\end{bmatrix} \\\\
&= \begin{bmatrix}
\det A & 0 & \cdots & 0 \\
0 & \det A & \cdots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \cdots & \det A
\end{bmatrix} \\\\
&= (\det A)I
\end{align}
```
<br>

```math
\therefore\quad A^{-1} = \frac{1}{\det A}C^{T}
```
<br>

Why $\sum_{j=1}^{n} a_{xj} C_{yj} = 0$ when $x \not= y$ ?

```math
\begin{align}
\text{Where}\quad A_{s} = \begin{bmatrix}
a_{11} & a_{12} & \cdots & a_{1n} \\
a_{21} & a_{22} & \cdots & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{x1} & a_{x2} & \cdots & a_{xn} \\
\vdots & \vdots & \ddots & \vdots \\
a\prime_{y1} & a\prime_{y2} & \cdots & a\prime_{yn} \\
\vdots & \vdots & \ddots & \vdots \\
a_{n1} & a_{n2} & \cdots & a_{nn}
\end{bmatrix} \quad \langle \text{with} \: row_{x} = row_{y} \rangle ,
\end{align}
```
<br>

```math
\begin{align}
\text{then}\quad \det A_{s} {} &= a\prime_{y1}C_{y1} + a\prime_{y2}C_{y2} + \cdots + a\prime_{yn}C_{yn} \\
&\quad [\vec{C_{y}} = \langle C_{y1}, C_{y2}, \cdots, C_{yn} \rangle \: \text{from} \: A \: \text{and} \: A_{s} \: \text{are equal.}]\\\\
&= a_{x1}C_{y1} + a_{x2}C_{y2} + \cdots + a_{xn}C_{yn} \quad (\because \: row_{x} = row_{y}) \\\\
&= \sum_{j=1}^{n} a_{xj} C_{yj} \\\\
&= 0 \quad (\because \: A_{s} \: \text{is dependent.})
\end{align}
```
<br>

Exapmle)
```math
\begin{align}
\text{Where}\quad A_{s} = \begin{bmatrix} a_{11} & a_{12} & a_{13} \\ a_{21} & a_{22} & a_{23} \\ a_{11} & a_{12} & a_{13} \end{bmatrix} \quad \langle row_{1} = row_{3} \rangle , \\
\end{align}
```

```math
\begin{align}
\text{then}\quad \det A_{s} {} &= a_{31}C_{31} + a_{32}C_{32} + a_{33}C_{33} \\\\
&= a_{11}C_{31} + a_{12}C_{32} + a_{13}C_{33} \quad (\because \: row_{1} = row_{3}) \\\\
&= \sum_{j=1}^{3} a_{1j} C_{3j} \\\\
&= 0 \quad (\because \: A_{s} \: \text{is dependent.})
\end{align}
```
<br>

**○ Cramer's Rule**

```math
\text{For}\quad A\vec{x} = \vec{b} \: \text{,}
```
<br>

```math
\begin{align}
\vec{x} {} &= A^{-1}\vec{b} \\\\
&= \frac{1}{\det A}C^{T}\vec{b} \\\\
&= \frac{1}{\det A} \begin{bmatrix}
C_{11} & C_{21} & \cdots & C_{n1} \\
C_{12} & C_{22} & \cdots & C_{n2} \\
\vdots & \vdots & \ddots & \vdots \\
C_{1n} & C_{2n} & \cdots & C_{nn}
\end{bmatrix}
\begin{bmatrix} b_{1} \\ b_{2} \\ \vdots \\ b_{n} \end{bmatrix}
= \begin{bmatrix} x_{1} \\ x_{2} \\ \vdots \\ x_{n} \end{bmatrix}
\end{align}
```
<br>

```math
\begin{align}
\therefore \: \vec{x} = \begin{bmatrix} x_{1} \\ x_{2} \\ \vdots \\ x_{n} \end{bmatrix}
= \begin{bmatrix} \sum_{i=1}^{n} b_{i} C_{i1} \\ \sum_{i=1}^{n} b_{i} C_{i2} \\ \vdots \\ \sum_{i=1}^{n} b_{i} C_{in} \end{bmatrix}
= \frac{1}{\det A} \begin{bmatrix} \det B_{1} \\ \det B_{2} \\ \vdots \\ \det B_{n} \end{bmatrix}
\end{align}
```
<br>

- $B_{k}$ : $A$ with $col_{k}$ replaced by $b$

```math
\begin{align} {}
& B_{1} = \begin{bmatrix} \vec{b} & \vec{a_{2}} & \cdots & \vec{a_{n}} \end{bmatrix} \\
& B_{k} = \begin{bmatrix} \vec{a_{1}} & \cdots & \vec{a}_{k-1} & \vec{b} & \vec{a}_{k+1} & \cdots & \vec{a_{n}} \end{bmatrix} \\
& B_{n} = \begin{bmatrix} \vec{a_{1}} & \cdots & \vec{a}_{n-1} & \vec{b} \end{bmatrix}
\end{align}
```
<br><br>

**○ Geometric meaning of determinant**
- $\det A$ = (Volume by rows or columns of $A$)<br>
(Same with area in 2-D case.)<br>

Example)
```math
\begin{align}
\text{For}\quad A = \begin{bmatrix} a & b \\ c & d \end{bmatrix} \: , \\
\text{Area} = \det A = ad - bc
\end{align}
```

<p align="center">
    <img src="images/lecture_20_01.jpg" alt="img_17_01" width="500">
</p><br>

Proof)

From <b>Gram-Schmidt process</b>, (lecture 17)

```math
\text{For}\quad A = \begin{bmatrix} \vec{a_{1}} & \cdots & \vec{a_{n}} \end{bmatrix}, \quad \det A
```
<br>

```math
\begin{align}
\begin{rcases}
\vec{u_{1}} = \vec{a_{1}}, {} & \quad \vec{e_{1}} = \frac{\vec{u_{1}}}{\lVert \vec{u_{1}} \rVert} \\
\vec{u_{2}} = \vec{a_{2}} - \text{proj}_{\vec{u_{1}}}\vec{a_{2}} , & \quad \vec{e_{2}} = \frac{\vec{u_{2}}}{\lVert \vec{u_{2}} \rVert} \\
\vec{u_{3}} = \vec{a_{3}} - \text{proj}_{\vec{u_{1}}}\vec{a_{3}} - \text{proj}_{\vec{u_2}}\vec{a_{3}} , & \quad \vec{e_{3}} = \frac{\vec{u_{3}}}{\lVert \vec{u_{3}} \rVert} \\\\
\quad\vdots & \quad\vdots \\\\
\vec{u_{k}} = \vec{a_{k}} - \sum_{j=1}^{k-1} \text{proj}_{\vec{u_{j}}}\vec{a_{j}} , & \quad \vec{e_{k}} = \frac{\vec{u_{k}}}{\lVert \vec{u_{k}} \rVert}
\end{rcases} \quad \begin{matrix} \text{property 5} \\ \text{property 3-ⓐ} \end{matrix} 
\end{align}
```
<br>

```math
\begin{align}
\therefore\quad \det A {} &= \det (\begin{bmatrix} \vec{a_{1}} & \cdots & \vec{a_{n}} \end{bmatrix}) \\\\
&= \det (\begin{bmatrix} \vec{u_{1}} & \cdots & \vec{u_{n}} \end{bmatrix}) \quad\text{(property 5)} \\\\
&= (\lVert \vec{u_{1}} \rVert \cdots \lVert \vec{u_{n}} \rVert) \det (\begin{bmatrix} \vec{e_{1}} & \cdots & \vec{e_{n}} \end{bmatrix}) \quad\text{(property 3-ⓐ)} \\\\
&= (\lVert \vec{u_{1}} \rVert \cdots \lVert \vec{u_{n}} \rVert) \det Q \\\\
&= \pm \lVert \vec{u_{1}} \rVert \cdots \lVert \vec{u_{n}} \rVert \quad (\because \det Q = \pm 1)
\end{align}
```
<br>

```math
\begin{align} {} \therefore
& \text{(2-D case)}\quad |\det A| = \lVert \vec{u_{1}} \rVert \lVert \vec{u_{2}} \rVert = (\text{area by rows or cols of } A) \\
& \text{(3-D case)}\quad |\det A| = \lVert \vec{u_{1}} \rVert \lVert \vec{u_{2}} \rVert \lVert \vec{u_{3}} \rVert = (\text{volume by rows or cols of } A)
\end{align}
```
<br>

Why $\det Q = \pm 1$ ?

```math
\begin{align}
(\det Q)^{2} {} &= (\det Q)(\det Q) \\
&= (\det Q^{T})(\det Q) \quad\text{(property 10)} \\
&= \det (Q^{T}Q) \quad\text{(property 9)} \\
&= \det I \quad (\because \: Q^{T}Q = I \quad \text{from lecture 17}) \\
&= 1 \quad\text{(property 1)} \\ \\\\\\
\therefore \: \det Q &= \pm 1
\end{align}
```
