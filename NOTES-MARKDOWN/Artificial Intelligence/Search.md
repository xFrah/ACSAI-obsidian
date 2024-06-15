> [!hint] Introduction
> 
> ## Search problem definition
> 
> We have a **State Space**(set) which contains all the possible states of the environment.
> 
> ![](../z_images/Pasted%20image%2020240510115334.png)
> 
> 
> We have a **Successor function** that maps actions to their cost.
> 
> ![](../z_images/Pasted%20image%2020240510115449.png)
> 
> We also have a **Start state** and a **Goal state**.
> 
> 
> ## State Space Graph
> 
> A mathematical representation of a search problem.
> 
> In this graph:
> - **Nodes** == world states
> - **Edges** == successors
> - Each state is unique
> - The goal is a set of goal nodes
> - Sometimes edges are one-way
> 
> ![](../z_images/Pasted%20image%2020240510115920.png)
> 
> 
> ## Tree search
> 
> - **Root** node == start state
> - **Children** nodes == successors
> - **Nodes** == plans(set of actions)
> 
> For tree search problems we have:
> - A **frontier**: which is the set of nodes that we can potentially expand to.
> - A **strategy**, which is the rule that makes us choose which nodes to expand from the frontier.
> - The **goal state**.
> 
> > [!example] Pseudo-Algorithm
> > ![](../z_images/Pasted%20image%2020240510125930.png)
> > ![](../z_images/Pasted%20image%2020240510130030.png)
> 
> 
> ### Performance of search
> 
> The algorithm is ... if ...:
> - **Complete**: if it is guaranteed to find a solution.
> - **Optimal**: if it is guaranteed to find the least cost path.
> 
> Then we also have:
> - **Time complexity**: is the amount of nodes that we need to traverse.
> - **Space complexity**: is the amount of nodes that we need to keep in memory.
> 
> ### Time/Space Complexity variables
> 
> In order to continue, we need to define some variables:
> - **b**: maximum branching factor of search tree.
> - **d**: depth of the shallowest goal node.
> - **m**: maximum length of any path in the state space


---

## Breadth-first Search

The strategy for this tree search is: **Always expand shallowest node**.

![](../z_images/Pasted%20image%2020240510130254.png)

> [!note] Performance [Exponential in Space and Time]
> - Is it **complete**? Yes, we are guaranteed to find a solution if **b** is finite.
> - **Time complexity**: $1+b+b^2+b^3 + ... + b^d = O(b^d) = O(\text{max branches}^\text{max depth})$
> - **Space complexity**: $O(b^d)$, it keeps every node in memory.
> - Is it **Optimal**? Yes, but only if cost = 1 for each step.


## Depth-first Search

The strategy for this tree search is: **Always expand deepest node**.

![](../z_images/Pasted%20image%2020240510131720.png)

> [!note] Performance [Terrible time but Good space]
> - Is it **complete**? No, it fails in infinite depth or looped spaces.
> - **Time complexity**: $O(b^m)= O(\text{max branches}^{\text{max path length}})$
> - **Space complexity:** $O(bm)$, linear space.
> - Is it **optimal**? No lol. We could find sub-optimal before finding optimal.


## Iterative deepening?

![](../z_images/Pasted%20image%2020240510132414.png)

![](../z_images/Pasted%20image%2020240510132424.png)

---

> [!warning]
> From this point on, nodes can have different costs.

## Uniform Cost Search

The strategy for this tree search is: **Always expand to the cheapest node**.

> [!hint]
> We basically order the frontier by the path cost function for each node. Then we expand on the first one.

![](../z_images/Pasted%20image%2020240510132909.png)


## Greedy

Expand node closest to goal according to a heuristic function.

## [A*](A-star.md)

Expand node that has lower cost according to this cost function

$$\large\text{cost}(n) = \text{real cost from start to n} + \text{estimated cost from n to goal}$$

![](../z_images/Pasted%20image%2020240602100039.png)
