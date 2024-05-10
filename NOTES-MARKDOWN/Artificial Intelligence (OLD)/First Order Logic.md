---
alias: FOL
---

![](../z_images/Pasted%20image%2020230710182554.png)


## Constants

Instances of objects.


## Variables

Placeholders for constants in formulas.


## Predicates

A predicate is a statement or mathematical assertion that contains variables.

> [!example]
> $$\large x \;\text{is a philosopher} = Philosopher(x)$$


## Quantifiers

There are two types of quantifiers.
- Universal quantifier $∀x$: The statement is true for all constants.
- Existential quantifier $∃x$: The statement is true for at least one constant.

> [!hint]
> $$\large ∀x \;\lnot Likes(x, Parsnips) = \lnot ∃x \;Likes(x, Parsnips)$$


## Equality

We can use the equality symbol to sifnify that two terms refer to the same object.

> [!example]
> $$\large Father(John) = Henry$$

---


## Interpretation of FOL

We name the pair $(Δ, \mathcal{I})$ as a structure $\mathcal{S}=(Δ, \mathcal{I})$.
Where
- $\mathcal{I}$ is the set that contains the [functions](Functions.md), elements and relations
- $\Delta$ is the set that contains all the outputs and inputs of functions

We also have the set $\alpha$, which contains the assignments for each variable.

> [!example]
> $$\large \Delta = \{1, 2\}$$
> $$\large \alpha(x) = 1,\quad \alpha(y) = 2$$

---


## Satisfiable, Valid or Unsatisfiable

> [!abstract] Definition of Satisfiable
> A formula $ψ$ is satisfiable if there is some structure $\mathcal{S}$ and some assignment $α$ such that $(\mathcal{S}, α) ⊨ ψ$.
> 
> $$\large ∀x \;P(x)\;\; \text{is Satisfiable}$$
> 
> This translates to: For every constant, $P(x) = \text{True}$, which can be true if we choose the constant and function wisely.
> 
> For example it can be true if $P(x) = x > 1$ and $\text{constants} = \{2\}$.

> [!abstract] Definition of Valid
> A formula $ψ$ is valid if, for every structure $\mathcal{S}$ and assignment $α$, $(\mathcal{S}, α) ⊨ ψ$.
> 
> $$\large ∀x\; P(x) → ∃y\; P(y)\;\; \text{is Valid}$$
> 
> This translates to: If $P(c)$ is true for all constants, then $P(c)$ is True for at least one constant.
> 
> This is valid for all structures and assignments, because the constants of $x$ and $y$ are the same, so at one point $x = y$, making the statement True.

---
