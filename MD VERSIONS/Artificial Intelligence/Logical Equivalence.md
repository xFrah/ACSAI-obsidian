---
alias: Logic Laws, DeMorgan's, Demorgan's Law, Demorgan's Laws, Distributive law, Contrapositive, Contrapositive law, conditional law, associative law
---

Some propositions are equal to others.
We have two ways of checking the equivalence between two proposition:
- By creating a truth table and checking if the outputs are the same
- By using the laws of logical equivalence.


### 1) DeMorgan's Laws

$$\large\lnot (p \land q)  \iff \lnot p \lor \lnot q$$
$$\large\lnot (p \lor q)  \iff \lnot p \land \lnot q$$

> [!hint]
> Saying that at least one must be negative is equal to saying that they can't both be positive.


### 2) Distributive Laws

$$\large p \land (q \lor r) \iff (p \land q)\lor (p \land r)$$

> [!hint]
> Left side: Either $q$ or $r$ must be True in conjunction with $p$.
> Right side: Either $p$ and $q$ is true, or $p$ and $r$ is true.
> 
> You can also think of it as a math formula:
> 
> $$\large3 \cdot (1+2) = (3 \cdot 1) + (3 \cdot 2)$$


### 3) Contrapositive Law

$$\large p \to q \iff \lnot q \to \lnot p$$

> [!hint]
> If $p$ implies $q$, then if $q$ is False, $p$ must be False.
> This is because if $p$ was True, it would have turned $q$ to True also.


### 4) Conditional Law

$$\large p \to q \iff \lnot p \lor q$$

> [!hint]
> If $p$ implies $q$, so when $p$ is true $q$ is also true, 
> then either $q$ is True or $p$ is Negative.


### 5) Associative Law

$$\large p \land (q \land) = (p \land q) \land r$$

