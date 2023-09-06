## Section 1

![](../z_images/Pasted%20image%2020230707152459.png)

> [!info] Required notions
> - [Heuristics](../Artificial%20Intelligence/Heuristics.md)
> - [A*](../Artificial%20Intelligence/A-star.md)
> - [Breadth First Search](../Artificial%20Intelligence/BFS.md) 
> - [Depth First Search](../Artificial%20Intelligence/DFS.md)(possibly)
> - [Best First Search](../Artificial%20Intelligence/Best-first%20search.md)(possibly) 


![](../z_images/Pasted%20image%2020230707152607.png)


### Draw the state space as a [graph](../Artificial%20Intelligence/Graph.md)

Here we just need to basically draw an automaton with edges that have a cost.
The cost will be the [heuristic](../Artificial%20Intelligence/Heuristics.md) $h(n)$ which is just the shortest number of blocks that can be traveled to reach the exit.

![](../z_images/Pasted%20image%2020230707154807.png)

Here, in addition to the cost, the prof has included the direction that the edge takes us to.

---


![](../z_images/Pasted%20image%2020230708172755.png)


### Run [A*](../Artificial%20Intelligence/A-star.md)

We just add to the "reached" set the node in the "frontier" that has the lowest cost.

![](../z_images/Pasted%20image%2020230707184827.png)

In the squares above:
- Top-left: state
- Top-right: actual cost to reach
- Bottom-left: step at which they are added to "frontier"
- Bottom-right: step in which they are added to "reached"


![](../z_images/Pasted%20image%2020230707184842.png)

---


![](../z_images/Pasted%20image%2020230708172845.png)


### Can BFS constitute an admissible heuristic

A heuristic function is said to be **admissible** if it never overestimates the cost of reaching the goal. Also it must have a value for every input.

#### WIP

---


## Section 2



---


## Section 3

> [!note] Required Notions
> - Propositional Logic
> - [Satisfiability](../Artificial%20Intelligence/Propositional%20Satisfiability.md) of a Compound Proposition
> - [Contrapositive](../Artificial%20Intelligence/Logical%20Equivalence.md) of a proposition
> - Forward Chaining
> - [Entailment](../Artificial%20Intelligence/Propositional%20Satisfiability.md) of propositions
> - Tableau Resolution Deductive System
> - DPLL


![](../z_images/Pasted%20image%2020230708173131.png)

