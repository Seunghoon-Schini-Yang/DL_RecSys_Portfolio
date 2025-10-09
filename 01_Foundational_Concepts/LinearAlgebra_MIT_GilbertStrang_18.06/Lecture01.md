# 📚 Chapter 2: Solving Ax = b (The Column Space and the Nullspace)

This chapter focuses on the complete solution to the linear system $\mathbf{A}\mathbf{x} = \mathbf{b}$. We explore the two fundamental subspaces associated with $\mathbf{A}$: the Column Space and the Nullspace.

## 2.1. The Column Space $\text{Col}(\mathbf{A})$

The Column Space is key to determining **when a solution exists** for $\mathbf{A}\mathbf{x} = \mathbf{b}$.

* **Definition:** The **Column Space** $\text{Col}(\mathbf{A})$ of an $m \times n$ matrix $\mathbf{A}$ is the set of all linear combinations of its columns.
* **Condition for Solvability:** The system $\mathbf{A}\mathbf{x} = \mathbf{b}$ has a solution **if and only if** the vector $\mathbf{b}$ lies in the $\text{Col}(\mathbf{A})$.

### 💡 Example: Is $\mathbf{b}$ in $\text{Col}(\mathbf{A})$?

Consider the matrix $\mathbf{A}$ and vector $\mathbf{b}$:

$$
\mathbf{A} = \begin{pmatrix} 1 & 2 \\ 3 & 6 \end{pmatrix}, \quad \mathbf{b} = \begin{pmatrix} 1 \\ 5 \end{pmatrix}
$$

**The Column Space** is the line through $\begin{pmatrix} 1 \\ 3 \end{pmatrix}$: $c \begin{pmatrix} 1 \\ 3 \end{pmatrix}$.
The vector $\mathbf{b}$ is **not** on this line, thus $\mathbf{A}\mathbf{x} = \mathbf{b}$ has **no solution**.

---

## 2.2. The Nullspace $\text{Null}(\mathbf{A})$

The Nullspace describes the **uniqueness** of the solution.

* **Definition:** The **Nullspace** $\text{Null}(\mathbf{A})$ is the set of all solutions $\mathbf{x}$ to the homogeneous equation $\mathbf{A}\mathbf{x} = \mathbf{0}$.
* **Key Property:** The Nullspace is always a **subspace** of $\mathbb{R}^n$.

### 🧩 Finding the Nullspace: The Elimination Method

1.  **Reduce $\mathbf{A}$ to its Echelon Form ($\mathbf{U}$) or Reduced Row Echelon Form ($\mathbf{R}$).**
2.  **Identify Pivot Variables** (corresponding to columns with pivots) and **Free Variables** (corresponding to columns without pivots).

Let's use the same $\mathbf{A}$:
$$
\mathbf{A} = \begin{pmatrix} 1 & 2 \\ 3 & 6 \end{pmatrix} \quad \xrightarrow{\text{Elimination}} \quad \mathbf{U} = \begin{pmatrix} 1 & 2 \\ 0 & 0 \end{pmatrix}
$$

* **Pivot Variable:** $x_1$
* **Free Variable:** $x_2$ (We can choose any value for $x_2$, say $x_2 = 1$).

From $\mathbf{U}\mathbf{x} = \mathbf{0}$: $x_1 + 2x_2 = 0 \Rightarrow x_1 = -2x_2$.
Setting the free variable $x_2 = c$, the Nullspace is:

$$
\mathbf{x} = c \begin{pmatrix} -2 \\ 1 \end{pmatrix} \quad \text{for any scalar } c
$$

The basis for the Nullspace is $\begin{pmatrix} -2 \\ 1 \end{pmatrix}$, and $\text{dim}(\text{Null}(\mathbf{A})) = 1$.