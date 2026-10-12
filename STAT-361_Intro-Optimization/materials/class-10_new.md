# Intro Optimization - Class 10

2026-10-02

## FBVs

Here is an alternative and equivalent way to define FBS:

If $x$ is feasible in the LP, $x$ is a **feasible basic vector** precisely when:
$$
\{A^{(i)}: x_i \geq 0\}
$$

is linearly independent, where $A^{i}$ denotes a basic column.

**Important Theorem**: $x$ is an extreme point of $S$ *if and only if* $x$ is a basic feasible vector.

Proof ($\leftarrow$):
- Suppose $x$ is a FBV. 
- WLOG:
$$
A=[B|N]
$$

$B$ is a basis, $x_N=0$, $x_B=B^{-1}b \geq 0$

Suppose $x'=\begin{bmatrix} x_b' \\ x_N'\end{bmatrix}$ and $x''=\begin{bmatrix} x_b'' \\ x_N''\end{bmatrix}$ and $\lambda \in (0,1)$ s.t. $x=\lambda x'+(1-\lambda)x''$

In particular:
$$
0=x_N=\lambda x_N'+(1-\lambda)x_N''
$$

$x_N' \geq 0$, $(1-\lambda)x_N''$ $\geq 0$. It must be the case that $x_N'=x_N''=0$ 

Next: Solving for the basic:

$x_B=Bx_B'+Nx_N'=Ax'=b$ i.e. $x_B'=B^{-1}b$

$Bx_B''=Bx_B''+Nx_N''=Ax''=b$ i.e. $x_B''=B^{-1}b$

they are the same. we've concluded $x'=x''$. Thus $x$ is an extreme point of $S$.

We now prove $\rightarrow$:

Suppose $x$ is not an FBV. That is, $\{A^{(i)}: x_i \geq 0\}$ is linearly dependent. 

This means there exists $z \in \mathbb{R}^n$ s,t, $Az=0$ and $z \neq 0$ and $\forall i$ s.t. $z_i \neq 0$ only if $x_i \gt 0$ (can you see this...?)

Now, there must exist $\epsilon > 0$ small enough s.t. $x' :=x+\epsilon z \geq 0$ and $x'' = x-\epsilon z \geq 0$

So $x'$ and $x'' \in S$ since $x' \geq 0$ and $x'' \geq 0$

$Ax'=A(x+\epsilon z)=Ax+\epsilon Az$ ($Az=0$)

Therefore, $Ax=b$

And by similar logic:

$Ax''=A(x-\epsilon z)=Ax+\epsilon Az=b$

Now take:

$\frac{1}{2}(x+\epsilon z)+\frac{1}{2}(x-\epsilon z)=x$

Furthermore, $x' \neq x'',\ z \geq 0, \ \epsilon > 0$

Hence $x$ is NOT an extreme point of $S$.

**END OF MATERIAL COVERED BY EXAM 1**

Professor's synthesis of content thus far and how to think about what will be covered on Midterm 1:

*Two key ideas covered thus far. First, basic optimization principles. Ideas, concepts, definitions. Relevant set theory and topology. Defining the space we're working in. Preliminary stuff. Second, linear programming. Setting up problems in a linear algebra-esque form. The idea of when solutions exist, feasible basic vectors and bases. Actually solving them with simplex algorithm.*