# Intro Optimization - Class 8

2026-09-28

## Simplex Example
$$
A=\begin{bmatrix} -6 & -5 & 25 & 3 & -85 & 4 & 30 \\ 
4 & -2 & 28 & 6 & -55 & 1 & -9 \\
9 & -5 & 11 & 2 & -55 & -1 & 19\end{bmatrix}
$$

$$
b=\begin{bmatrix} 62 \\ 62 \\ 3\end{bmatrix}
$$

$$
c=\begin{bmatrix} 23 \\ 1 \\ -16 \\ -1 \\52 \\ -6 \\ -12\end{bmatrix}
$$

Task:
$$
\mathrm{min} \ c^Tx
\newline
Ax=b
\newline
x \geq 0
$$

First Tableau: We choose basis 1, 3, 6

Note the LHS corresponds to the $z$ objective function value and will NEVER CHANGE! The top row is the *header row* (so column 2 corresponds to $x_1$)
$$
\begin{bmatrix} 1 & 0 & .77.. & 0 & 0.44.. & -1.444 & 0 & -4.4 & -63.2 \\ 0 & 1 & .44.. & 0 & .11.. & 3.88.. & 0 & -3.11.. & 1.44.. \\ 0 & 0 & -.55.. & 1 & .11.. & 6.11.. & 0 & 2.88.. & .44.. \\ 0 & 0 & 2.88.. & 0 & .22.. & 22.77.. & 1 & -15.22.. & 14.88..\end{bmatrix}
$$

Second Tableau: Pivot to $x_2$ since the coefficient corresponding to it (0.77) is largest positive coefficient. By the ratio test.. we kick out $x_1$
$$
\begin{bmatrix} 1 & -1.65 & 0 & 0 & .25 & -8.25 & 0 & -9 & -65.75 \\ 0 & 2.25 & 1 & 0 & .25 & 8.75 & 0 & -7 & 3.25 \\ 0 & 1.25 & 0 & 1 & .25 & -1.25 & 0 & -1 & 2.25 \\ 0 & -6.5 & 0 & 0 & -.5 & -2.5 & 1 & 5 & 5.5\end{bmatrix}
$$

Third tableau: Pivot to $x_4$ since the coefficient corresponding to it (0.25) is largest positive coefficient. By the ratio test, we kick $x_3$
$$
\begin{bmatrix} 1 & -3 & 0 & -1 & 0 & -7 & 0 & -8 & -68 \\ 0 & 1 & 1 & -1 & 0 & 10 & 0 & -6 & 1 \\ 0 & 5 & 0 & 4 & 1 & -5 & 0 & -4 & 9 \\ 0 & -4 & 0 & 2 & 0 & -5 & 1 & 3 & 10\end{bmatrix}
$$

No more positive objective function coefficients- this is optimal. 

$$
FBV=\begin{bmatrix} 0 \\ 1 \\ 0 \\ 9 \\ 0 \\ 10 \\ 0\end{bmatrix}
$$

## A Second Simplex Example

$$
A=\begin{bmatrix} 8 & -226 & -33 & 10 & 9 & 49 & -1 \\ 9 & -199 & -51 & 10 & 3 & 25 & -25 \\ 2 & 24 & 45 & -6 & 3 & -45 & -15\end{bmatrix}
$$

$$
b=\begin{bmatrix} 107 \\ 55 \\ 25\end{bmatrix}
$$

$$
c=\begin{bmatrix} -4 \\ 63 \\ 7 \\ -2 \\ -2 \\ 0 \\ 21\end{bmatrix}
$$

The first tableau, if we choose basis columns 1,3,4:
$$
\begin{bmatrix} 1 & 0 & 3 & 0 & 0 & .33.. & 5 & -6 & -25 \\ 0 & 1 & -9 & 0 & 0 & 0 & -6 & -6 & 2 \\ 0 & 0 & -2 & 1 & 0 & .33.. & 1 & 1 & 3 \\ 0 & 0 & -22 & 0 & 1 & 2 & 13 & 8 & 19\end{bmatrix}
$$

Observe that third column. We can already conclude the **objective function is unbounded below**. Objective function coefficient is positive but constraint coefficients are negative (steps in the direction $x_2$ always reduce the obj func value). So there is **no solution**.

