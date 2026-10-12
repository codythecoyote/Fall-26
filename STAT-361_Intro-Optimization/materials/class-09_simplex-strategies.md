# Intro Optimization - Class 9

## How to find the first feasible basic tableau?

**Special case**: It's often in practice that $A, b, c \ge 0$ and the traditional objective is:
$$
\mathrm{max} \ c^Tx \ \mathrm{s.t.} \ Ax \leq b, \ x \geq 0
$$

We can reframe this problem as:
$$
\mathrm{min} \ -c^Tx \ \mathrm{s.t.} \ Ax+z=b, \ x,z \geq 0
$$

And in vector form this is:
$$
\mathrm{min} \ \begin{bmatrix} c \\ 0 \end{bmatrix}^T\begin{bmatrix} x \\ z\end{bmatrix} \ \mathrm{s.t.} \ \begin{bmatrix} A & I\end{bmatrix} \begin{bmatrix} x \\ z\end{bmatrix}=b
$$

From this we can construct the immediate tableau:
$$
\begin{bmatrix} 1 & c^T & 0^T & 0 \\ 0 & A & I & b\end{bmatrix}
$$

Observe this is already a **feasible basic tableau** (contains identity and zeros in header row above it) from the slack variables. Of course, this is probably not a good basis, because slack variables generally aren't those of interest.

**This special case above requires just the less than condition and $b \geq 0$**

### Two Phase Method
- REQUIREMENTS: $b \geq 0$. If a component is negative, negate that row to make it positive.

Consider the LP:
$$
\mathrm{min} \ 2x_1+2x_2-x_3-3x_4-2x_5
\newline
\mathrm{s.t.}
\newline
2x_1+x_3+x_4+3x_5=8
\newline
4x_1+x_2+2x_4+4x_5=13
\newline
3x_1+x_2-x_3+2x_4+2x_5=8
\newline
x_1,..,x_5 \geq 0
$$

We mysteriously introduce dummy variables into the LP... call it LP'
$$
\mathrm{min} \ ... + x_6 + x_7  + x_8
\newline
\mathrm{s.t.}
\newline
2x_1+x_3+x_4+3x_5+x_6=8
\newline
4x_1+x_2+2x_4+4x_5+x_7=13
\newline
3x_1+x_2-x_3+2x_4+2x_5+x_8=8
\newline
x_1,..,x_6,x_7,x_8 \geq 0
$$

If the LP is feasible, then the optimal objective function value of LP' is 0. Conversely, if the optimal objective function value of LP' is 0, then LP is feasible.

In solving LP' we will create a feasible basic tableau to solve LP in 'Phase 2'.
