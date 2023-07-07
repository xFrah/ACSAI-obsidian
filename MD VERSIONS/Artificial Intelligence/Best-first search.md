---
alias: Best first search
---

We have 2 data structures:
- Explored: set of already examined nodes
- Frontier: set of nodes that have an edge on the explored set

Basically at every step of the algorithm we must choose a node from the frontier and traverse it, adding it to the explored set.

This node is chosen by getting the one with the minimum value of a function f(n).


```ad-note
title: Greedy best-first search
This algorithm is said to be "informed" when $\large f$ is an [[Heuristics|heuristic]] function.

So at every step we expand on the node that appears closer to the destination.
```

