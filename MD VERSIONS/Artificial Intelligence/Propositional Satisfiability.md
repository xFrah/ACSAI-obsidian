---
alias: Satisfiability, Tautology, Contradiction, Entailment
---

When you have a compound proposition, you want to be able to determine **whether it is possible for it to be true**.

For example, the following proposition is unsatisfiable:

$$\large p \land \lnot p$$

> [!abstract] Satisfiability Definition
> A proposition is **satisfiable** if there exists a set of inputs that makes it output "True".

> [!abstract] Tautology Definition
> A **tautology** $φ$ is a proposition that is true in all situations. 
> That is, it is true for all possible values of its variables.
> $$\Large ⊨ φ$$

> [!abstract] Contradiction Definition
> A **contradiction** $φ$ is a proposition that is false in all situations; that is, it is false for all possible values of its variables.
> $$\Large ⊭ φ$$

> [!abstract] Entailment Definition
> A proposition logically entails another if (and only if) **there is no way for the first to be True while the second is False**.
> 
> We say that $φ$ entails $ψ$, or:
> $$\large φ ⊨ ψ \quad \text{otherwise} \quad φ ⊭ ψ$$
> 
> When we have multiple proposition on the left side, we call them **"assumptions"**, and we call the right side **"conclusion"**.
> 
> $$\large \{a \to c,\; b \to c \} ⊨ ψ$$


## How to:

In order to determine the satisfiability of a compound proposition, 