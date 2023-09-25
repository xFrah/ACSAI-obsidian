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

> [!hint]
> We know for sure that the dependency is in $F^A$, because we obtained i through axioms, now we gotta demonstrate that it's also in $F^+$.


We know that the dependencies in $F^+$ need to satisfy every legal instance of $R$, so we need to ensure that by using a random dependency.

$X→Y$ is legal in $R$ if:

$$\large t_1[x]=t_2[x] →t_1[y]=t_2[y]$$

In the case of reflexivity, this is always true, because $Y$ is part of $X$.


###### Augmentation
We are obtaining $X→Y \in F^A$ through augmentation, which means that we had a dependency $V→W \in F^+$ and we augmented it to $VZ→WZ \in F^A$.

We need to prove that this dependency belongs to $F^+$.

> [!hint]
> Remember that in this case $X=VZ$ and $Y=WZ$.


We prove that $X→Y$ belongs to $F^+$ because:

### WIP

#### $F^A \supseteq F^+$

We want to demonstrate that every dependency in $F^+$ is also in $F^A$.

![](../z_images/Pasted%20image%2020230906161744.png)

Per assurdo questa instanza non è legale.
In order for $r$ to be illegal, we would need to have a dependency such that:
$$\large V→W \in F\quad \text{and} \quad t_1[V]=t_2[V] => t_2[W] \neq t_2[W]$$

Let's demonstrate that this is impossible.
For $r$ to be illegal, we would need to have that:
- $V$ is a subset of $X^+$ and $W$ belongs to $R-X^+$.

We have a contradiction:
1. $V \subseteq X^+$
2. $X → V \in F^A$(LEMMA 1).
3. $V→W \in F$
4. $X→W \in F^A$
5. $W \subseteq X^+$ CONTRADICTION.

---


## Closure of X

### Theorem

The algorithm outputs $X^+_F$.


### Proof

We use 2 sets in the algorithm:
- $Z$: Attributes **already included** in the result at current iteration.
- $S$: Attributes that **will be added** to the result at the current iteration.

We want to prove that $Z_f = X^+$.
We do so by double inclusion and by induction on the number of iterations.


#### $Z_f \subseteq X^+$

##### Base case($i=0$):q
At the start, we have that $Z$ contains the attributes of $X$.
$$\large Z_0=X\subseteq X^+$$
So **by reflexivity** we have that $Z_0 \subseteq X^+$.


##### Induction case:
We assume that $Z_i \subseteq X^+$ and prove that $Z_{i+1}\subseteq X^+$.

$$\large Z_{i+1}=Z_i \cup S_i$$

Let $A$ be an attribute in $Z_{i+1}$.
- If $A \subseteq Z_i$ we are done, $A$ **was already in** $Z$ and proven to be in $X^+$.
- If $A \subseteq S_i$ it means that $A$ **was added in the current iteration**.

In this second case, there must exist a dependency $Y→V \in F$ such that $Y \subseteq Z_i$ and $A \in V$.

> [!hint] Explanation of last statement
> We added $A$ in the last iteration, so it means that it must be in the right part $V$ of some dependency $Y→V$, whose left part $Y$ is already in $Z_i$.


So we have found out that $Y$ is contained in $Z$ and $Z$ is contained in $X^+$:
$$\large Y \subseteq Z_i \subseteq X^+ \quad \text{or} \quad Y \subseteq X^+$$
1.  $X→Y \in F^A$ by lemma 1.
2.  $X→V \in F^A$ by transitivity.
3.  $V\subseteq X^+$ by lemma 1. 
4.  $A \in V \subseteq X^+$.

We just proved that any attribute $A$ that is in $Z_{i+1}$ is also part of $X^+$.


#### $Z_f \supseteq X^+$

> [!warning]
> The premise here is that we have just demonstrated that $Z_f \subseteq X^+$.


We need to demonstrate that $A \in X^+ => A \in Z_f$.

> [!hint]
> That every element that is in $X^+$ is also in $Z_f$.


By lemma 1, from $A \in X^+$ we obtain that $X→A \in F^A$.
But now we also know that $F^A$ is equal to $F^+$.

