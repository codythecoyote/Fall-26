# Intro Optimization - Class 11

## Outline
- Intro to Duality in Linear Programming
- Symmetric and Standard Form
- Weak Duality
- Supervisor Principle

## Duality in Linear Programming

*Definition*: Given $A \in \mathbb{R}^{(m \times n)}$, $c \in \mathbb{R}^n$, and $b \in \mathbb{R}^m$, we call the **canonical** or **symmetric** form of the (LP):
$$
\mathrm{min} \ c^Tx
\newline
Ax \geq b
\newline
x \geq 0
$$

And this problem as the **dual** (DP):
$$
\mathrm{max} \ b^Ty
\newline
A^Ty \leq c
\newline
y \geq 0
$$

### Example

Consider the canonical LP:
$$
\mathrm{min} \ 1x_1+2x_2
\newline
3x_1+4x_2 \geq 9
\newline
5x_1+6x_2 \geq 10
\newline
7x_1+8x_2 \geq 11
\newline
x_1, x_2 \geq 0
$$

Its dual is:
$$
\mathrm{max} \ 9y_1+10y_2+11y_3
\newline
3y_1+5y_2+7y_3 \leq 1
\newline
4y_1+6y_2+8y_3 \leq 2
\newline
y_1,y_2,y_3 \geq 0
$$

### Duality in Standard Form

*Definition*: Given $A \in \mathbb{R}^{(m \times n)}, c \in \mathbb{R}^n, b \in \mathbb{R}^m$, we call the **standard** form of (LP):
$$
\mathrm{min} \ c^Tx
\newline
Ax=b
\newline
x \geq 0
$$

And this problem has the **dual** (DP):
$$
\mathrm{max} \ b^Ty
\newline
A^Ty \leq c
$$

Observe there is no non-negativity constraint of $y$.

## Symmetric vs. Standard Form

*FACT*: The symmetric and standard forms of the DP are equivalent.

How can we show this? Let's assume we're given a canonical form LP and asked to take a dual. But we forgot how to take the dual of a symmetric form LP- we only know standard form. Recall we convert to:
$$
\mathrm{min} \ c^Tx
\newline
Ax-s=b
\newline
x,s \geq 0
$$

And in matrix form this is:
$$
\mathrm{min} \ \begin{bmatrix} c \\ 0\end{bmatrix}^T \begin{bmatrix} x \\ s\end{bmatrix}
\newline
\begin{bmatrix} A & -I\end{bmatrix} \begin{bmatrix} x \\ s\end{bmatrix} = b
\newline
\begin{bmatrix} x \\ s\end{bmatrix} \geq 0
$$

Now taking the standard form dual:
$$
\mathrm{max} \ b^Ty
\newline
\begin{bmatrix} A^T \\ -I\end{bmatrix}y \leq \begin{bmatrix} c \\ 0\end{bmatrix}
$$

Breaking the constraints into components, we get:
$$
A^Ty \leq c
\newline
-y \leq 0 \implies y \geq 0
$$

Which is now equivalent to the symmetric form dual definition.

Now, what if I only know the symmetric form of duality, but was handed an LP in standard form?

Recall a standard LP can be converted to the equivalent canonical LP:
$$
\mathrm{min} \ c^Tx
\newline
\begin{bmatrix}A \\ -A \end{bmatrix}x \geq \begin{bmatrix}b \\ -b \end{bmatrix}
\newline
x \geq 0
$$

Note this comes from $Ax=b$ $\implies$ $Ax \geq b$ and $Ax \leq b$ $\implies$ $Ax \geq b$ and $-Ax \geq -b$

Let us now take the symmetric dual. So that we can align components, let $y=\begin{bmatrix} U \\ V\end{bmatrix}$ so:
$$
\mathrm{max} \begin{bmatrix}b \\ -b \end{bmatrix} ^T \begin{bmatrix}U \\ V \end{bmatrix}
\newline
\begin{bmatrix} A^T & -A^T\end{bmatrix} \begin{bmatrix}U \\ V \end{bmatrix} \leq c
\newline
\begin{bmatrix}U \\ V \end{bmatrix} \geq 0
$$

