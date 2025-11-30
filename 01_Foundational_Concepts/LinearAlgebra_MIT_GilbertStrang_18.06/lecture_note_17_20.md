# 📚 Lecture 17: Orthogonal matrices and Gram-Schmidt

**○ Orthonormal Matrix**

- For orthonormal matrix $Q$,<br>
Every $\vec{q}$ is orthogonal to every other $\vec{q}$.

```math
\begin{align}
Q = \begin{bmatrix} \vec{q_{1}} & \vec{q_{2}} & \cdots & \vec{q_{n}} \end{bmatrix} \\
\vec{q_{i}}^{T} \cdot \vec{q_{j}} =
\begin{cases}
0 \quad(\text{if} \quad i \not= j) \\
\lVert \vec{q_{i}} \rVert^{2} = 1 \quad(\text{if} \quad i = j)
\end{cases} \\
Q^{T}Q = \begin{bmatrix} \vec{q_{1}}^{T} \\ \vec{q_{2}}^{T} \\ \vdots \\ \vec{q_{n}}^{T} \end{bmatrix} \begin{bmatrix} \vec{q_{1}} & \vec{q_{2}} & \cdots & \vec{q_{n}} \end{bmatrix} = I
\end{align}
```
<br>

- If $Q$ is <b>square</b>,<br>
```math
\text{then}\quad Q^{T} = Q^{-1} \quad (\because\: Q^{T}Q = I)
```
<br>

- $Q$ has orthonormal columns <b>project onto its column space</b>.
```math
\begin{align}
P {} &= Q(Q^{T}Q)^{-1}Q^{T} \\
&= Q(I)Q^{T} \\
&= QQ^{T} \\\\
\end{align}
```

```math
\begin{cases}
P^{T} {} &= (QQ^{T})^{T} = QQ^{T} \\
&= P \quad\text{(: Symmetric)}\\
P^{2} {} &= (QQ^{T})(QQ^{T}) = Q(Q^{T}Q)Q^{T} = Q(I)Q^{T} = QQ^{T} \\
&= P
\end{cases}
```
<br>

- if $Q$ is <b>square</b>, then $P = QQ^{T} = QQ^{-1} = I$.<br>
When $Q$ is square, then $C(Q)$(= columns space of Q) is $R^{n}$(= the whole space).<br>
($\because$ all columns of Q are independent.)<br>
Therefore, the proj. matrix $P$ onto $R^{n}$ becomes $I$(= the identity matrix).<br>
($\because$ proj. of $\vec{x}$ onto $R^{n}$ becomes $\vec{x}$)

- From $A^{T}A\vec{x} = A^{T}\vec{b}$,
```math
\begin{align}
Q^{T}Q\vec{x} = Q^{T}\vec{b} \\\\
\vec{x} = Q^{T}\vec{b} \quad\text(\because \: Q^{T}Q = I) \\\\
\hat{x_{i}} = \vec{q_{i}}^{T}\vec{b}
\end{align}
```
<br>

**○ Gram-Schmidt**

<p align="center">
    <img src="images/lecture_17_01.jpg" alt="img_17_01" width="600">
</p>

orthogonal : $(\vec{d_{a}}, \vec{d_{b}})$<br>
orthonormal : $(\vec{q_{a}}, \vec{q_{b}}) = (\frac{\vec{d_{a}}}{\lVert \vec{d_{a}} \rVert}, \frac{\vec{d_{b}}}{\lVert \vec{d_{b}} \rVert})$

```math
\begin{align}
\vec{d_{b}} = \vec{b} - \frac{\vec{d_{a}}^{T}\vec{b}}{\vec{d_{a}}^{T}\vec{d_{a}}}\vec{d_{a}} \\
\vec{d_{a}}^{T}\vec{d_{b}} = \vec{d_{a}}^{T}(\vec{b} - \frac{\vec{d_{a}}^{T}\vec{b}}{\vec{d_{a}}^{T}\vec{d_{a}}}\vec{d_{a}}) = 0
\end{align}
```
<br>

Now, find $\vec{d_{c}}$ which is perp. to both $\vec{d_{a}}$ and $\vec{d_{b}}$.<br>
($\vec{d_{c}} \perp \vec{d_{a}}$ and $\vec{d_{c}} \perp \vec{d_{b}}$)

