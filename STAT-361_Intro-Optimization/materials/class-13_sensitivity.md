# intro opti class 13 - sensitivity

## outline
- Intro to sensitivity
- Sensitivity of optimal dual variables
- Sensitivity analysis example
## Sensitivity

Consider the standard form LP:
$$
\mathrm{min} \ c^Tx
\newline
Ax=b
\newline
x \geq 0
$$

The simplex tableau will have final form:
$$
\begin{bmatrix} 1 & \leq 0^T & c_B^TB^{-1}b \\ 0 & I & B^{-1}b \geq 0\end{bmatrix}
$$

(this form is acquirable via row operations)

Now consider the new LP:
$$
\mathrm{min} \ c^Tx
\newline
Ax=b+\Delta b
$$

You can analogously apply row operations to get the SAME final tableau form as above, except in the rightmost column:
$$
\begin{bmatrix} 1 & \leq 0^T & c_B^TB^{-1}(b + \Delta b) \\ 0 & I & B^{-1}(b+\Delta b) \end{bmatrix}
$$

We have two questions about this new tableau:

1. Is it a *feasible basic tableau*?
- That is, is it the case that $B^{-1}(b+\Delta b) \geq 0$?
2. If it is a feasible basic tableau, is an *optimal* feasible basic tableau?
- YES since the header row (negative reduced costs) is unchanged.

*Remark*: If the original final tableau is nondegenerate i.e. $B^{-1}b > 0$, then for $\Delta b$ "small enough", it will still hold that $B^{-1}(b+\Delta b) \geq 0$

## Sensitivity of Optimal Dual Variables

Recall last lecture it was derived:
$$
y^{*T}=c_B^TB^{-1}
$$

is the *optimal dual variable*.

The Optimal Dual Variable WILL NOT CHANGE as $b \rightarrow b+\Delta b$

Why? The optimal objective function value was:
$$
c_B^TB^{-1}b = y^{*T}b
$$

and now is:
$$
c_B^TB^{-1}(b+\Delta b) = y^{*T}b+y^{*T}\Delta b
$$

where $y^{*T}\Delta b$ is the update to the optimal objective function value.

When there is *no degeneracy* in the final tableau, then for all $i$:
$$
y_i^*=\frac{\partial \mathrm{oofv}}{\partial b_i}
$$

### Numerical Example

Let $y^{*}=\begin{bmatrix} 100 \\ 50 \\ 10\end{bmatrix}$ and $b=\begin{bmatrix} 3 \\ 2 \\ 7\end{bmatrix}$ and $\Delta b=\begin{bmatrix} 0.01 \\ -0.5 \\ 1\end{bmatrix}$

(just hypothetical values)

Then:
$$
y^{*T}(b+\Delta b)= \begin{bmatrix} 100 \\ 50 \\ 10\end{bmatrix}^T\begin{bmatrix} 3+0.01 \\ 2-0.5 \\ 7+1\end{bmatrix}
$$

### Example on an actual LP
Consider:
$$
A=\begin{bmatrix} 2 & 0 & 1 & 1 & 3 \\ 4 & 1 & 0 & 2 & 4 \\ 3 & 1 & -1 & 2 & 2\end{bmatrix}, b=\begin{bmatrix} 8 \\ 13 \\ 8\end{bmatrix}, c=\begin{bmatrix} 2 \\ 2 \\ -1 \\ -3 \\ -2\end{bmatrix}
$$

Goal:
$$
\mathrm{min} \ c^Tx
\newline
Ax=b
\newline
x \geq 0
$$

The final tableau will have form:
$$
\begin{bmatrix} 1 & -\frac{1}{2} & 0 & -\frac{1}{2} & 0 & 0 & -\frac{5}{2} \\ 0 & \frac{1}{2} & 0 & -\frac{1}{2} & 1 & 0 & \frac{1}{2}\\0 & 1 & 1 & -1 & 0 & 0 & 2 \\ 0 & \frac{1}{2} & 0 & \frac{1}{2} & 0 & 1 & \frac{5}{2}\end{bmatrix}
$$

with new $b$:

$$
\begin{bmatrix}
8+\Delta\\
13\\
8
\end{bmatrix}
=
b+\Delta
\begin{bmatrix}
1\\0\\0
\end{bmatrix}.
$$

The new basic solution is

$$
\begin{bmatrix}
\frac12+\Delta\\
2-2\Delta\\
\frac52
\end{bmatrix}.
$$

The current basis remains feasible when

$$
-\frac12\leq\Delta\leq1.
$$

Within this interval, $y_1^*=-7$, so the new optimal objective function value is

$$

-\frac52-7\Delta.
$$

Outside this interval, the current basis is no longer feasible.












