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

Push negation inward by using [logical equivalences](Logical%20Equivalences.md) for negation.


> [!note]
> The logical equivalences for negations are:
> $\large ¬ ¬φ ≡ φ$
> $\large ¬ φ ∨ ψ ≡ ¬φ ∧ ¬ψ$
> $\large ¬ φ ∧ ψ ≡ ¬φ ∨ ¬ψ$
> $\large ¬ φ → ψ ≡ φ ∧ ¬ψ$
> $\large ¬ φ ↔ ψ ≡ φ ∧ ¬ψ ∨ (¬φ ∧ ψ)$

