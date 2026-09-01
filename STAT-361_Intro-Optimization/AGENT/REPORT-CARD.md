# STAT 361 Report Card

## 2026-09-01 — Class 1: Preliminaries

### Recall gaps

- Initially omitted the feasibility requirement \(x^*\in S\) from the formal definition of an optimal solution.
- Initially described the feasible region for \(\min \log x\) subject to \(1<x\le 7\) as points on the graph of \(\log x\). Reinforce that the feasible region \(S=(1,7]\) contains decision-variable values; the graph and objective values are separate objects.
- Needs precision distinguishing a lower bound from an attained minimum. A lower bound \(c\) becomes a minimum when there exists a feasible \(x^*\in S\) such that \(f(x^*)=c\).
- Used “the objective function must be defined at the lower bound,” which mixes the objective-space value \(c\) with a decision-space input. Review decision vectors versus objective values.
- Initially called \((1,7]\) open. Reinforce that it is neither open nor closed in \(\mathbb R\); both 1 and 7 are boundary points, although only 7 belongs to the set.

### Application gaps

- No significant application errors. Correctly formalized a two-variable production problem by identifying the decision vector, objective, constraints, and feasible region.

### Demonstrated strengths

- Correctly identified the objective function, decision variables, and constraints/feasible region as the ingredients of an optimization problem.
- Correctly distinguished the optimal solution \(x^*\) from the optimal objective value \(f(x^*)\).
- Correctly defined boundedness below using quantifiers.
- Correctly reasoned that \(\log x\) on \((1,7]\) has infimum 0 but no minimizer because 0 is not attained.
- Accurately recalled the epsilon-neighborhood definitions of interior and boundary points.

### Future recall prompts

1. State the complete quantified definition of a minimizer, including feasibility.
2. Explain the difference among a lower bound, the infimum, and an attained minimum.
3. Given a constraint set, identify its interior and boundary and determine whether it is open, closed, both, or neither.
4. Given a verbal optimization problem, separately identify the decision space, feasible region, objective function, optimizer, and optimal objective value.
