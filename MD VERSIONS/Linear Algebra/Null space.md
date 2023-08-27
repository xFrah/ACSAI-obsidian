---
alias: nullspace, nullspaces, null spaces
---

If $A$ is an $m$x$n$ [matrix](Matrix%20(ML).md), then the set of all solutions of the homogeneous [system of linear equations](Systems%20of%20Linear%20Equations.md) $Ax=0$ is a subspace of $R^n$ called the null space of $A$ and denoted by $\text{N}(A)$.

> [!note]
> The dimension of the null space is called the **nullity** of $A$.

> [!hint] Intuitive explanation
> When a [matrix](Matrix%20(ML).md) isn't full [rank](Rank.md), meaning that it has a zero [determinant](Determinant.md) and collapses the space, some [vectors](Vectors.md) go to zero.
> 
> The **set of vectors that goes to zero** after this transformation is called the null space.
> 
> The expression...
> 
> $$\large Ax=0$$
> 
> ... quite literally means "What is the vector $x$ that when transformed by $A$ goes to zero?".

---

## Lil theorem

$$\large \text{rank}(A) + \text{nullity}(A) = \text{number of columns}$$