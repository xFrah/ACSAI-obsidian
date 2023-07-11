---
alias: Prenex Conjunctive Normal Form
---

PCNF stands for Prenex Conjunctive Normal Form. 


## How do we turn from [FOL](First%20Order%20Logic.md) to PCNF?

1. Turn into [NNF](Negational%20Normal%20Form.md)
	1. Eliminate $\to$ and $\iff$
	2. Push negations inward
2. Turn into [Prenex Normal Form](Prenex%20Normal%20Form.md)
	1. Pull quantifiers outward
	2. Put quantifiers in front(after renaming, if needed)
3. Turn into in [CNF](CNF.md)(using distributivity)