Since it belongs to $F^+$, $X→A$ needs to be legal for every instance of $R$.

![](../z_images/Pasted%20image%2020230907080014.png)


Facciamo per assurdo, that exists a dependency $V→W$ that is not satisfacted.

It would need to have $V \subseteq Z_f$ and an intersection of $W$ in $R-Z_f$.

The problem here, is that if we have a dependency that is in $Z_f$ that determines something that is outside $Z_f$, it means that **the algorithm hasn't terminated**, because something is yet to be added to $Z_f$.

This is a contradiction.


---


## Closure of $X^+_G$

#### $Z_f \subseteq X^+_G$
##### Base case($i=0$):

$Z_0$ is equal to $X$ and $X \subseteq X^+_G$ by definition so this holds.


##### Induction case:
$Z_i \subseteq X^+_G$ is True and we gotta prove that $Z_{i+1} \subseteq X^+_G$.

Let $A$ be an attribute inside $Z_{i+1}$, which could come from either $Z_i$ or $S_i$.
- $A\in Z_i$, the statement holds.
- $A \in S_i$, we must still prove that it belongs to $X^+_G$.


If $A \in S_i$, then by definition it was added in a step of the type $(Z_i\cap R_j)^+_F \cap R_j$.

Since it's an intersection, this means that $A$ is in both sides:
- $A \in R_j$
- $A \in (Z_i\cap R_j)^+_F$, and by lemma 1?: $(Z_i \cap R_j) → A \in F^+$

> [!hint]
> Our goal now is to prove that $A \in G^+$, so we need to have a dependency that determines $A$ inside $G^+$: $X→A \in G^+$.


$(Z_i \cap R_j) → A \in F^+$ belongs to a projection of $F$ on $R_j$, which is the definition of $G$. Because of these things:
- Left side in $R_j$
- Right side in $R_j$
- Dependency is in $F^+$

So we now know that $(Z_i \cap R_j) → A \in G$.
We know that $Z_i \subseteq X^+_G$ from the start and $(Z_i \cap R_j) \subseteq Z_i$, so $(Z_i \cap R_j) \subseteq Z_i \subseteq X^+_G$.

1. $(Z_i \cap R_j) \subseteq X^+_G$
2. $X→(Z_i \cap R_j)\in G^+$ by lemma 1.
3. $X→A\in G^+$ by transitivity.
4. $A \in X^+_G$


#### $Z_f \supseteq X^+_G$

We know that $X=Z_0\subseteq Z_f$, we obtain that 

### WIP

---


## Lossless join

### Definition

For a given solution scheme R and a decomposition.
$S$ has a lossless join if $r=m_S(r)$, where $m_S(r)=\pi_{R_0}(r)\Join \cdots\Join\pi_{R_k}(r)$.


### Theorem

The following statements hold.
1. $r \subseteq m_S(r)$
2. $\pi_{R_i}(m_S(r))=\pi_{R_i}(r)$
3. $m_S(m_S(R))=m_S(r)$

> [!hint]
> 1. The tuples in the reconstructed schema are contained or equal to the ones in the original.
> 2. 


### Proof

We have that:
$$\large t \in \underbracket{\{t[R_1]\} \Join \cdots \Join \{t[R_k]\}}_{\Join\text{ of projections of tuple t}} \subseteq \underbracket{\pi_{R_1}(r) \Join \cdots \Join \pi_{R_k}(r)}_{\Join\text{ of projections of the entire relation}}=m_S(r)$$
> [!hint]
> We are saying that if we decompose a single tuple and we join it back, this tuple is for sure contained in the reconstructed $r$ also.
> 
> This is a way of ensuring that additional tuples don't get generated.


$$\large\pi_{R_i}(m_S(r))=\pi_{R_i}(r)$$

> [!hint]
> This is saying that a projection $R_i$ over $r$ should be equal to the projection $R_i$ over $m_S(r)$.


$$\large m_S(m_S(r))=m_S(r)$$

> [!hint]
> If you project and re-join twice, the thing should stay the same.
