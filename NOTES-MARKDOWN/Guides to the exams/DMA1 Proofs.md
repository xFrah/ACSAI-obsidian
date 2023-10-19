> [!cite] Slides
> - [Closure Lemma](https://drive.google.com/file/d/1YYm6b061ucbzg8sBA7bNud2CfCOdhLW8/view) - Slide 8 Page 10
> - [Fa = F+](https://drive.google.com/file/d/1YYm6b061ucbzg8sBA7bNud2CfCOdhLW8/view) - Slide 8 Page 11
> - [Closure of X](https://drive.google.com/file/d/1M1pJCkFKwQRxXft-eQiU5Jm_1gvL5Fpi/view) - Slide 11 Page 8
> - [Closure inclusion Lemma](https://drive.google.com/file/d/1n4PRcCG0abmxvBYpDyc5pMHGZMtALzIM/view) - Slide 13 Page 14


## Closure Lemma

### Lemma

$X→Y$ is in $F^A$ if and only if $Y$ is determined by $X$.

$$\large X→Y \in F^A \quad <=> \quad Y\subseteq X^+$$
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


## $F^A=F^+$

### Proof (By double inclusion)

#### $F^A \subseteq F^+$ (every dependency in $F^A$ is also in $F^+$)

Let $X→Y$ be a **dependency in $F^A$**, we will demonstrate that it's **also in $F^+$**.

##### Base case(n=0):
Since **we used 0 axioms** to get $X→Y$, it must be in $F$ and so in $F^+$.
##### Induction case:
We assume that the dependencies obtained with n applications of the axioms are already in both $F^A$ and $F^+$.

**We apply the axioms another time**(n+1) and prove that the resulting dependency is in $F^+$.


###### - Reflexivity
We are obtaining $X→Y \in F^A$ because $Y$ is part of $X$.

> [!hint]
> We know that the dependencies in $F^+$ need to satisfy every legal instance of $R$, so we demonstrate that $X→Y$ is legal in $R$.


$X→Y$ is legal in $R$ if:

$$\large t_1[x]=t_2[x] →t_1[y]=t_2[y]$$

**In the case of reflexivity**, **this is always true**, because $Y$ is part of $X$.


###### - Augmentation
We obtained $X→Y \in F^A$ through augmentation, which means that we had a dependency $V→W$ in $F^+$ and we augmented it to $VZ→WZ \in F^A$.

> [!hint]
> Remember that $X=VZ$ and $Y=WZ$.


**We assume we have a legal instance of R**, and knowing that $V→W \in F^+$, we prove that $X→Y \in F^+$.

We take as example two tuples with equal $X$ on a legal instance of R:
$$\large t_1[X]=t_2[X]$$

We demonstrate that if $X$ is equal, $Y$($WZ$) will be equal too.

- $\large t_1[V]=t_2[V]$ because of **reflexivity**.
- $\large t_1[W]=t_2[W]$ because **we know $V→W \in F^+$ and $V$ is in $X$**.
- $\large t_1[Y]=t_2[Y]$ because of reflexivity on $Z$ and **the two proofs above**.


###### - Transitivity
We obtained $X→Y \in F^A$ through transitivity, which means that we had $X→Z$ and $Z→Y$ already in $F^+$.

So supposing that we have two tuples with equal $X$, for those tuples the following will hold:
- $\large t_1[Z]=t_2[Z]$ **because of $X→Z \in F^+$**.
- $\large t_1[Y]=t_2[Y]$ **because $Z→Y \in F^+$ and the statement above**. 

#### $F^A \supseteq F^+$ (every dependency in $F^+$ is also in $F^A$)

![](../z_images/Pasted%20image%2020230906161744.png)

We suppose that **there exists a dependency in $F^A$ that is not in $F^+$**.
We use a legal instance of R to show that this brings a **contradiction**.

##### 1) R is legal

In order for $r$ to be illegal, we would need to have a dependency such that:
$$\large V→W \in F\quad \text{and} \quad t_1[V]=t_2[V] => t_2[W] \neq t_2[W]$$
This could happen only if:
- $V$ is a subset of $X^+$ and $W$ has parts in $R-X^+$.

We have a contradiction:
###### 1) Apply LEMMA 1
$$\large \underbracket{V \subseteq X^+}_{\text{premise}} \quad= \quad X → V \in F^A$$
###### 2) Apply Transitivity
$$\large \underbracket{\underbracket{X → V \in F^A}_{\text{Lemma 1}} \quad \text{e} \quad \underbracket{V→W \in F}_{\text{premise}}}_{\text{Transitivity}} \quad=\quad X→W \in F^A$$

###### 3) Apply LEMMA 1 - Contradiction part

$W \subseteq X^+$. 

So in any case we have that when $V$ belongs to $X^+$, $W$ belongs to $X^+$ too. $V→W \in F$ is **always satisfacted**. 
Since we proved it with a general dependency this **R is always legal**.

##### 2) Every dependency in $F^+$ is also in $F^A$

Since R is legal, if we have $X → Y \in F^+$ it means that if two tuples are equal on $X$, they will also be equal on $Y$.

**This means:**
$$\large Y\subseteq X^+ \quad \text{and so} \quad X → Y \in F^A$$

---

## Closure inclusion Lemma

### Lemma

If $F$ is contained in $G^+$, then $F^+$ is also contained in $G^+$.

$$\large \text{If} \quad F \subseteq G^+ \quad \text{then}\quad F^+\subseteq G^+$$
### Proof

> [!warning]
> The premise is that we know that $F\subseteq G^+$ is True.

> [!info] Notation
> Let $F'$ be a set of functional dependencies derived by $F$ through the axioms. We indicate this process of deriving by:
> 
> $$\large F \rightarrow^{A} F'$$
> 

##### Demonstrate that $F^+$ can be derived from $F$
1) **HOLDS:** $F'$ can be derived from $F$ (through axioms) if and only if $F'$ is in $F^+$.

$$\large F \rightarrow^{A} F' \quad \text{iff} \quad F'\subseteq F^+$$

> [!hint]
> If $F'$ was derived from $F$, it must be a subset of $F^+$.


2) **This implies** that $F^+$ can be derived from $F$.

$$\large F \rightarrow^{A} F^+$$

##### The actual proof
3) Now we know that we can get $F^+$ from $F$. If we can get $F$ from $G$, then we know that we can get $F^+$ from $G$.

$$\large F \subseteq G^+ \quad \text{iff} \quad \underbracket{G→^A F→^AF^+}_{G → F^+}$$

> [!hint]
> The premise here is that $F\subseteq G^+$ is True, so $G→^A F→^AF^+$ is also True.


4) $G→^A F→^AF^+$ being true means that we can get $F^+$ from $G$, and so $G^+$ also contains $F^+$.

