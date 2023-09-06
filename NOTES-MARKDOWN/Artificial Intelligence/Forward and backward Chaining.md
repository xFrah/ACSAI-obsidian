---
alias: Horn Clauses, horn clause, definite clauses, definite clause, goal clauses, goal clause, forward chaining, forward-chaining, backward-chaining, backward chaining, backwards chaining, dpll
---

We can do inference on the horn clauses via forward chaning or backward chaining
Some definitions first:

> [!abstract] Definite Clause Definition
> Definite Clause: disjunction of literals of which exactly one is positive.
> 
> $$\large (\lnot a \lor \lnot b \lor c)$$
> 
> Definite clauses can be rewritten as an implication with the rule:
>
> $$\large \lnot a \lor \lnot b \lor c= (a\land b) \to c$$
> 
> Meaning that we know that the clause is true, so if a and b ar both true, then the only way for it to be true is if c is also true.

> [!abstract] Horn Clause Definition
> Horn clause: disjunction of literals of which at most one is positive.
> 

> [!abstract] Goal Clause Definition
> Goal clauses: Clauses with no positive literals.
> 

---


## Forward chaining

It begins from known positive literals.
Then if all the premises of an implication are known, then its conclusion is added to the set of known facts

If we know $a$ and $b$ and we have this implication
$$\large (a \land b) \to c$$
Then we add $c$ to the knowledge base.
Then we continue recursively.

So in order for this algorithm to work, we want a knowledge base of horn clauses.
Every step/inference is basically an application of [modus ponens](Logical%20Inference.md).

---


## DPLL

1. Turn the proposition in CNF
	1. Eliminate $\to$ and $\iff$
	2. Remove double negations and push negations inward
2. We rewrite in the form of clauses(for convenience)
3. We run DPLL
	0. Check for any false clauses(early termination).
	1. We search for pure literals, when we find one, we kill every clause that has one in itself.
	2. We also search for unit clauses, we kill every one of them(because they are certainly true).
	3. We output all the pure literals that we found and their value, and that is our result.