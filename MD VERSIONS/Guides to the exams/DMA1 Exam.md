## Exercise 1

![](../z_images/Pasted%20image%2020230824105209.png)

In order to solve this, we need to know how the operators used to make queries:
- Selection($\large\sigma$): Takes a subset of tuples.
- Projection($\large\pi$): Takes a subset of columns.
- Join($\Join$): There are apparently two kinds:
	- Natural: We join on attributes with the same name (we don't use this).
	- Theta: We choose the fields to use for the join (even if they have the same name)
- Cartesian product(X): We join the two tables and we end up with every tuple combined with every other tuple. 
- Rename($\large p$): Renames attributes, can be useful for joins.

> [!note]
> The grade of a relation is the number of columns.


Prof's solution:
1) We get the code of the Project supercar by selecting code=Supercar, we name the table as supercar_code.
2) We want to find the employees that have that particular supercar project code, so we join participation and supercar_code.
3) We are left with the codes of the employees that are involved in the supercar project, now we just join employee with the new table.
4) But we actually want only the employees that have an head of division with function=Development 


> [!hint] Takeaways
> - We can use the join to filter.
> - After we create new tables with the join we can name them
> - We can subtract tables.
> - In order to get the maximum or minimum of a table, we can do the cartesian product of the table with itself, and then select with a comparative condition and eliminate all the tuples that don't satisfy it.

---

## Exercise 2a

![](../z_images/Pasted%20image%2020230828135216.png)

> [!note] Checking for equivalence
> Two sets of functional dependencies $F$ and $G$ are equivalent if
> 
> $$\large F^+ = G^+$$
> 
> Obviously, $F$ and $G$ are not the same, but the two supersets of all axiom-derivable dependencies must be.
> 
> So how do we check if the two closures are equivalent?
> 
> $$\large F^+\subseteq G^+\quad\text{and}\quad F^+\supseteq G^+$$

> [!note] How to make this shit faster
> Obviously computing this would take too much time so we use this lemma:
> 
> $$\large \text{If} \quad F \subseteq G^+ \quad \text{then}\quad F^+ \subseteq G^+$$
> 
> This is because if $G^+$ contains F, then axioms can be used to obtain all of $F^+$.

In order to determine whether a decomposition with dependencies $G$ preserves F, we need to check if $F \subseteq G^+$.

For every dependency we must know if the right side of the dependencies are contained within $X^+_G$.

These are the steps to compute $X^+_G$:
1) For each table in the decomposition, we start with two sets:
	- $Z$: contains the attributes functionally determined by $X$ in the decomposition.
	- $S$: to be used in a loop, progressively collects the attributes that are determined by $Z$ in each sub-schema.
2) We use the following formula in a loop(i++) to collect the determined attributes from each sub-schema:

$$\large S \;\text{+=} \;\underbracket{\underbracket{(\underbracket{Z\;\cap R_i}_{\text{Part of X also in R}_i})^+_F}_{\text{Attributes determined}}\;\cap R_i}_{\text{Determined attributes that are also in R}_i}$$

3) We add $S$ to $Z$.
4) Repeat step 2 and 3.


> [!example]
> 
$R=ABCDE$, 
$F=\{AC🡪E, AE🡪CD, CE🡪B\}$
$ρ=\{ABCE, CD\}$ (decomposition)
> 
> We want to verify that $AC🡪E$ is satisfied.
> 
> $Z = AC$
> 
> $$\large S \;\text{+=}\; (AC \cap ABCE)^+_F\cap ABCE, \quad S \;\text{+=}\; (AC \cap CD)^+_F\cap CD$$
> $$\large S \;\text{+=}\; (AC)^+_F\cap ABCE, \quad S \;\text{+=}\; (C)^+_F\cap CD$$
> $$\large S \;\text{+=}\; ACE\cap ABCE, \quad S \;\text{+=}\; \emptyset\cap CD$$
> $$\large S \;\text{+=}\; ACE, \quad S \;\text{+=}\; \emptyset$$
> 
> $Z = ACE$
> 
> We stop the loop here, since $E$ is inside $Z$.
> 
> If this wasn't the case, we would have needed to do another iteration of the loop.
> 

---
## Exercise 2b

![](../z_images/Pasted%20image%2020230828135232.png)

> [!note] What is a Lossless Join?
> We have a lossless join when upon applying natural join to a decomposition of $R$, we get exactly $R$.

Steps for checking whether a join is lossless or not:
1) We construct a table where the rows represent the sub-schemas, and the columns represent the individual attributes of $R$. In each cell, we put $a_{j}$ if the attribute is contained in the subschema, we put $b_{ij}$ otherwise ($i$=row, $j$=column).

2) ![](../z_images/Pasted%20image%2020230828172634.png)

3) You loop until no more changes can be made or if one row is full of $a$'s. If we have a row full of $a$'s the join is lossless, otherwise it is lossy.

> [!example]
$R = (A, B, C, D, E)$
$F = \{ C → D, AB → E, D → B \}$
Say whether decomposition
$ρ = \{ AC, ADE, CDE ,AD ,B \}$
has a lossless join.
> ![](../z_images/Pasted%20image%2020230828171546.png)
> 
> We examine the dependency $C → D$, and we can see that $C$ has 2 rows($a$'s) in its columns, so we need to make the elements in the columns of $Y$ equal in correspondence of those $a$'s.
> 
> ![](../z_images/Pasted%20image%2020230829155354.png)
> 
> We examine the dependency $AB → E$, there are no rows in which $A$ and $B$ are equal, so we have no way of verifying the dependency right now(already verified).
> 
> We examine the dependency $D → B$, we can see that $D$ has 3 equal rows, so we make the rows of $B$ equal.
> 
> ![](../z_images/Pasted%20image%2020230829160914.png)
> 
> We have completed the first loop and we don't have a row full of $a$'s, but changes can still be made, so we keep going.
> 
> We examine the dependency $C → D$, which is already satisfied.
> 
> ![](../z_images/Pasted%20image%2020230829161305.png)
> 
> We examine the dependency $AB → E$, and we can make some changes:
> 
> ![](../z_images/Pasted%20image%2020230829161435.png)
> 
> We examine the dependency $D → B$, which is already satisfied.
> 
> We keep the loop going.
> 
> ![](../z_images/Pasted%20image%2020230829161839.png)
> 
> No more changes can be made at all.
> Since we don't have a row full of $a$'s, our join is lossy.

---

## Exercise 2c

![](../z_images/Pasted%20image%2020230829163426.png)

> [!note] Definition of Key
> A subset $K$ of a relation is a key if:
> - $K → R \in F^+$: $K$ determines all other attributes.
> - There are no subsets $K'$ such that $K → R \in F^+$: There are no subsets of $K$ that determines all other attributes.

