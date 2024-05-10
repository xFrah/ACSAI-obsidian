> [!note]
> We can consider **searching as an agent-based task**, for which the agent finds a sequence of actions which transform the environment into the goal state.

## Open loop search

While the agent executes the solution, it **ignores the perception** stage.
This is possible if the environment is:
- **Deterministic**
- **Fully observable**
- **Known to the agent**

> [!example]
> This is not possible with chess, because the other player can change the environment, so we must perceive it again.


## Search problem definition

We have a **State Space**(set) which contains all the possible states of the environment.

![](../z_images/Pasted%20image%2020240510115334.png)


We have a **Successor function** that maps actions to their cost.

![](../z_images/Pasted%20image%2020240510115449.png)

We also have a **Start state** and a **Goal state**.


## State Space Graph

A mathematical representation of a search problem.

In this graph:
- **Nodes** == world states
- **Edges** == successors
- Each state is unique
- The goal is a set of goal nodes
- Sometimes edges are one-way

![](../z_images/Pasted%20image%2020240510115920.png)

