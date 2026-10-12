# Optimization Class 6
2026-09-16

## Outline

## Pray for luck
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

Here, a possible feasible vector is $x = \begin{bmatrix} 1 \\ 3 \\ 2 \\ 1\\ 1\end{bmatrix}$

Of course, we wouldn't know that initially. So, suppose $x_4 = x_5 = 0$. Now lets solve for $x_1, x_2, x_3$ (a square system! maybe we'll get lucky with a non-negative solution..)
$$
\begin{bmatrix} 2 & 0 & 1 \\ 4 & 1 & 0 \\ 3 & 1 & -1 \end{bmatrix}
\begin{bmatrix} x_1 \\ x_2 \\ x_3 \end{bmatrix}
= \begin{bmatrix} 8 \\ 13 \\ 8 \end{bmatrix}
\newline
\newline
= Bx_b = b
$$

Good news: $B$ is invertible (the odds are in your favor on this one)
$$
B^{-1} = \begin{bmatrix} 1 & -1 & 1 \\ -4 & 3 & -4 \\ 1 & 2 & -2 \end{bmatrix}
$$

But the real luck? The solution $x_b = B^{-1}b = \begin{bmatrix} 3 \\ 1 \\ 2 \end{bmatrix} \geq 0$

But think about it. Assuming no other info about the problem this would happen $(\frac{1}{2})^3$ of the time (getting 3 non-negative integers)... Now consider this chunk of the system we cut out and look for $x_4$, $x_5$

$$
N = \begin{bmatrix} 1 & 3 \\ 2 & 4 \\ 2 & 2  \end{bmatrix}, x_v = \begin{bmatrix} 0 \\ 0 \end{bmatrix} 
$$

$\begin{bmatrix} 3 \\ 1 \\ 2 \\ 0 \\ 0\end{bmatrix}$ is called a **feasible basic vector** (and is an extreme point of a polyhedral set). Can you show these?

What we instead made $x_4=x_5=1$?
$$
\begin{bmatrix} 2 & 0 & 1 \\ 4 & 1 & 0 \\ 3 & 1 & -1 \end{bmatrix}
\begin{bmatrix} x_1 \\ x_2 \\ x_3 \end{bmatrix}
= \begin{bmatrix} 8 \\ 13 \\ 8 \end{bmatrix} - \begin{bmatrix} 1 & 3 \\ 2 & 4 \\ 2 & 2 \end{bmatrix}\begin{bmatrix} 1 \\ 1 \end{bmatrix} = \begin{bmatrix} 4 \\ 7 \\ 4 \end{bmatrix}

$$

and:
$$
B^{-1}\begin{bmatrix} 4 \\ 7 \\ 4 \end{bmatrix} = \begin{bmatrix} 1 \\ 3 \\ 2 \end{bmatrix} \geq 0
$$

$\begin{bmatrix} 3 \\ 1 \\ 2 \\ 1 \\ 1\end{bmatrix}$ is another particular feasible vector.. maybe?

Now suppose, for now, $x_1, x_3 = 0$
$$
\begin{bmatrix} 0 & 1 & 3 \\ 1 & 2 & 4 \\ 1 & 2 & 2 \end{bmatrix}\begin{bmatrix} x_3 \\ x_4 \\ x_5 \end{bmatrix}=\begin{bmatrix} 8 \\ 13 \\ 8 \end{bmatrix} 
$$

Again we have to get lucky twice. First that $B$ is invertible. Second, that:
$$
B^{-1}b = \begin{bmatrix} 2 \\ \frac{1}{2} \\ \frac{5}{2} \end{bmatrix} \geq 0
$$

Here, again we have: (matrix of third and first column correspond to our non-basic variables $x_1, x_3=0$)
$$
N = \begin{bmatrix} 2 & 1 \\ 4 & 0 \\ 3 & -1 \end{bmatrix}
$$

and we get the feasible basic vector (start denoting by fbV):
$$
\begin{bmatrix} 0 \\ 2 \\ 0 \\ \frac{1}{5} \\ \frac{5}{2} \end{bmatrix}
$$

Now suppose $x_1 = 1, x_3 = 2$. Solve for $x_2, x_4, x_5$
$$
\begin{bmatrix} 0 & 1 & 3 \\ 1 & 2 & 4 \\ 1 & 2 & 2 \end{bmatrix}\begin{bmatrix} x_2 \\ x_4 \\ x_5 \end{bmatrix}=\begin{bmatrix} 8 \\ 13 \\ 8 \end{bmatrix} - \begin{bmatrix} 2 & 1 \\ 4 & 0 \\ 3 & -1 \end{bmatrix}\begin{bmatrix} 1 \\ 2 \end{bmatrix} = \begin{bmatrix} 4 \\ 9 \\ 7 \end{bmatrix}
$$

So:
$$
\begin{bmatrix} x_2 \\ x_4 \\ x_5 \end{bmatrix}=B^{-1}\begin{bmatrix} 4 \\ 9 \\ 7 \end{bmatrix} = \begin{bmatrix} 3 \\ 1 \\ 1 \end{bmatrix} \geq 0
$$

$\begin{bmatrix} 3 \\ 1 \\ 2 \\ 1 \\ 1\end{bmatrix}$ is NOT a fbV.. something about no zeroes?

In general, 
$$
\mathrm{min} \ c^Tx \ \mathrm{s.t.} \ Ax = b, \ x \geq 0
\newline
$$

Assume $A \in \mathbb{R}^{(m \times n)}$ is full row rank (without loss of generality. can you show why? you can just eliminate redundant equations in pre-processing)

From $[A]$, pull out $B \in \mathbb{R^{(m \times m)}}$ and $N \in \mathbb{R^{m \times (n - m)}}$

From $x$ pull out $x_B$ (corresponding to columns of B) and $x_N$ (basic vectors)

Now, if $B$ is invertible, then $B$ is a basis (luck #1)

If $B^{-1} \geq 0$, then we get a feasible basic vector (luck #2)

We can always reorder the columns of $A$. So WLOG, suppose:
$$
A = [B \ | \ N]
$$

$Ax = b$ then is $Bx_B + Nx_N = b$

Then $x_B = B^{-1}(b - Nx_N$)

When $x_N = 0$, $x_B = B^{-1}n$ which is an fbV!

For any $x_N \geq0, $ if $x_B = $ computed above $\geq 0$ then $\begin{bmatrix} x_B \\ x_N \end{bmatrix}$ is feasible.

**Every feasible vector arises this way**

a basis does not only reflect a point but is a point of view!