## A Third Simplex Example
$$
A=\begin{bmatrix} 7 & 7 & 45 & -1 & 3 & -53 & -68 \\ 9 & -5 & 27 & -115 & 7 & -129 & 42 \\ 5 & -3 & 63 & -96 & 10 & -109 & 86\end{bmatrix}
$$

$$
b = \begin{bmatrix} 26 \\ 18 \\ 34\end{bmatrix}
$$

$$
c=\begin{bmatrix} 1 \\ 7 \\ -37 \\ 94 \\ -9 \\ 76 \\ -146\end{bmatrix}
$$

First Tableau if we choose basis 1,2,5:

$$
\begin{bmatrix} 1 & 0 & 0 & -8 & -5 & 0 & -9 & 0 & -22 \\ 0 & 1 & 0 & -1 & -5 & 0 & -8 & -7 & 0 \\ 0 & 0 & 1 & 4 & 7 & 0 & 3 & -7 & 2 \\ 0 & 0 & 0 & 8 & -5 & 1 & -6 & 10 & 4\end{bmatrix}
$$

Notice the header row is non-positive.. so we already have the optimal basis here..

$$
FBV=\begin{bmatrix} 0 \\ 2 \\ 0 \\ 0 \\ 4 \\ 0 \\ 0\end{bmatrix}
$$

While there is *degeneracy* due to the zero in the 8th column, we're still optimal. It's fine.

What if we chose the basis based on 1,2,7?
$$
\begin{bmatrix} 1 & 0 & 0 & -8 & -5 & 0 & -9 & 0 & -22 \\ 0 & 1 & 0 & 4.6 & -8.5 & .7 & -12.2 & 0 & 2.8 \\ 0 & 0 & 1 & 9.6 & 3.5 & .7 & -1.2 & 0 & 4.8 \\ 0 & 0 & 0 & .8 & -.5 & .1 & -.6 & 1 & .4\end{bmatrix}
$$

Observe the header row is non-positive.. this is also optimal!
$$
FBV=\begin{bmatrix} 2.8 \\ 4.8 \\ 0 \\ 0 \\ 0 \\ 0 \\ .4\end{bmatrix}
$$

So in this problem, we have **non-unique** solutions get us to the same optimal objective function value $-22$. We could've saw this coming through the degeneracy observation.

And if we chose the basis 1,3,6?
$$
\begin{bmatrix} 1 & 0 & 2.5 & 0 & 13.75 & -.25 & 0 & -20 & -18 \\ 0 & 1 & 1.458 & 0 & 8.229 & -.604 & 0 & -23.25 & .5 \\ 0 & 0 & .125 & 1 & .5625 & .0625 & 0 & -.25 & .5 \\ 0 & 0 & .166.. & 0 & 1.583 & -.0833 & 1 & -2 & 0\end{bmatrix}
$$

Here, we want to introduce $x_4$. By the ratio test (0 always lowest) we must kick out $x_6$. Tableau 2 hence is 1,3,4:
$$
\begin{bmatrix} 1 & 0 & 1.053 & 0 & 0 & .4737 & -8.6842 & -2.6316 & -18 \\ 0 & 1 & .5921 & 0 & 0 & -.1711 & -5.1974 & -12.8553 & .5 \\ 0 & 0 & .0658 & 1 & 0 & .0921 & -.3553 & .4625 & .5 \\ 0 & 0 & .1053 & 0 & 1 & -.0526 & .6316 & -1.2632 & 0\end{bmatrix}
$$

Observe that the objective function value didn't change.. and even though we changed bases, it's the same FBV (a common consequence of degeneracy..)

We must introduce $x_2$ and by the ratio test $x_4$ is kicked. So tableau 3 consists of 1,3,2:
$$
\begin{bmatrix} 1 & 0 & 0 & 0 & -10 & 1 & -15 & 10 & -18 \\ 0 & 1 & 0 & 0 & -5.62 & .125 & -8.75 & -5.75 & .5 \\ 0 & 0 & 0 & 1 & -.62 & .125 & -.75 & 1.25 & .5 \\ 0 & 0 & 1 & 0 & 9.5 & -.5 & 6 & -12 & 0\end{bmatrix}
$$

We should introduce $x_7$ and by the ratio test we must kick out $x_3$. But we already showed 1,2,7 is optimal!