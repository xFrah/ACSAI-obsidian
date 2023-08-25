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

## Exercise 2

![](../z_images/Pasted%20image%2020230825180314.png)

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

$R=ABCDE$, 
$F=\{AC🡪E, AE🡪CD, CE🡪B, DC🡪EB\}$
$ρ=\{ABCE, CD\}$ (decomposition)


We just need to check that the left and right parts of all dependencies are together the tables.
