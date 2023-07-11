---
alias: NNF
---

Every propositional formula is equivalent to a formula where:
- Negation appears only in front of propositional symbols.
- There are no occurrences of $→$ and $↔$.

---


## Translation algorithm

### Kill $→$ and $↔$

We use
$$\large φ ↔ ψ ≡ (φ → ψ) ∧ (ψ → φ)$$
and

$$\large φ → ψ ≡ ¬φ ∨ ψ$$

### Put negations only in front of symbols

Push negation inward by using
logical equivalences for
negation.


> [!note]
> The logical equivalences for negations are:
> $\large ¬ ¬φ ≡ φ$
> $\large ¬ φ ∨ ψ ≡ ¬φ ∧ ¬ψ$
> $\large ¬ φ ∧ ψ ≡ ¬φ ∨ ¬ψ$
> $\large ¬ φ → ψ ≡ φ ∧ ¬ψ$
> $\large ¬ φ ↔ ψ ≡ φ ∧ ¬ψ ∨ (¬φ ∧ ψ)$

---


## NNF for [FOL](First%20Order%20Logic.md)

In order to turn a FOL thing into [Negational Normal form](Negational%20Normal%20Form.md), we must:

![](../z_images/Pasted%20image%2020230711183107.png)

> [!example]
> ![](../z_images/Pasted%20image%2020230711183631.png)
> 
> Basically when we use one of the rules above to push the negations inward, we just invert the quantifier.
