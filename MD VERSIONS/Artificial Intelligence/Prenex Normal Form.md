---
alias: PNF
---

It basically has the quantifiers only in front.

> [!example]
> $$\large ∃x\,\text{King}(x) ∧ ∃x\,\text{Crown}(x)\text{ is not in prenex form}$$
> $$\large ∃x∃y\; (\text{King} (x) ∧ \text{Crown} (y)) \text{ is in prenex form}$$
> 
> The two are equivalent.
> Sometimes we need to rename variables in order to achieve prenex form.


In order to turn a thing into Prenex form, we must:
1. Use equivalences(after renaming maybe) to pull quantifiers outwards.
2. Use formulas to put quantifiers in front of the formula(after renaming, maybe).

> [!note] The equivalences for step 1
> 
> $$\large ∀x (φ) ∧ ∀x (ψ) ≡ ∀x(φ ∧ ψ)$$
> $$\large ∃x (φ) ∨ ∃x (ψ) ≡ ∃x(φ ∨ ψ)$$

> [!note] The formulas for step 2
> $$\large ∀x (φ) ∧ ψ ≡ ∀x(φ ∧ ψ)$$
> $$\large ∀x (φ) ∨ ψ ≡ ∀x(φ ∨ ψ)$$
> $$\large ∃x (φ) ∧ ψ ≡ ∃x(φ ∧ ψ)$$
> $$\large ∃x (φ) ∨ ψ ≡ ∃x(φ ∨ ψ)$$
