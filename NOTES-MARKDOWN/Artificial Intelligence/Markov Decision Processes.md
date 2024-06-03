A Markov Decision Process is a setting in which **the next state is not certain**, actions have probabilities of bringing different next states.
For this reason, the solution to an MDP is **not a sequence of actions**, because you cannot predict the next states, but a **policy that will be used at each step** of the process.

Remember, here the goal is to learn a policy, not decide the move at each step.
The action to take is already decided by the policy at runtime, but the policy must be learned somehow.

## Rewards

Some states have a reward. For example the finish states or the death states.

![](../z_images/Pasted%20image%2020240603165235.png)

## Utility

The utility a sum of (discounted) rewards.

> [!example]
> For example, the utility of taking a path towards a pit of lava is negative, but the immediate reward of stepping towards it might not be.

## Discounts

An action has a utility based on the future states to which the action leads.
The discount factor is how much the rewards are considered at each step away from the current state.

> [!hint]
> Different discount factors bring different optimal policies. A policy is optimal in relation to its discount factor.


## Value of a state

The value of a state is the expected utility of the state considering that we always take the optimal action.
The policy is made to **maximize the expected utility of the whole system**.

![](../z_images/Pasted%20image%2020240603170908.png)