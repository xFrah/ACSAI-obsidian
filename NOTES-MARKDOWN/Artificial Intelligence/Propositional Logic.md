A logic based on propositions, sentences or statements.

## Syntax

- ⊥ = True
- ⊤ = False

- ¬ = Not
- ∧ = And
- ∨ = Or
- → = Implies
- ↔ = Co-Implies

Once the propositional symbols are assigned a truth value, the truth value of the formula can be determined.

### Operator precedence

$$\large \lnot, \; \land, \;\lor,\;→, \;↔$$

## Construction tree of a formula

![](../z_images/Pasted%20image%2020240610200031.png)

## Satisfiability

If an assignment $ν$ of symbols makes a formula true, we say that $ν$ satisfies $φ$, denoted by:
$$\large ν⊨φ$$

A formula is satisfiable if it is satisfied by any assignment.

> [!example]
> Given $φ=(a∨b)∧¬c$, $φ$ is satisfiable by $ν={(a,T),(b,F),(c,F)}$.
> Formula φ′= a ∧ b ∧ ¬a is not satisfiable.

> [!summary] Model definition
> An assignment/valuation $ν$ such that $ν⊨φ$ is also called a model of $φ$.

## Tautology

Formula $φ$ is a tautology if every assignment makes it true.
It's denoted as:
$$\large ⊨φ$$
on the other hand, the formula is a contradiction/unstatisfiable if it doesn't have any assignment that makesi t true.


## Deduction theorem

$φ⊨ψ$ is true if and only if the sentence $φ → ψ$ is always true.

How do we check that $φ → ψ$?
We either:
- **Model-checking**: Check if for every possible assignment that makes $φ$ true(models of $φ$), $ψ$ is true too.
- **Theorem-proving**: Search for a series of steps that lets us derive $ψ$ from $φ$.

> [!summary] Entails vs Implies
> - **Entailment** ($⊨$) refers to a truth relationship across all possible models.
> - **Implication** ($→$) refers to a logical relationship within propositional logic.
>   
>   > [!example]
> > ### ?

---

# Exercises

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


## Truth tables, CNF

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

### 2.

> [!summary] CNF
> How do we turn a formula into Conjunctive Normal Form?
> 1. We substitute ↔ with 
> 2. We substitute → with 
> 3. We allow ¬ only in front of single symbols.




