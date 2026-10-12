# Intro to Optimization - Class 5

2026-09-11 🇺🇸

## Outline
- More on transforming linear programs

## Reordering variables
Ex.
$$
\mathrm{min}\begin{bmatrix} 17 \\ 83 \\ -11\end{bmatrix}^T\begin{bmatrix} x_1 \\ x_2 \\ x_3\end{bmatrix}
\newline
\mathrm{s.t.}
\newline
\begin{bmatrix} 2 \ -2 \ 6 \\ 3 \ 1 \ -1\end{bmatrix}\begin{bmatrix} x_1 \\ x_2 \\ x_3\end{bmatrix} = \begin{bmatrix} 8 \\ 2\end{bmatrix}
\newline
\begin{bmatrix} x_1 \\ x_2 \\ x_3\end{bmatrix} \geq 0
$$

The variables / columns of $A$ / entries of $C$ can be "conformally reordered"

$$
\mathrm{min}\begin{bmatrix} 83 \\ -11 \\ 17\end{bmatrix}^T\begin{bmatrix} x_2 \\ x_3 \\ x_1\end{bmatrix}
\newline
\mathrm{s.t.}
\newline
\begin{bmatrix} -2 \ 6 \ 2 \\ 1 \ -1 \ 3\end{bmatrix}\begin{bmatrix} x_2 \\ x_3 \\ x_1\end{bmatrix} = \begin{bmatrix} 8 \\ 2\end{bmatrix}
\newline
\begin{bmatrix} x_2 \\ x_3 \\ x_1\end{bmatrix} \geq 0
$$

## Geometry of Linear Programs

Suppose $p,x \in \mathbb{R}^n$. Recall the inner product is:
$$
p^Tx = \sum_{i=1}^n p_ix_i = ||p||||x||cos(\theta)
$$

The product is **positive** if $\theta < \frac{\pi}{2}$ (acute)

The product is $0$ if $\theta = \frac{\pi}{2}$ (vectors **orthogonal**)

The product is **negatve** if $\theta > \frac{\pi}{2}$ (obtuse)

**Def**: suppose $p \in \mathbb{R}^n$ is nonzero. Then:
$$
\{x \in \mathbb{R^n} : p^Tx = 0\}
$$

is a **hyperplane** through the origin with normal vector $p$.

$$
\{x \in \mathbb{R^n} : p^Tx \geq 0\}  \ \mathrm{and} \ \{x \in \mathbb{R^n} : p^Tx \leq 0\}
$$

are (closed) **halfspaces**

**Def**: Suppose $p, z \in \mathbb{R}^n$, $p$ nonzero. Call the spaces:

$$
\{x \in \mathbb{R^n} : p^T(x - z) = 0\}
$$

a hyperplane through $z$ with normal vector $p$

$$
\{x \in \mathbb{R^n} : p^T(x - z) \geq 0\} \ \mathrm{and} \ \{x \in \mathbb{R^n} : p^T(x - z) \leq 0\}
$$

closed halfspaces.

**Hyperplanes** are precisely described by: Given $p \in \mathbb{R}^n$ nonzero, $\alpha \in \mathbb{R}$

$$
\{x \in \mathbb{R^n} : p^Tx = \alpha\}
$$

and **(closed) halfspaces** by:

$$
\{x \in \mathbb{R^n} : p^Tx \geq \alpha\} \ \mathrm{and} \ \{x \in \mathbb{R^n} : p^Tx \leq \alpha\}
$$

A **polyhedron** or **polyhedral set** is the intersection of finitely many halfspaces. 

A **polytope** is a bounded polyhedron.

Ex. Given $A \in \mathbb{R}^{(m \times n)}, \ b \in \mathbb{R}^m$
$$
\{x \in \mathbb{R}^n : Ax \geq b\}
$$

is a polyhedron. Why?

We can rewrite $Ax \geq b$ as:
$$
\begin{bmatrix}
p_{1}^T \\ p_{2}^T \\ . \\ . \\ . \\ p_n^T
\end{bmatrix}
x \geq \begin{bmatrix} b_1 \\ b_2 \\ . \\ . \\ b_n \end{bmatrix}
$$

For any $x \in \mathbb{R}^n$ we have $Ax \geq b$ if and only if:
$p_i^Tx \geq b_i$. 

***All polyhedra can be expressed like this! ($Ax \geq = \leq b$)***

Also, any hyperplane is a polyhedral set. 