We can write the program equivalently as:
$$
\mathrm{max} \ b^T(U-V)
\newline
A^T(U-V) \leq c
\newline
U,V \geq 0
$$

Let's substitute $z=U-V$:
$$
\mathrm{max} \ b^Tz
\newline
A^Tz \leq c
\newline
(z \ \mathrm{unrestricted})
$$

which is indeed the dual in standard form.

## Dual of the dual?

Let's take the symmetric form LP:
$$
\mathrm{min} \ c^Tx
\newline
Ax \geq b
\newline
x \geq 0
$$

We know its dual is:
$$
\mathrm{max} \ b^Ty
\newline
A^Ty \leq c
\newline
y \geq 0
$$

Let's rewrite the dual to symmetric form:
$$
\mathrm{min} \ -b^Ty
\newline
-A^Ty \geq -c
\newline
y \geq 0
$$

Now this dual has the dual:
$$
\mathrm{max} \ -c^Tz
\newline
(-A^T)^Tz \leq -b
\newline
z \geq 0
$$

which is precisely the symmetric LP:
$$
\mathrm{min} \ c^Tz
\newline
Az \geq b
\newline
z \geq 0
$$

## Weak Duality

*Theorem*: Given (LP) and its dual (DP), if $x$ feasible in (LP) and $y$ feasible in (DP), then:
$$
\mathrm{obj}_{DP}(y) \leq \mathrm{obj}_{LP}(x)
$$

That is, the objective function value of the dual is less than or equal to the objective function value of the LP. Hence, the same could be said about their **optimal** objective function values:
$$
\mathrm{oofv}_{DP} \leq \mathrm{oofv}_{LP}
$$

**Proof**: Let's show standard form.

$x$ feasible in (LP) $\implies$ $Ax=b, x \geq 0$ *

$y$ feasible in (DP) $\implies A^Ty \leq c$ **

The objective function value of the value is:
$$
\mathrm{ofv}_{DP}(y) = b^Ty
$$

Substituting *

$$
b^Ty=(Ax)^Ty=x^TA^Ty
$$

Since $x \geq 0$, when we apply ** it holds that:
$$
x^TA^Ty \leq x^Tc = c^Tx
$$

Recall $c^Tx=\mathrm{ofv}_{LP}(x)$. Hence we've shown:
$$
\mathrm{ofv}_{DP}(y) \leq \mathrm{ofv}_{LP}(x)
$$

Let us now prove for symmetric form. Here,

$x$ feasible in LP $\implies Ax \geq b, x \geq 0$

$y$ feasible in DP $\implies A^Ty \leq c, y \geq 0$

Applying the same strategy,
$$
\mathrm{ofv}_{DP}(y) = b^Ty \leq (Ax)^Ty = x^TA^Ty \leq x^Tc = c^Tx = \mathrm{obj}_{LP}(x)
$$

## Supervisor Principle

*Theorem*: Given (LP) and its dual (DP), if $x$ feasible in LP and $y$ feasible in DP and $\mathrm{ofv}_{DP}(y) = \mathrm{ofv}_{LP}(x)$, then $x$ is a (global) optimal solution of LP (intuitively, this is because weak duality does not allow further improvement)
 

## Review Questions

1. Given a general symmetric and standard form LP, write their symmetric and standard form duals (for each, one will come from the definition, the other you'll need to derive).

2. Show that the dual of the dual of an LP (canonical or standard) is the original LP.

3. Derive the theorem of weak duality. i.e. if $x$ feasible in LP and $y$ feasible in DP, show $\mathrm{ofv}_{DP}(y) \leq \mathrm{ofv}_{LP}(x)$

4. Intuitively explain the Supervisor Principle and how it arises from weak duality.