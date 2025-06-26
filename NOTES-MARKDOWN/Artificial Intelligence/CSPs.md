---
aliases:
  - Constraint satisfaction problem
  - constraint satisfaction problems
---
CSP [search](Search.md) algorithms aim to take advantage of the structure of states(and not [heuristics](../Artificial%20Intelligence/Heuristics.md)) to enable the solution of complex problems.

We want to eliminate large portions of the search space all at once by identifying which combinations violate the constraints.

---

## States in CSP

In CSP, each state is a set of variables, each of which has a value. A problem is solved when all the variables satisfy the constraints.

---

## CSP problem definition

A constraint satisfaction problem consists of three components:
- $X$ - a set of variables { ${X_1,...,X_n}$ }
- $D$ - a set of domains { ${D_1,...,D_n}$ }, one for each variable.
- $C$ - a set of constraints, which specify allowable combinations of values.


### Domains

A domain $D_i$ consists of a set of allowable values { ${v_1,...,v_k}$ } for variable $X_i$ .

```ad-example
A boolean variable would have domain {$true$, $false$}.
```


###  Constraints

A constraint $C_j$ consists of a pair $(scope, \;rel)$ where:
- $scope$ is a tuple of variables that are used in the constraint.
- $rel$ is a relation that defines what values those variable can take on.

```ad-example
A relation can be either:
- a set of tuples containing the values that satisfy the constraint for each variable.
$$\large \langle \, (X_1,\;X_2),\;\{ (3, \,1),\;(3, \,1),\;(2, \,1) \} \, \rangle$$
- a function that can compute if the variable satisfies the constraint or not.
$$\large \langle \, (X_1,\;X_2),\; X_1 > X_2 \, \rangle$$
```


### Assignments

A CSPs assignment is the process of assigning a value to a variable.

Types if assignments:
- Consistent assignment: the assignment doesn't violate any constraints.
- Complete assignment: every variable is assigned a value
- Partial assignment: leaves some variables unassigned.
- Partial solution: Partial assignment that is consistent.

The solution to a CSP is a complete, consistent assignment.

---

## Map coloring problem

We are given the task of coloring regions on a map of Australia, but in such a way that no two neighboring regions have the same color.

![](../z_images/Pasted%20image%2020230416193009.png)

We start with the set of variables:
$X = \{WA,NT,Q,NSW,V,SA,T\}$

The domain of every variable is:
$D = \{red,green,blue\}$

Now for the constraints, since there are 9 borders, we impose that the bordering sections aren't the same color:
$C = \{SA\neq WA,\; SA \neq NT,\; SA\neq Q,\; SA \neq NSW,\; SA \neq V,\; WA \neq NT,\; NT \neq Q,\; Q \neq NSW,\; NSW \neq V\}$
---

## And then what?

Basically we can proceed with the assignments.
Whenever we find that a partial assignment has violated a constraint, we immediately discard further processing on it.

We do this until we find a solution.

---

## Arc Consistency

Arc Consistency is a pre-processing strategy that prunes possibilities by enforcing constraints before proceeding with the search.

It reduces the domains of variables before the search starts by removing values that cannot be part of any solution.
This helps in pruning the search space, making the subsequent backtracking search more efficient.