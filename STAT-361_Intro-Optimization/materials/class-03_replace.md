# Intro to Optimization - Class 3
2026-09-04

## Outline
- Intro to Linear Programming
- Diet and Transportation Problems

## Learning Objectives
- I can **set up** linear programming problems in both canonical and standard form.
- I can **convert** between different kinds of linear programming questions as described below.

## Characteristics of Linear Programs
- **Proportionality**: Proportional scaling by constants.
- **Additivity**: 
- **Divisibility**: Whole number constraint..?

### Canonical Form
$$
\mathrm{min} \ c_1x_1 + c_2x_2 + ... + c_nx_n
\newline
\mathrm{s.t}
\newline
a_{11}x_1 + a_{12}x_2 + ... + a_{1n}x_n \geq b_1
\newline
. 
\newline
. 
\newline
a_{m1}x_1 + a_{m2}x_2 + ... + a_{mn}x_n \geq b_m
$$

In **Standard Form**:
$$
A \in \mathbb{R^{(m \times n)}}, b \in \mathbb{R^m}, x \in \mathbb{R^n}, c \in \mathbb{R^n}
\newline
\mathrm{min} \ c^Tx
\newline
\mathrm{s.t.}
\newline
Ax \geq b
\newline
x \geq 0
$$
## The Diet Problem
*You pick amounts of 4 ingredients to go into chicken feed*
- Let $x_1 = $ # units of ingredient 1
- Let $x_2 = $ # units of ingredient 2
- etc.

*Given minimum requirements of 3 nutrients..* 
- $(6.2, 11.9, 10)$ # units of nutrient 1, 2, 3 respectively.
- Costs of ingredients are $(6.2, 2, 1.6, 3.2)$

Given # units in nutrient/unit g ingredient (WHAT IS THIS?)

| 1.2 | 2.6 | 0 | 9.2 |
|
| 3.9 | 1 | 0.8 | 2
| 6 | 0 | 4 | 3.1

The problem is:
$$
\mathrm{min} \ 6.2x_1+ 2x_2 + 1.6x_3 + 3.2x_4
\newline
\mathrm{s.t.}
\newline
1.2x_1 + 2.6x_2 + 0x_3 + 9.2x_4 \geq 6.2
\newline
3.9x_1 + 1x_2 + 0.8x_3 + 2x_4 \geq 11.9
\newline
6x_1 + 0x_2 + 4x_3 + 3.1x_4 \geq 10
\newline
x_1, x_2, x_3, x_4 \geq 0
$$

## The Transportation Problem
*What is the cheapest way to transport widgets meeting supply and demand*?

**INSERT VISUAL FROM IPAD**

$$
\mathrm{min} \ 8.1x_{\alpha \beta} + 20x_{\delta \alpha} + 3x_{\beta \gamma} + 7.2x_{\beta \delta} + 6x_{\delta \epsilon} + 1.3x_{\epsilon \delta} + 2.2x_{\delta \zeta} + 10x_{\epsilon \zeta}
\newline
\mathrm{s.t.}
\newline
x_{\alpha \beta} + x_{\alpha \gamma} = 3
\newline
-x_{\alpha \beta} + x_{\beta \gamma} + x_{\beta \delta} = 2
\newline
-x_{\alpha \gamma} - x_{\beta \gamma} + x_{\gamma \epsilon} = -1
\newline
-x_{\beta \delta} - x_{\epsilon \delta} + x_{\epsilon \zeta} = 0
\newline
-x_{\delta \epsilon} + x_{\epsilon \delta} + x_{\epsilon \zeta} = 0
\newline
-x_{\delta \zeta} - x_{\epsilon \zeta} = -4
\newline
x_{\alpha \beta}, ...,x_{\epsilon \zeta} \geq 0
$$

In standard form: You define $A, b, c$ are matrices/vectors (**Exercise**)

## Converting types of LP problems
- $\mathrm{max} \iff \mathrm{min}$ is done by negating the objective function, so $f \rightarrow -f$

## Questions
- Take a **serious look** at those linear programming questions again.

## Current Understanding Level
**UNCONFIDENT**. I feel I do "get it" but I couldn't effectively follow along.

