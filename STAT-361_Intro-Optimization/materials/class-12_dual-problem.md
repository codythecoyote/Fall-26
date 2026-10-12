# Intro Optimization - Class 12

2026-10-07

## Outline

- A corollary on weak duality
- Strong duality

## Corollary on Weak Duality

Recall the theorem of weak duality:

*Theorem*: Given (LP) and its dual (DP), if $x$ feasible in (LP) and $y$ feasible in (DP), then:
$$
\mathrm{obj}_{DP}(y) \leq \mathrm{obj}_{LP}(x)
$$

*Cor*: If ofv of (LP) is unbounded below, then (DP) is infeasible. 
- This makes sense because if LP can become infinitely small, the DP can never satisfy weak duality. So the feasible region of the DP must be empty.

Conversely, if ofv of (DP) is unbounded above, then (LP) is infeasible.
- Similarly, if DP can become infinitely large, the LP can never satisfy weak duality. So the feasible region of the LP must be empty.

## Strong Duality

*Thrm*: Given LP and its dual DP. Suppose LP is feasible and the objective function is bounded below. Then, there exists $x$ feasible in LP and there exists $y$ feasible in DP such that:
$$
\mathrm{ofv}_{DP}(y) = \mathrm{ofv}_{LP}(x)
$$

Thus, in particular, $x$ and $y$ are respectively optimal in LP, DP by the supervisor principle, and:
$$
\mathrm{oofv}_{DP}=\mathrm{oofv}_{LP}
$$

**Proof**: Consider standard form; $A \in \mathbb{R}^{(m \times n)}$ full row rank, $b \in \mathbb{R}^m, c \in \mathbb{R}^n$. Our LP is:
$$
\mathrm{min} \ c^Tx
\newline
Ax=b
\newline
x \geq 0
$$

which by assumption, the objective function is bounded below. So, we know the simplex algorithm terminates with optimal basis. 

Say WLOG, $A=[B \ | \ N]$ where $B$ is the optimal basis. 

The optimal solution of (LP) is $x^*=\begin{bmatrix} B^{-1}b \\ 0\end{bmatrix}$ and 

$r_N^T=c_N^T-c_B^TB^{-1}N \geq 0$ 

since this is the simplex termination condition.

Let's express the dual via the following (we just transposed the definition)
$$
\mathrm{max} \ y^Tb
\newline
y^TA \leq c^T
$$

Consider $y^{*T} := c_B^TB^{-1}$. $y^*$ is feasible in DP since:
$$
y^{*T}A=(c_B^TB^{-1})A=c_B^TB^{-1}[B \ | \ N] = [c_B^T \ | \ c_B^TB^{-1}N]
$$

From the simplex termination condition in the reduced cost,
$$
c_B^TB^{-1}N \leq c_N^T
$$

And so:

$[c_B^T \ | \ c_B^TB^{-1}N] \leq [c_B^T \ | \ c_N^T] = c^T$

Hence, we've shown $y^*$ is feasible in the dual. 

And since $y^{*T}b=(c_B^TB^{-1})b=c_B^T(B^{-1}b)=c^Tx^*$, we have that $\mathrm{ofv}_{DP}(y^*)=\mathrm{ofv}_{LP}(x^*)$

## A Numerical Example of Duality

Consider:
$$
A=\begin{bmatrix} 2 & 0 & 1 & 1 & 3 \\ 4 & 1 & 0 & 2 & 4 \\ 3 & 1 & -1 & 2 & 2\end{bmatrix}, b=\begin{bmatrix} 8 \\ 13 \\ 8\end{bmatrix}, c=\begin{bmatrix} 2 \\ 2 \\ -1 \\ -3 \\ -2\end{bmatrix}
$$