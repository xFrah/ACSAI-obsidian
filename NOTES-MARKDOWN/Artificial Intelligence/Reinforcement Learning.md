## Passive Reinforcement Learning

### Model-based

In model-based learning, the agent first learns the model of the environment (the [MDP](Markov%20Decision%20Processes.md)) from the experiences. 
We have to learn the transition probabilities and reward functions by ourselves.

So we learn an empirical MDP model:
- **Discover probabilities**: Each time we do an action, we count the outcome in the probability distribution $P(s'|s, a)$.
	
> [!hint]
> $P(s'|s, a)$ = (probability of $s'$ given state $s$ and action $a$)
	
- **Discover rewards** for each transaction.


### Model-free

In model-free learning, the agent directly learns the value function (V) or the action-value function (Q) from the experiences, without explicitly learning the transition probabilities and reward functions.

---

> [!attention]
> We will mainly discuss about model-free learning from now on

---
## Direct / Monte-Carlo evaluation

Act according to the policy, then after visiting a state, begin to write down the sum of discounted rewards from that state onwards.

We do this several times for each state and we call them samples, then we average the samples.

> [!example]
> We want the value of state $s$. Let's start from this:
> 
> $$\large V(s) = R(s)$$
> 
> We then transition from $s$ to $s'$, so we write the discounted reward in the formula.
> $$\large V(s) = R(s) + \gamma R(s')$$
> 
> Then as we go from $s'$ to $s''$, so we add it to the formula for $s$.
> $$\large V(s) = R(s) + \gamma R(s') + \gamma^2 R(s'')$$
> 
> > [!hint]
> > Obviously at this point:
> > $$\large V(s') = R(s') + \gamma R(s'')$$
> > and:
> > $$\large V(s'') = R(s'')$$
> 

