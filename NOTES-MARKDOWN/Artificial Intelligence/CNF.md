---
aliases:
  - Conjunctive normal form
---
![[Pasted image 20251124083333.png]]

We can translate any formula into its Conjunctive Normal Form. 

### 1. Kill ↔
Substitute ↔ with $(α→β)∧(β→α)$

### 2. Kill →
Substitute → with $¬α∨β$

### 3. Kill outer ¬'s
We allow ¬ only in front of single symbols. (using double negation or [[Logical Equivalences|De Morgan's]]

### 4. Apply distributivity
Apply distributivity to make it like this:

$$\large (¬B1,1 ∨ P1,2 ∨ P2,1) ∧ (¬P1,2 ∨ B1,1) ∧ (¬P2,1 ∨ B1,1)$$

> [!hint]
> Distributivity is like multiplication of a sum with a scalar.
> 
> $$\large a\cdot (b + c) = ab + ac$$
> $$\large a\lor (b \land c) = (a \lor b) \land (a \lor c)$$
> $$\large a\land (b \lor c) = (a \land b) \lor (a \land c)$$
> 
> The $\cdot$ becomes whatever is outsite the parenthesis.
