### Reduction from 3-CNF-SAT (30 e lode)

The idea is that we have some way to represent this formula as a graph.
We represent each variable as a double way linked chain on k nodes (k = number of clauses).

We interconnect each edge of the row with another external vertex (above and below each row).
The extremes of the row are only there to make the graph...

There are 2 nodes that speak about the presence of a variable in a clause, then a separator, then again 2 nodes, then separator, and so on.

SEPARATOR | NODE IN A CLAUSE | SEPARATOR | NODE IN A CLAUSE

Suppose $c_j$ is a clause.
We have an external node $c_j$, and for each pair of nodes (that are not separators), we put edges that go to or from this external node $c_j$. 
- If the variable is not negated inside the clause $c_j$, we go from the left node and we come back from $c_j$ in the right node
- If the variable is negated inside $c_j$, we go from the right node to $c_j$, and we come back to the left node.

> [!hint]
> It's not strictly required to have 3k+3, you can have 2k+2, but then it's more difficult...?


Now we have to prove that once we have a satisfiable assignment for a formula, we should be able to find an hamiltonian path.
Conversely, from an hamiltonian path, we should be able to recover an assignment that is satisfiable for a formula.