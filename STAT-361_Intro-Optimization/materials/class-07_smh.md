# Optimization - Class 7

2026-09-18

The optimization problem from last time:

$$
\mathrm{min} \ c^Tx \ \mathrm{s.t.} \ Ax = b, \ x \geq 0
\newline
\mathrm{min} \ 2x_1 + 2x_2 - x_3 - 3x_4 - 2x_5
\newline
s.t.
\newline

2x_1 \ \ + x_3 + x_4 + 3x_5 = 8
\newline
4x_1 + x_2 + \ + 2x_4 + 4x_5 = 13
\newline
3x_1 + x_2 - x_3 + 2x_4 + 2x_5 = 8
\newline
x_1, x_2, x_3, x_4, x_5 \geq 0
$$

We now bring in the objective function, using same conventions for $B$ and $N$ as last class:
$$
c^Tx = \begin{bmatrix} c_B \\ c_N \end{bmatrix}^T\begin{bmatrix} x_B \\ x_N \end{bmatrix} = c_B^Tx_B + C_N^Tx_N
$$

Substitute the formula we got based on our luckiness:
$$
x_B = B^{-1}(b-Nx_N) \geq 0
$$

So we get:
$$
c_B^TB^{-1}(b-Nx_N) + c_N^Tx_N
\newline
=c_B^TB^{-1}b + (c_N^T - c_B^TB^{-1}N)x_N
$$

## Simplex Tableau

