# Intro to Optimization - Class 2
2026-09-02

## Outline
- More on sets and neighborhoods
- Defining minimizers

## Learning Objectives
- I can use definitions to classify sets (open, closed, both, neither) and classify optimizers (global/local, strict/non-strict)

## More on Neighborhoods
**Def**: 

A set $S \subset \mathbb{R^n}$ is **bounded** precisely when $\exists \epsilon > 0$ s.t. $S \subset N_{\epsilon}(0)$

$S$ is **open** $\iff$ $\forall x \in S$, $x$ is an interior point of $S$

$S$ is **closed** $\iff$ every boundary point of $S$ is in $S$

>Note sets can be **neither** open nor closed. Similarly, sets can be **both** open and closed. Also, interestingly, a set need not be bounded to be closed.

**Remark**: 
- It is easier to deal with the calculus of open sets, since no matter where you are in the set, you can find a small enough neighborhood to take a small step.
- But if $S$ is closed and bounded (**compact**), and $f: S \rightarrow R$ is continuous, there exists optimal solutions to $\mathrm{min}_{x \in S}f(x)$ and $\mathrm{max}_{x \in S}f(x)$

**Proposition**: $S \subset \mathbb{R^n}$ is open $\iff S^c $ is closed

## Defining Minimizers

Let $P := \mathrm{min}_{x \in S}f(x)$

**Def**: Suppose $S \subset \mathbb{R^n}$ and $f: S \rightarrow \mathbb{R}$. $x^*$ is called the **global minimzer** of $P$ precisely when $\forall x \in S$, $f(x^*) \leq f(x)$
- Call $x^*$ the **strict global minimzer** of $P$ precisely when $\forall x \in S$ s.t. $x \neq x^*$, $f(x^*) < f(x)$ (this is equivalent to **uniqueness**)

Call $x^*$ a **local minimizer** of $P$ precisely when $\exists \epsilon > 0$ s.t. $\forall x \in S \cap N_\epsilon(x^*)$, $f(x^*) \leq f(x)$ (there is some neighborhood around which $x^*$ is optimal)
- Call $x^*$ the **strict local minimizer** of $P$ when $\exists x \in S \cap N_\epsilon(x^*)$ s.t. $x \neq x^*$, $f(x^*) \lt f(x)$

## Questions
- Explore what it further means for a set to be "bounded"
- Rederive the proposition $S$ open $\iff S^c$ closed