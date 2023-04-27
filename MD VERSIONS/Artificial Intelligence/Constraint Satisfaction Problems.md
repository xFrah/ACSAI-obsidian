CSP search algorithms aim to take advantage of the structure of states(and not [heuristics](Heuristics.md)) to enable the solution of complex problems.

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

```ad-note
Of course, we are using abbreviations here, for example $SA\neq WA$ stands for $\large \langle \, (SA,\;WA),\; SA \neq WA \, \rangle$.
```

---

## And then what?

Basically we can proceed with the assignments.
Whenever we find that a partial assignment has violated a constraint, we immediately discard further processing on it.

We do this until we find a solution.

---

### [Actual code](https://github.com/xFrah/CSP-UNI) of Map Coloring algorithm:

```python
constraints = {
    "WA": ["NT", "SA"],
    "NT": ["WA", "SA", "Q"],
    "SA": ["WA", "NT", "Q", "NSW", "V"],
    "Q": ["NT", "SA", "NSW"],
    "NSW": ["Q", "SA", "V"],
    "V": ["SA", "NSW", "T"],
    "T": ["V"],
}

region_colors = {r: get_random_color() for r in list(constraints.keys())}
domains = {region: set(colors.values()) for region in region_colors}
traversed = set()


def constraint_propagation(region, region_colors, constraints, domains, traversed):

    print(f"Traversing {region} with domain {domains[region]}")
    traversed.add(region)

    # choose a random color from the domain
    color = get_color_from_domain(region, domains)
    region_colors[region] = color
    print(f"[{region}] Set {region} to {color}")


    # remove the color from the domain of the neighbors
    for constraint in constraints[region]:
        if color in domains[constraint]:
            domains[constraint].remove(color)
        print(f"[{region}] Removed {color} from {constraint}")

  
    # choose new neighbor to traverse
    for constraint in constraints[region]:
        if constraint not in traversed:
            constraint_propagation(constraint, region_colors, constraints, domains, traversed)



constraint_propagation("WA", region_colors, constraints, domains, traversed)
```

Example output:

```
Traversing WA with domain {(0, 255, 0), (255, 0, 0), (0, 0, 255)}
[WA] Set WA to red
[WA] Removed red from NT
[WA] Removed red from SA

Traversing NT with domain {(0, 255, 0), (255, 0, 0)}
[NT] Set NT to blue
[NT] Removed blue from WA
[NT] Removed blue from SA
[NT] Removed blue from Q

Traversing SA with domain {(0, 255, 0)}
[SA] Set SA to green
[SA] Removed green from WA
[SA] Removed green from NT
[SA] Removed green from Q
[SA] Removed green from NSW
[SA] Removed green from V

Traversing Q with domain {(0, 0, 255)}
[Q] Set Q to red
[Q] Removed red from NT
[Q] Removed red from SA
[Q] Removed red from NSW

Traversing NSW with domain {(255, 0, 0)}
[NSW] Set NSW to blue
[NSW] Removed blue from Q
[NSW] Removed blue from SA
[NSW] Removed blue from V

Traversing V with domain {(0, 0, 255)}
[V] Set V to red
[V] Removed red from SA
[V] Removed red from NSW
[V] Removed red from T

Traversing T with domain {(0, 255, 0), (255, 0, 0)}
[T] Set T to blue
[T] Removed blue from V

Constraint satisfied: WA, NT = red, blue
Constraint satisfied: WA, SA = red, green
Constraint satisfied: NT, WA = blue, red
Constraint satisfied: NT, SA = blue, green
Constraint satisfied: NT, Q = blue, red
Constraint satisfied: SA, WA = green, red
Constraint satisfied: SA, NT = green, blue
Constraint satisfied: SA, Q = green, red
Constraint satisfied: SA, NSW = green, blue
Constraint satisfied: SA, V = green, red
Constraint satisfied: Q, NT = red, blue
Constraint satisfied: Q, SA = red, green
Constraint satisfied: Q, NSW = red, blue
Constraint satisfied: NSW, Q = blue, red
Constraint satisfied: NSW, SA = blue, green
Constraint satisfied: NSW, V = blue, red
Constraint satisfied: V, SA = red, green
Constraint satisfied: V, NSW = red, blue
Constraint satisfied: V, T = red, blue 
Constraint satisfied: T, V = blue, red 
All constraints satisfied
```