```math
\begin{align}
\vec{d_{c}} = \vec{c} - \frac{\vec{d_{a}}^{T}\vec{c}}{\vec{d_{a}}^{T}\vec{d_{a}}}\vec{d_{a}} - \frac{\vec{d_{b}}^{T}\vec{c}}{\vec{d_{b}}^{T}\vec{d_{b}}}\vec{d_{b}} \\
\vec{q_{c}} = \frac{\vec{d_{c}}}{\lVert \vec{d_{c}} \rVert}
\end{align}
```
<br>

Example)
```math
\begin{align}
A = \begin{bmatrix} \vec{a} & \vec{b} \end{bmatrix} = \begin{bmatrix} 1 & 1 \\ 1 & 0 \\ 1 & 2 \end{bmatrix} \\
\begin{cases}
\vec{d_{a}} = \vec{a} = \begin{bmatrix} 1 \\ 1 \\ 1 \end{bmatrix} \\
\vec{d_{b}} = \vec{b} - \frac{\vec{d_{a}}^{T}\vec{b}}{\vec{d_{a}}^{T}\vec{d_{a}}}\vec{d_{a}} = \begin{bmatrix} 1 \\ 0 \\ 2 \end{bmatrix} - \frac{3}{3}\begin{bmatrix} 1 \\ 1 \\ 1 \end{bmatrix} = \begin{bmatrix} 0 \\ -1 \\ 1 \end{bmatrix}
\end{cases}
\end{align}
```

```math
\begin{align}
\vec{q_{a}} = \frac{\vec{d_{a}}}{\lVert \vec{d_{a}} \rVert} = \begin{bmatrix} \frac{1}{\sqrt{3}} \\ \frac{1}{\sqrt{3}} \\ \frac{1}{\sqrt{3}} \end{bmatrix}, \quad
\vec{q_{b}} = \frac{\vec{d_{b}}}{\lVert \vec{d_{b}} \rVert} = \begin{bmatrix} 0 \\ -\frac{1}{\sqrt{2}} \\ \frac{1}{\sqrt{2}} \end{bmatrix} \\
Q = \begin{bmatrix} \vec{q_{a}} & \vec{q_{b}} \end{bmatrix} = \begin{bmatrix} \frac{1}{\sqrt{3}} & 0 \\ \frac{1}{\sqrt{3}} & -\frac{1}{\sqrt{2}} \\ \frac{1}{\sqrt{3}} & \frac{1}{\sqrt{2}} \end{bmatrix}
\end{align}
```
<br>

**○ QR Decomposition** <a href="https://en.wikipedia.org/wiki/QR_decomposition">(Wikipedia)</a>

```math
\begin{align}
\text{proj}_{\vec{u}}\vec{a} = (\frac{\vec{u}^{T}\vec{a}}{\vec{u}^{T}\vec{u}})\vec{u} \quad (= \vec{a} \: \text{proj. onto} \: \vec{u}) \\
\langle \vec{e}, \vec{a} \rangle = \vec{e} \cdot \vec{a} = \vec{e}^{T}\vec{a} = \vec{a}^{T}\vec{e}
\end{align}
```

- From Gram-Schmidt process,

```math
A = \begin{bmatrix} \vec{a_{1}} & \cdots & \vec{a_{n}} \end{bmatrix}
```

```math
\begin{align}
\begin{cases}
\vec{u_{1}} = \vec{a_{1}}, {} & \quad \vec{e_{1}} = \frac{\vec{u_{1}}}{\lVert \vec{u_{1}} \rVert} \\
\vec{u_{2}} = \vec{a_{2}} - \text{proj}_{\vec{u_{1}}}\vec{a_{2}} , & \quad \vec{e_{2}} = \frac{\vec{u_{2}}}{\lVert \vec{u_{2}} \rVert} \\
\vec{u_{3}} = \vec{a_{3}} - \text{proj}_{\vec{u_{1}}}\vec{a_{3}} - \text{proj}_{\vec{u_2}}\vec{a_{3}} , & \quad \vec{e_{3}} = \frac{\vec{u_{3}}}{\lVert \vec{u_{3}} \rVert} \\\\
\quad\vdots & \quad\vdots \\\\
\vec{u_{k}} = \vec{a_{k}} - \sum_{j=1}^{k-1} \text{proj}_{\vec{u_{j}}}\vec{a_{j}} , & \quad \vec{e_{k}} = \frac{\vec{u_{k}}}{\lVert \vec{u_{k}} \rVert}
\end{cases}
\end{align}
```
<br>

```math
\begin{align}
Q = \begin{bmatrix} \vec{e_{1}} & \cdots & \vec{e_{n}} \end{bmatrix}
\end{align}
```
<br>

