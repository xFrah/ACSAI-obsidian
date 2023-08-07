---
alias: Bellman Equation, Bellman's Equation, Bellman's Equations
---
First a few definitions:

> [!quote] State concept
> A numeric representation of what the [agent](../Artificial%20Intelligence/Agent.md) is observing at a particular point in time in the [environment](../Artificial%20Intelligence/Environment.md).

> [!quote] Action concept
> The input the agent provides to the environment, computed by applying a policy to the current state.

> [!quote] Policy concept
> Either a table that contains the actions for every state, or a neural network that can estimate such actions based on input states.

> [!quote] Reward concept
> A feedback from the environment reflecting how well the agent is performing the goals of the game.


## What is the Bellman Equation for?

Given the current state, and assuming that I play perfectly in all future steps, what is the long-term reward?

It assigns a value to a state.

$$\large V(s) = \text{max}_a(R(s, a)+\gamma V(s'))$$

> [!hint]
> - $\text{max}_a$: selects the action that maximizes $V$.
> - $R(s, a)$: reward of action $a$ in current state $s$.
> - $\gamma$: discount factor, it diminishes our reward over time.

> [!example]
>![](../z_images/Pasted%20image%2020230807152401.png)

> [!danger]
> This process/formula assumes that at each step we take the perfect action.

---

## Stochastic Environment

We use the [Markov Decision Process](Markov%20Decision%20Process.md) to account for uncertainty and randomness.

$$\large V(s) = \text{max}_a \left(R(s, a) + \gamma \sum_{s'}P(s, a, s')V(s')\right)$$

> [!hint]
> We are not sure what the next state will be, so we basically compute the Expectation of its value $V$(by iterating through all possible next states).
> 
> The result will be the expected value of the next state.

> [!example]
> ![](../z_images/Pasted%20image%2020230807155135.png)
