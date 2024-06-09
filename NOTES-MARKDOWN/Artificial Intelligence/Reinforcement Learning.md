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

In model-free learning, the agent directly learns the value function (V) or the action-value function (Q) from the experiences, without learning the transition probabilities and reward functions.

---

> [!attention]
> We will mainly discuss about model-free learning from now on.
> The question will be... **how do we find $V(s)$** without probabilities or rewards?

---
## Direct / Monte-Carlo evaluation

Act according to the policy, then after visiting a state, begin to write down the sum of discounted rewards from that state onwards.

We do this several times for each state (in different **episodes**) and we call them samples, then we average the samples.

1. We start from the fixed policy. [Start of episode]
2. We take the action decided by the policy.
3. We keep **different computations of $V(s)$ for each state**, and at each transition we **append the discounted rewards** to the computations of the previous states.
4. We keep going and do the same until S is terminal. [End of episode]
5. **Update the value function altogether**.
6. Do another episode.

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

## Temporal difference

Same as direct evaluation, the only difference is that we update the $V$ function right when we visit the states, not at the end altogether.

1. We start from the fixed policy. [Start of episode]
2. We take the action decided by the policy.
3. We update the value for that state by weighing the previous value and the new sample:

$$\large V(s) \leftarrow (1-\alpha) \underbracket{V(s)}_{\text{prev value}} + \alpha [\underbracket{R(s) + \gamma V(s')}_{\text{new sample}}]$$
4. We go onto the next state and do the same until S is terminal. [End of episode]
5. Restart from starting state and do episodes until you are satisfied I guess?

> [!important]
> Temporal difference is just a model-free way to do policy evaluation, it doesn't compute or improve the policy.

> [!note] Advantages
> It should converge faster than Direct Evaluation because we don't wait an entire episode to update the value function, so our update can use more recent data.


## Q-Value iteration