```math
\begin{align}
\begin{cases}
\vec{a_{1}} = \vec{u_{1}} {} &= \langle \vec{e_{1}}, \vec{a_{1}} \rangle \vec{e_{1}} \\
\vec{a_{2}} = \text{proj}_{\vec{u_{1}}}\vec{a_{2}} + \vec{u_{2}} &= \langle \vec{e_{1}}, \vec{a_{2}} \rangle \vec{e_{1}} + \langle \vec{e_{2}}, \vec{a_{2}} \rangle \vec{e_{2}} \\
\vec{a_{3}} = \text{proj}_{\vec{u_{1}}}\vec{a_{3}} + \text{proj}_{\vec{u_2}}\vec{a_{3}} + \vec{u_{3}} &= \langle \vec{e_{1}}, \vec{a_{3}} \rangle \vec{e_{1}} + \langle \vec{e_{2}}, \vec{a_{3}} \rangle \vec{e_{2}} + \langle \vec{e_{3}}, \vec{a_{3}} \rangle \vec{e_{3}} \\\\
\quad\vdots & \quad\vdots \\\\
\vec{a_{k}} = \sum_{j=1}^{k-1} \text{proj}_{\vec{u_{j}}}\vec{a_{j}} + \vec{u_{k}} &= \sum_{j=1}^{k} \langle \vec{e_{j}}, \vec{a_{k}} \rangle \vec{e_{j}}
\end{cases}
\end{align}
```
<br>

- $A = QR$

```math
\begin{align}
A {} &= \begin{bmatrix} \vec{a_{1}} &\vec{a_{2}} &\vec{a_{3}} & \cdots & \vec{a_{n}} \end{bmatrix} \\
&= \begin{bmatrix} \vec{e_{1}} & \vec{e_{2}} & \vec{e_{3}} & \cdots & \vec{e_{n}} \end{bmatrix}
\begin{bmatrix}
\langle \vec{e_{1}}, \vec{a_{1}} \rangle & \langle \vec{e_{1}}, \vec{a_{2}} \rangle & \langle \vec{e_{1}}, \vec{a_{3}} \rangle & \cdots & \langle \vec{e_{1}}, \vec{a_{n}} \rangle \\
\langle \vec{e_{2}}, \vec{a_{1}} \rangle & \langle \vec{e_{2}}, \vec{a_{2}} \rangle & \langle \vec{e_{2}}, \vec{a_{3}} \rangle & \cdots & \langle \vec{e_{2}}, \vec{a_{n}} \rangle \\
\langle \vec{e_{3}}, \vec{a_{1}} \rangle & \langle \vec{e_{3}}, \vec{a_{2}} \rangle & \langle \vec{e_{3}}, \vec{a_{3}} \rangle & \cdots & \langle \vec{e_{3}}, \vec{a_{n}} \rangle \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
\langle \vec{e_{n}}, \vec{a_{1}} \rangle & \langle \vec{e_{n}}, \vec{a_{2}} \rangle & \langle \vec{e_{n}}, \vec{a_{3}} \rangle & \cdots & \langle \vec{e_{n}}, \vec{a_{n}} \rangle
\end{bmatrix}
\end{align}
```

```math
\begin{align}
{} &= \begin{bmatrix} \vec{e_{1}} & \vec{e_{2}} & \vec{e_{3}} & \cdots & \vec{e_{n}} \end{bmatrix}
\begin{bmatrix}
\langle \vec{e_{1}}, \vec{a_{1}} \rangle & \langle \vec{e_{1}}, \vec{a_{2}} \rangle & \langle \vec{e_{1}}, \vec{a_{3}} \rangle & \cdots & \langle \vec{e_{1}}, \vec{a_{n}} \rangle \\
0 & \langle \vec{e_{2}}, \vec{a_{2}} \rangle & \langle \vec{e_{2}}, \vec{a_{3}} \rangle & \cdots & \langle \vec{e_{2}}, \vec{a_{n}} \rangle \\
0 & 0 & \langle \vec{e_{3}}, \vec{a_{3}} \rangle & \cdots & \langle \vec{e_{3}}, \vec{a_{n}} \rangle \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
0 & 0 & 0 & \cdots & \langle \vec{e_{n}}, \vec{a_{n}} \rangle
\end{bmatrix} \\\\
&= QR \quad
\begin{cases}
Q \quad \text{: Orthonormal Matrix} \\
R \quad \text{: Upper Triangular Matrix}
\end{cases}
\end{align}
```

<br><br><br>

# 📚 Lecture 18: Properties of determinants

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
$\det A \not= 0$, when $A$ is <b>invertible</b>.
