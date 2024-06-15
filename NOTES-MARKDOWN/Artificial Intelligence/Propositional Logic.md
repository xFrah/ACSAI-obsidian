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

## Satisfiability

When you have a proposition, you want to be able to determine **whether it is possible for it to be true**.

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

> [!example] Solving Satisfiability problems
> In order to prove satisfiability, we can either use:
> - Truth tables
> - Proof by contradiction
> 
> ### Contradiction check
> We want to prove that:
> 
> $$\large \{a → c, b → c\} ⊨ (a ∨ b) → c$$
> 
> We do that by checking the unsatisfiability of $(\alpha \land \lnot \beta)$:
> 
> $$\large (a → c) ∧ (b → c) ∧ ¬ ((a ∨ b) → c)$$
> 
>  Is this a contradiction?
>  For it to be true, it would need:
>  1. $ν (a → c) = T$ 
>  2. $ν (b → c) = T$
>  3. $ν (a ∨ b) → c = F$
>  
>  For $ν (a ∨ b) → c$ to be false, we need that $a \lor b$ is True and $c$ is False.
>  But then:
> - $ν (a → c) = F$, contradicting point 1.
> - $ν (b → c) = F$, contradicting point 2.
> 
>  ### Truth tables method
>  Algorithm for checking whether a proposition entails another or not.
>  We just build a truth table that contains every possible input combination/model.
>  
>  > [!hint]
>  > It's just a bruteforce.
> 
>  
>  For every mode, we check the entailment(if second proposition is False, the first must also be False).
>  If the condition is true for every model, then we have an entailment.
> 

> [!summary] Entails vs Implies
> - **Entailment** ($⊨$) refers to a truth relationship between propositions.
> - **Implication** ($→$) refers to a logical relationship within propositional logic.

---

## Inference

A deductive system is defined by a set of formulae called axioms and a set of Inference Rules.

These inference rules can be applied to derive a proof, which is a chain of conclusion that leads to the desired goal(in our case [SAT problems](Propositional%20Satisfiability.md) conclusions).

> [!note]
> If a formula $φ$ can be deduced from a set of formulae $Γ$ in a deductive system $D$, we say that $φ$ is a deductive consequence of $Γ$ in $D$, denoted with:
> $$\large Γ ⊢_D φ$$


### 1) Modus Ponens

$$\large\frac{{P \to Q \quad P}}{{Q}}$$

If we have $P$, and $P$ implies $Q$, then we can deduce $Q$.

> [!hint]
> We know $P$ is True.
> So in this case $Q$ can only be True.


### 2) Modus Tollens

$$\large\frac{{P \to Q \quad \lnot Q}}{{\lnot P}}$$

We know that $Q$ is False, hence $P$ can only be False.

> [!hint]
> Because if $P$ was True, it would have turned $Q$ True too.


### 3) Disjunctive Syllogism

$$\large\frac{{P \lor R \quad \lnot R}}{{P}}$$


> [!hint]
> Either $P$ is True or $R$ is true.
> We know that $R$ is False so $P$ must be True.


### 4) Conjunction Introduction

$$\large\frac{{Q \quad P}}{{P \land Q}}$$

> [!hint]
> We know that $P$ is True and $Q$ is True, so an $\land$ between the two must also be True.


### 5) Conjunction Elimination

$$\large\frac{{P \land Q}}{{P}} \quad \frac{{P \land Q}}{{Q}}$$

> [!hint]
> If the $\land$ is True, both components must be True.


### 6) Disjunction Introduction

$$\large\frac{{P}}{{P \lor Q}}$$

> [!hint]
> $P$ is True, so $P$ or $Q$ must be True.


### 7) Double Negation

$$\large \lnot \lnot D= D$$


### 8) Contraposition

$$\large\frac{{P \to Q}}{{\lnot Q \to \lnot P}}$$

> [!hint]
> We know that if $P$ is True, $Q$ is also True.
> So can deduce that if $Q$ is False, $P$ must be False, or it would have turned $Q$ to True.

---

## Forward chaining

It begins from known positive literals.

> [!abstract] Literal Definition
> A variable or negation of a variable is called a Literal.
> 
> $$\large p \quad \text{or}\quad \lnot p$$


If all the premises of an implication are known, then its conclusion is added to the set of known facts:

1. Assume we have this implication
$$\large (a \land b) \to c$$
2. If we know $a$ and $b$, then we add $c$ to the knowledge base.
3. We continue recursively.

In order for this algorithm to work, we want a knowledge base of horn clauses.
Every step/inference is basically an application of [modus ponens](Logical%20Inference.md).

> [!abstract] Clause
> A Clause is a disjunction of Literals.
> 
> $$\large l_1 ∨ l_2 ∨ ⋯ ∨
l_n$$

> [!abstract] Definite Clause Definition
> Exactly one literal is positive.
> 
> $$\large (\lnot a \lor \lnot b \lor c)$$
> 
> Definite clauses can be rewritten as an implication with the rule:
>
> $$\large \lnot a \lor \lnot b \lor c= (a\land b) \to c$$
> 
> Meaning that we know that the clause is true, so if a and b ar both true, then the only way for it to be true is if c is also true.

> [!abstract] Horn Clause Definition
> At most one literal is positive.
> 

> [!abstract] Goal Clause Definition
> No positive literals.
> 


## DPLL

### Preliminary operations
1. Turn the proposition in [CNF](CNF.md)
2. We rewrite in the form of clauses(for convenience)

### Running DPLL

0. Check for any false clauses(early termination).
1. We search for pure literals, when we find one, we kill every clause that has one in itself.
2. We also search for unit clauses, we kill every one of them(because they are certainly true).
3. We output all the pure literals that we found and their value, and that is our result.