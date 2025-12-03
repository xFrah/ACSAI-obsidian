### Reduction from SAT to CLIQUE

We can show that 3-CNF-SAT reduces to clique ($\text{3-CNF-SAT} \leq_P \text{CLIQUE}$).

(G, k) with k as the number of clauses in my formulas.
We need to find formulas that are satisfiable if and only if bla bla bla


For every clause and for every literal of a clause, i add some nodes.

Imagine we have a graph, and for each clause we have a triplet of nodes (literals), basically one vertex for every literal.
I will put an edge between every pair of literals that are from different clauses, but are not complements of each other.

This formula is satisfiable if and only if we have a clique of size 3 in this graph.

Assume that the formula is satisfiable. Since it is in CNF, every clause has at least one literal that is 1. 
For every clause, we choose one literal that is 1. This corresponds to a set of vertices in my graph with exactly size k. Then we claim that these k nodes are all pairwise connected.

Basically this construction makes it so that if the formula is satisfiable, then we have a clique of size k.

#### from clique to sat

Suppose that the graph has a clique of size k.