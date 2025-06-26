# [CSPs](CSPs.md)

![](../z_images/Pasted%20image%2020240613173017.png)

> [!hint]
> When he says draw the graph, draw an undirected graph with domains attached.
> 

![](../z_images/Pasted%20image%2020240613174245.png)

> [!hint] How to represent constraints
> Represent a generic state as $R_i$ and say for each state $R_j$ in the neighbors of $R_i$.
> 
> Also divide by type: unary, binary...
> 

> [!summary] Type of constraints
> - **Unary**
> - **Binary**
> - **Higher order**


### Constraints:
**Unary**:
- $R_1 = c$
- $R_7 = i$
- $R_8=t$

**Binary**:
- $\underbracket{\forall R_i=\{i,t\},}_{\text{which states to constraint?}} \forall \underbracket{R_j \in Neighbors(R_i)}_{\text{for each neighbor}}:\underbracket{R_j \neq \{c\}}_{\text{constraint}}$
- $\forall R_i=\{c\}, \;\forall R_j \in Neighbors(R_i) : R_j \neq {i,t}$
- $\forall R_i, \;\forall R_j \in Neighbors(R_i) : R_i \neq R_j$

## AC-3

1. Analyze every arc, they are bidirectional so we have twice the checks.
2. Dequeue: **check** if the node on the **left has a domain change**. If it does, **put in queue** again all the **arcs with that node on the right**(if they are not in the queue)

---
# [Propositional Logic](Propositional%20Logic.md)
## Checking entailments (Reductio at absurdum)

![](../z_images/Pasted%20image%2020240612112614.png)

### 1.
> [!hint]
> If $X \land  Y$ is true, then $Y$ is true.


Since $Y$ can be false when $X∨Y$ is true, the entailment does not hold.

### 2. 

We try to prove that the following formula is unsatisfiable(reductio at absurdum):

$$\large \lnot X \lor (Y \land Z) \land \lnot (X \rightarrow Y)$$

The outer node is an AND so both sides need to be true.
The only way that $\lnot (X \rightarrow Y)$ is true, is if $X$ = True and $Y$ = False.
For the other side to be true, we either need $Y$ and $Z$ to be true, but this is not possible since $Y$ should be False, OR we need $X$ to be false, and this is not possible since $X$ should already be false.

> [!hint]
> $$\large \underbracket{\lnot X}_{X=False} \lor \underbracket{(Y \land Z)}_{Y=True, \;Z=True} \land \underbracket{\lnot (X \rightarrow Y)}_{X = True,\;Y=False}$$
> 
> The two $X$ or two $Y$ would need to have 2 different assignments and that's not possible.


## Truth tables, [CNF](CNF.md)

![](../z_images/Pasted%20image%2020240612181307.png)

> [!hint]
> When the professor talks about **enumeration**, he's telling you to make a **truth table**.

> [!abstract] Valid vs Satisfiable
> - A formula is **satisfiable** if at least one assignment makes it true.
> - A formula is **valid** if every assignment makes it true(it is a tautology).

### 1.
| Food | Drinks | Party | Entire Sentence |
|------|--------|-------|-----------------|
| T    | T      | T     | T               |
| T    | T      | F     | T               |
| T    | F      | T     | T               |
| T    | F      | F     | T               |
| F    | T      | T     | T               |
| F    | T      | F     | T               |
| F    | F      | T     | T               |
| F    | F      | F     | T               |
The sentence is valid.

> [!danger]
> We might need to include all the clauses, not just the entire sentence's result.


### 2.

> [!summary] CNF summary
> How do we turn a formula into Conjunctive Normal Form?
> 1. We substitute ↔ with $(α→β)∧(β→α)$
> 2. We substitute → with $¬α∨β$
> 3. We allow ¬ only in front of single symbols. (using double negation or [De Morgan](../Computer%20Architecture%201/7.%20De%20Morgan's%20Theorem.md)'s)
> 4. Apply distributivity to make it like this:
>    
>    $$\large (¬B1,1 ∨ P1,2 ∨ P2,1) ∧ (¬P1,2 ∨ B1,1) ∧ (¬P2,1 ∨ B1,1)$$

We turn the left hand side and right hand side of the following formula into CNF:

$$\large [(f \rightarrow p) \lor (d \rightarrow p)] \rightarrow [(f \land d) \rightarrow p]$$
1. There are no $↔$.
2. We remove the implications:

$$\large (\lnot f \lor p) \lor (\lnot d \lor p); \quad \lnot(f \land d) \lor p$$

3. We limit $\lnot$'s to symbols only:

$$\large (\lnot f \lor p) \lor (\lnot d \lor p); \quad (\lnot f \lor \lnot d) \lor p$$

> [!hint]
> We used De Morgan's law.
> 
> $$\large \lnot (a \land b) = \lnot a \lor \lnot b$$
> $$\large \lnot (a \lor b) = \lnot a \land \lnot b$$


4. Apply distributivity(there is no distributivity to apply here):

$$\large \lnot f \lor p \lor \lnot d;\quad \lnot f \lor \lnot d \lor p$$

> [!hint]
> Distributivity is like multiplication of a sum with a scalar.
> 
> $$\large a\cdot (b + c) = ab + ac$$
> $$\large a\lor (b \land c) = (a \lor b) \land (a \lor c)$$
> $$\large a\land (b \lor c) = (a \land b) \lor (a \land c)$$
> 
> The $\cdot$ becomes whatever is outsite the parenthesis.
