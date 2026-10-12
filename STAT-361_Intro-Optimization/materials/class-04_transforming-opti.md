# Intro to Optimization - Class 4

2026-09-09

## Outline

## Converting between types of linear programs

*Ex*: 
$$
6x_1 + 3x_2 - 8x_3 \leq 6
$$

Negative both sides changes the direction:
$$
-6x_1-3x_2+8x_3 \geq -6
$$

Converting between $=$ to $\leq$ or $\geq$? This is done by expressing $=$ as two inequalities
$$
6x_1 + 3x_2 - 8x_3 = 6
$$

is equivalent to the system:
$$
6x_1+3x_2-8x_3 \geq 6
\newline
6x_1+3x_2-8x_3 \leq 6
$$

Converting from standard to canonical form: ([] denotes a column vector..)
$$
\mathrm{min}_{Ax=b,\ x \geq 0} \ c^Tx
\newline
=\mathrm{min}_{Ax\leq b, \ Ax\geq b, \ x \geq 0} \ c^Tx 
\newline
=\mathrm{min}_{Ax\leq b, \ -Ax\geq -b, \ x \geq 0} \ c^Tx
\newline
= =\mathrm{min}_{[A \ -A]x \ \geq \ [b \ -b], \ x \geq 0}, \ c^Tx
$$

Converting between $\geq$ or $\leq$ to $=$ by creating *slack variables* (subtracts/adds off the "extra" to force equality)
$$
6x_1+3x_2-8x_3 \geq 6
\newline
7x_1-5x_2+2x_3 \geq 5
\newline
=
\newline
6x_1+3x_2-8x_3-x_4 = 6
\newline
7x_1-5x_2+2x_3 \ \ \ -x_5 = 5
\newline
x_4, x_5 \geq 0
$$

Converting from canonical to standard form:
$$
\mathrm{min}_{Ax \geq b, \ x \geq 0} \ c^Tx
\newline
\mathrm{min}_{Ax - z = b, \ x \geq 0, \ z \geq 0} \ c^Tx
\newline
\mathrm{min}_{[A \ | \ -I]^T[x \ z] = b, \ [x \ z] \geq 0} \ [c \ 0]^T[x \ z]

$$

Non-negative constraints $\rightarrow$ eliminate as a separate class (?)
$$
\mathrm{s.t.} \ Ax \geq b, \ x \geq 0
\newline
[A \ I]x \geq [b \ 0]
\newline
\mathrm{the \ next \ line \ or \ smth}
\newline
Ax \leq b , \ x \geq 0
\newline
[A \ -I] \leq [b \ 0]
$$

Non-signed variables $\rightarrow$ non-negative variables (?)

Here let $x_2$ have no sign constrant, and define $x_2', x_2'' \geq 0$, then we can write:
$$
x_2 := x_2' - x_2''
$$

Ex.
$$
\mathrm{min}_{2x_1-3x_2 \geq 9, \ x_1 + x_2 \geq -8, \ x_1 \geq 0, \ x_2 \ no \ sign \ constraint} \ 5x_1 + 6x_2
\newline
\mathrm{min}_{2x_1-3x_2' + 3x_2'' \geq 9, \ x_1 + x_2' - x_2'' \geq -8, \ x_1 \geq 0, \ x_2' \geq 0, \ x_2'' \geq 0} \ 5x_1 + 6x_2' - 6x_2''
$$

*Row operations* don't change the set of solutions.

1. Swapping rows (equations)
2. Multiply row (equation) by a non-zero scalar
3. Add one row (equation) to another

**Theorem**: Suppose $Y, Z \in \mathbb{R}^{(m \times n)}$. $Y$ and $Z$ are **row-equivalent** iff there exists $\Omega \in \mathbb{R}^{(m \times m)}$ invertible such that:
$$
\Omega Y = Z
$$



