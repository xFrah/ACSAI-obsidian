A Markov Decision Process is a setting in which **the next state is not certain**, actions have probabilities of bringing different next states.
For this reason, the solution to an MDP is **not a sequence of actions**, because you cannot predict the next states, but a **policy that will be used at each step** of the process.

Remember, here the goal is to learn a policy, not decide the move at each step.
The action to take is already decided by the policy at runtime, but the policy must be learned beforehand, somehow.

## Definitions

> [!hint] Definition of **Policy**
> A policy is a map of states to actions

> [!hint] Definition of **Reward**
> Immediate feedback received after a state transition due to an action.
> For example the finish states or the death states:
> 

> [!hint] Definition of **Utility**
> The utility is a sum of (discounted) rewards.
> 
> > [!example]
> > For example, the utility of taking a path towards a pit of lava is negative, but the immediate reward of stepping towards it might not be.
> 

## Discounts

An action has a utility based on the future states to which the action leads.
The discount factor is how much the rewards are considered at each step away from the current state.

> [!hint]
> Different discount factors bring different optimal policies. A policy is optimal in relation to its discount factor.

## Value of a state

The value of a state is the expected utility of the state considering that we always take the optimal action.

![](../z_images/Pasted%20image%2020240603170908.png)

> [!hint]
> Here the rewards could be like this:
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

### WIP