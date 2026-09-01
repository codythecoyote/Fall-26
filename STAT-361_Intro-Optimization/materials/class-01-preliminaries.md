# Intro Optimization - Class 1
## Outline
- Generalizing optimization questions
- Boundedness and Feasibility
- Topology

## Key Learning Objectives
- I can generalize "toy" optimization problems seen in past Calculus courses into a more formal notion of optimization problems.
- I know how to draw the feasible region of simple optimization problems.
- I understand what it means for an optimization problem to be feasible and can determine whether it is for simple cases.
- I understand formal and intuitive definitions for basic topological concepts.
## A Simple Optimization Example

*"There is 100 ft of fence available to enclose a rectangular area. Let $x$ denote the North/South length, and $y$ denote the East/West. The North/South side must be at least as long as East/West. Find dimensions $x, y$ that maximize the enclosed area"*

- Formally, we may write the task as the **objective function** constrained by requirements on **decision variables**.
$$
\mathrm{max}(xy) \ \mathrm{s.t.}
\newline
2x + 2y \leq 100
\newline
x \geq y
\newline
x \geq 0
\newline
y \geq 0
$$
- There exists a **feasible region** (draw it) that meets the constraints, but here there is one solution that optimizes the objective function $xy$

## General Optimization Problem
Given a feasible region $S \subset R^n$, an objective function $f: S \rightarrow R$, find the decision variables $x \in S$ that maximize or minimize the objective function value.
- **Minimization task**: An optimial solution of $P: \mathrm{min}f(x) \ \mathrm{s.t.} \ x \in S$ is an $x^* \in S$ such that $\forall x \in S, f(x^*) \leq f(x)$. We say the **optimal objective function value is** $f(x^*)$

## Boundedness and Feasibility
$\mathrm{min \ log}x \ \mathrm{s.t.} \ 0 < x \leq 7$
- Objective function is *unbounded below*. No solution exists.

$\mathrm{min \ log}x \ \mathrm{s.t.} \ 1 < x \leq 7$
- Objective function is *bounded* below. Still no soln exists.

$\mathrm{min \ log}x \ \mathrm{s.t.} \ x > 1, x \leq \frac{1}{2}$
- **Infeasible** problem, meaning feasible region is empty (no soln)

## Topology

$\forall x \in \mathbb{R^n}$, the **Euclidean Norm** of $x$ is:

$$
||x|| = (\sum_{i=1}^{n}x_i^2)^\frac{1}{2}
$$

- Intuitively this is the *length* of $x$

$\forall x,y \in \mathbb{R}^n$, the **Euclidean Distance** between $x,y$ is:
$$
||x-y||
$$

$\forall x \in \mathbb{R^n}, \epsilon > 0$, the **epsilon neighborhood** of $x$ is:
$$
N_{\epsilon}(x) = \{y \in \mathbb{R^n} : ||x-y|| < \epsilon\}
$$
- the set of points within $\epsilon$ of $x$

For any $S \subset \mathbb{R^n}, x \in \mathbb{R^n}$ is an **interior point** of $S$ precisely when:

$\exists \epsilon > 0 \ \mathrm{s.t.} \ N_{\epsilon}(x) \subset S$

A **boundary point** when:

$$
\forall \ \epsilon > 0, N_\epsilon(x) \cap S \neq \empty
\newline
\mathrm{and}
\newline
N_{\epsilon}(x) \cap S^c, \neq \empty 
$$

## Questions
