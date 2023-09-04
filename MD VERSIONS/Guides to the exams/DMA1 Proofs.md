## Closure Lemma

### Lemma

A functional dependency $X→Y$ is in the armstrong-extended $F$ if and only if $Y$ is determined by $X$.

$$\large X→Y \in F^A \quad <=> \quad Y\subseteq X^+$$  
> [!hint]
> Obviously, $X→Y$ needs to belong to $F$ before belonging to $F^A$.
> $Y\subseteq X^+$ is equal to saying that the dependency is in $F$.


### Proof

#### "$=>$" - If $X→Y$ is in $F^A$ then $Y \subseteq X^+$

> [!warning]
> The premise here is that  $X→Y$ is in $F^A$.


1) By decomposition rule, we obtain:

$$\large X→K \in F^A \quad \forall K \in Y$$

2) Knowing the definition of $X^+$, we also obtain that:

$$\large K \in X^+ \quad \forall K \in Y$$

> [!hint]
> I guess that the definition of $X^+$ implies this equivalence:
> $$\large X→K \in F^A \quad == \quad K \in X^+$$


3) Which means that :
$$\large Y \subseteq X^+$$

> [!example]
> $$\large X→BC \in F^A$$
> $$\large X→B \in F^A \quad\text{and}\quad X→C \in F^A$$
> $$\large B \in X^+ \quad\text{and}\quad C\in X^+$$
> $$\large BC \subseteq X^+$$


#### "$<=$" - If $Y \subseteq X^+$ then $X→Y$ is in $F^A$ 

> [!warning]
> The premise here is that $Y$ is contained in $X^+$


1. Since $Y \subseteq X^+$, it holds that:

$$\large X→K \in F^A \quad \forall K \in Y$$

2. Wich, by union rule, implies that:

$$\large X→Y \in F^A$$

> [!example]
> $$\large BC \subseteq X^+$$
> $$\large X→B \in F^A \quad\text{and}\quad X→C \in F^A$$
> $$\large X→BC \in F^A$$

---


## Closure inclusion Lemma

### Lemma

If $F$ is dontained in $G^+$, then $F^+$ is also contained in $G^+$.

$$\large \text{If} \quad F \subseteq G^+ \quad \text{then}\quad F^+\subseteq G^+$$
### Proof

> [!warning]
> The premise is that we know that $F\subseteq G^+$ is True.


Let $F'$ be a set of functional dependencies derived by $F$ through the axioms. We indicate this process of deriving by:

$$\large F \rightarrow^{A} F'$$

1) **It holds** that $F'$ can be derived through the axioms from $F$ if and only if $F'$ is in $F^+$.

$$\large F \rightarrow^{A} F' \quad \text{iff} \quad F\subseteq F^+$$

> [!hint]
> Since $F^+$ contains all possible derivate dependencies of $F$, if $F'$ was derived from $F$, it must be a subset of $F^+$.


2) **This implies** that $F^+$ can be derived from $F$ through the axioms.

$$\large F \rightarrow^{A} F^+$$

3) Now we have demonstrated that we can get $F^+$ from $F$. If we can get $F$ from $G$, then we know that we can get $F^+$ from $G$.

$$\large F \subseteq G^+ \quad \text{iff} \quad G→^A F→^AF^+$$

> [!hint]
> The premise here is that $F\subseteq G^+$ is True, so $G→^A F→^AF^+$ is also True.


4) $G→^A F→^AF^+$ being true means that we can get $F^+$ from $G$, and so $G^+$ also contains $F^+$.

$$\large F^+ \subseteq G^+$$

---


## $F^A=F^+$

### Theorem

$F^+$ is equal to $F^A$.

### Proof (By double inclusion)

#### $F^A \subseteq F^+$

##### Base case(n=0):
We don't use any axiom, $X→Y$ already belongs to $F$ and also to $F^+$.

> [!hint]
> Are there dependencies in $F^A$ that we can obtain with 0 applications of the axioms? YES! The ones in $F$.


##### Induction case:
Here we are assuming that the dependencies obtained with n applications of the axioms are already in both $F^A$ and $F^+$.

What we are trying to do is apply the axioms another time(n+1) and prove that the resulting dependencies are in $F^+$.


###### Reflexivity
We are obtaining $X→Y \in F^A$ because $Y$ is part of $X$.

