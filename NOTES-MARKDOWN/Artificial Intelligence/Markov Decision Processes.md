---
aliases:
  - MDP
---

A Markov Decision Process is a setting in which **the next state is not certain**, actions have probabilities of bringing different next states.

For this reason, the solution to an MDP is **not a sequence of actions**, because you cannot predict the next states, but a **policy that will be used at each step** of the process.

Remember, here the goal is to learn a policy, not decide the move at each step.
The action to take is already decided by the policy at runtime, but the **policy must be learned beforehand**, somehow.

## Definitions

> [!hint] Definition of **Policy**
> A policy is a map of states to actions.

> [!hint] Definition of **Reward**
> Immediate feedback received after a state transition due to an action.

> [!hint] Definition of **Utility**
> The utility is a sum of (discounted) rewards.
> 
> > [!example]
> > For example, the utility of taking a path towards a pit of lava is negative, but the immediate reward of stepping towards it might not be.
> 

## Discounts

An action has a utility based on the future states to which the action leads.
The discount factor is how much the rewards are considered at each step away from the current state.
This basically decides the **importance of future rewards**.

> [!hint]
> Different discount factors bring different optimal policies. A policy is optimal in relation to its discount factor.

## Value of a state

The value of a state is the expected utility of the state considering that we always take the optimal action.

![](../z_images/Pasted%20image%2020240603170908.png)

> [!hint]
> Utility != Rewards.
> Here the rewards look like this:
> ![](../z_images/Pasted%20image%2020240603165235.png)


## Q-Values

Q-Values represent the expected utility of a state if we take a **specific action and act optimally** from that point onwards. Values of a state are computed through an **[argmax](../Machine%20Learning/Multi-Class%20Classification.md) of the q-values** of the state.

Here we can see values on the left and q-values on the right.

![](../z_images/Pasted%20image%2020240604095123.png)


## Bellman Equations

![](../z_images/Pasted%20image%2020240604104238.png)

Hopefully going through the Bellman equations will bring a better understanding.
As we already know, the value of a state is given by its highest q-value, so it's optimal action.

$$\large V^*(s)=\max_{a \in A}Q^*(s, a)$$

But how do we know the q-value of that action?

$$\large Q^*(s, a)=R(s)+\gamma \max_{a \in A} \sum_{s'}{P(s'|s, a)V^*(s')}$$
The second part of the equation basically means:
- We iterate through the actions
- For each action, compute the average value ([expected value](../Statistics/Expected%20value.md)) of its possible next states, because the **next state is uncertain**.
- Take the action with the highest expected value.
- That will be the q-value of that action, * the discount, + the current reward.

> [!hint] How is this different from [[Adversarial Search#Expectimax Search|expectimax]]?
> The score of an expectimax node is the average score of its children. Each children has a probability of happening, so this score will be the expected value of the scores of the children.
> 
> Basically there is no difference, here the scores of the children are the $V^*$ values of the next states, and we take the expectimax node (action) with the highest average $V^*$.


Obviously, in order to do this we need the $V^*$ of every state.

## Value iteration

We keep a vector $V$ which contains all the values of all the states.
We update vector $V$ with the bellman update equation, using values from the previous iteration:

$$\large V_{i + 1}\leftarrow R(s)+\gamma \max_{a \in A} \sum_{s'}{P(s'|s, a)V_i(s')}$$

> [!hint] Hints
> - The first iteration of vector $V$ is called $V_0$, the second $V_1$ and so on...
> - In iteration $i$ of the algorithm, we use the values of $V_i$ to fill the values in $V_{i+1}$.
> - So basically the notation $V_i$ and $V_{i+1}$ indicate the whole vectors, not just single cells/states.


The result is that information propagates outwards from terminal states.

> [!example]
> $\gamma = 0.9$
> $\text{noise} = 0.2$ (probability of going to the wrong state)
> ![](../z_images/Pasted%20image%2020240604152401.png)
> 
> Here the only cell that can actually update is the cell at the left of the positive finish state, since every other cell has neighbors with value 0 or -1 ($\max(0, -1) = 0$).
> 
> That cell has 3 possible actions:
> - Going left
> - Going right (**we already know that it's the best action because we're human**)
> - Going down
>   
> > [!hint]
> According to the bellman equation, we should iterate through the actions, and find the action that gives the highest average value (between the possible states that it can lead to).
> > 
> > But here (as humans) we already know that the best action is going to the right, so we skip the $\max$ step and **we just compute the expected value of the best action**.
> 
> We compute the **expected value of "going right"**:
> 
> $$\large \gamma \sum_{s'}{P(s'|s, a)V_i(s')} = 0.9 \cdot \underbracket{[\underbracket{0.8 \cdot 1}_{\text{correct state}} + 0.2 \cdot 0 + 0.2 \cdot 0]}_{\text{expected value}} = 0.72$$
> 
> > [!hint]
> > Remember that **this formula accounts for the possibility of transaction randomness**.
> > In this case we have a 0.2 chance of going to the wrong state, and we take that into account in our expected value computation.
> 
> ![](../z_images/Pasted%20image%2020240604160207.png)
> 
> > [!hint]
> > The cell from before has a new value because the adjacent cells don't have 0 value anymore, so they add to the expected value due to the 0.2 possibility of going there.


---

 > [!note] Sources
>https://www.youtube.com/watch?v=l87rgLg90HI
>https://www.cs.cmu.edu/~./15281-f19/lectures/15281_Fa19_Lecture_15_MDPs_II_inked.pdf
>Indro's slides.
