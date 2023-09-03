## Closure Lemma

### Lemma:

A functional dependency $X→Y$ is in the armstrong-extended $F$ if and only if $Y$ is determined by $X$.

$$\large X→Y \in F^A \quad <=> \quad Y\subseteq X^+$$  
> [!hint]
> Obviously, $X→Y$ needs to belong to $F$ before belonging to $F^A$.
> $Y\subseteq X^+$ is equal to saying that the dependency is in $F$.


### Proof

#### "$=>$"


1) By decomposition rule, we obtain:

$$\large X→A \in F^A \quad \forall A \in Y$$

> [!example]
> We are just changing the left side by splitting the dependency.
> $$\large X→B \in F^A \quad\text{and}\quad X→C \in F^A$$

2) Knowing the definition of $X^+$, we also obtain that:

$$\large A \in X^+ \quad \forall A \in Y$$

> [!example]
> $$\large B \in X^+ \quad\text{and}\quad C\in X^+$$

> [!hint]
> I guess that the definition of $X^+$ implies this equivalence:
> $$\large X→Y \in F^A \quad == \quad Y \in X^+$$


3) Which means that :
$$\large Y \subseteq X^+$$

> [!example]
> $$\large BC \subseteq X^+$$


