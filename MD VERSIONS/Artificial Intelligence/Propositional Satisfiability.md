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

> [!example] Contradiction check
> $$\large (a → c) ∧ (b → c) ∧ ¬ ((a ∨ b) → c)$$
> 
> Is this a contradiction?
> For it to be true, it would need:
> 1. $ν (a → c) = T$ 
> 2. $ν (b → c) = T$
> 3. $ν (a ∨ b) → c = F$
> 
> For $ν (a ∨ b) → c$ to be false, we need that $a \lor b$ is True and $c$ is False.
> But then:
> - $ν (a → c) = F$, contradicting point 1.
> - $ν (b → c) = F$, contradicting point 2.



## TT-ENTAILS

Algorithm for checking whether a proposition entails another or not.
We just build a truth table that contains every possible input combination/model.

> [!hint]
> It's just a bruteforce.


For every mode, we check the entailment(if second proposition is False, the first must also be False).
If the condition is true for every model, then we have an entailment.