$$\large F^+ \subseteq G^+$$

---


## Closure of X

### Theorem

The algorithm outputs $X^+_F$.
We use 2 sets in the algorithm:
- $Z$: Attributes **already included** in the result at current iteration.
- $S$: Attributes that **will be added** to the result at the current iteration.

We want to prove that $Z_f = X^+$.
We do so by double inclusion and by induction on the number of iterations.

> [!note]
> A single step is done as follows:
> $$\large S = A | Y→V ∈ F, A∈V ∧ Y⊆Z$$
> 
> Which basically means that we add to S **every attribute of V** if **V depends on attributes that are in Z**.
> 
> For each:
> $$\large \underbracket{A}_{\text{For each attribute of the dependency}} | \underbracket{Y→V ∈ F}_{\text{For each dependency in F}}$$
> 
> Condition: 
> $$\large \underbracket{A∈V}_{\text{attribute is in V}} \quad \underbracket{∧}_{\text{and}} \quad \underbracket{Y⊆Z}_{\text{left side is part of Z}}$$


### Proof

#### $Z_f \subseteq X^+$

##### Base case($i=0$):
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


###### 1) Transitivity:
We know $Y$ is contained in $Z$ and $Z$ is contained in $X^+$:
$$\large Y \subseteq \underbracket{Z_i \subseteq X^+}_{\text{induction}} \quad = \quad Y \subseteq X^+$$
###### 2) Lemma 1
$$\large Y \subseteq X^+ \quad = \quad X→Y \in F^A$$

###### 3) Transitivity
$$\large X→Y \in F^A\quad \text{and} \quad \underbracket{Y→V \in F}_{\text{original dependency}}\quad = \quad X→V \in F^A$$
###### 4) Lemma 1
$$\large X→V \in F^A \quad = \quad V\subseteq X^+$$

###### 5) A is in $X^+$
$$\large A \in V \subseteq X^+$$

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
