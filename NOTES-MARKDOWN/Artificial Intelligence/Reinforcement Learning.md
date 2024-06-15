## Passive Reinforcement Learning

### Model-based

In model-based learning, the agent first learns the model of the environment (the [MDP](Markov%20Decision%20Processes.md)) from the experiences. 
We have to learn the transition probabilities and reward functions by ourselves.

So we learn an empirical MDP model:
	
- **Discover probabilities**: Each time we do an action, we count the outcome in the [probability distribution](../Probability/Probability%20distribution.md) $P(s'|s, a)$.
	
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
#### Direct / Monte-Carlo evaluation

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

#### Temporal difference

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


#### Q-Value iteration

Now that we know how to evaluate the policy in a model-free way, we need to do the action selection part.

It's exactly the same as value iteration, we keep a vector $Q_i$ which stores the q-values for each state and action at each itearation, and we use the q-values in $Q_i$ to compute $Q_{i+1}$.

If this wasn't model free, we'd use the following formula:

$$\large Q_{i+1}(s, a)=R(s)+\gamma \sum_{s'}{P(s'|s, a)\max_{a' \in A}Q_i(s', a')}$$
> [!hint]
> Which means that we are taking the [expected value](../Statistics/Expected%20value.md)(because of randomness in transitions) of the best action.


Since we don't have the probabilities or the rewards, we need to take samples.

$$\large Q_{i+1}(s, a) \leftarrow (1-\alpha)\underbracket{Q_i(a, s)}_{\text{old value}} + \alpha \underbracket{[R(s) + \gamma\max Q_i(s', a')]}_{\text{new sample}}$$

> [!hint]
> The new sample is given by the best q-value from the new state $s'$ + the transition reward.

> [!example]
> ![](../z_images/Pasted%20image%2020240610105931.png)


## Active Reinforcement Learning

We act accordingly to the q-values for gaining experience. (**Exploitation**)

> [!summary] Exploration vs Exploitation
> - **Exploration** means that we choose suboptimal actions to gain samples and improve the policy. 
> - **Exploitation** means that we follow the actions that were found to bring higher rewards.
>   
>  We need a balance between the two, because if the agent explores too much, **learning takes a long time**; if the agent exploits too much, we might get **stuck in a local optima**. 


But in order to exploit the policy, we also need to learn it or improve it.
We do this by exploring more, so that we can find new ways of improving the policy.

### ε-greedy

Every time we take a step, flip a coin, we have $ε$ probability of acting randomly.
We should lower the probability over time.

### Exploration functions

Explore areas that were not explored enough times.

### Approximate q-learning

We don't learn all possible states, but we learn generalized states and use them for new similar solutions.

This is too much for now, I don't care sorry.

## Feature representations

Features are functions that map states to numbers that capture important information of the state.

> [!example]
> ![](../z_images/Pasted%20image%2020240610170931.png)
> 
> - Distance to closest ghost
> - Distance to closest dot
> - Number of ghosts
> - 1 /(dist to dot)2
> - Is Pacman in a tunnel? (0/1)

### Linear Value Functions

We can write the value functions using features of the states.

$$\large V(s) = w_1f_1(s)+w_2f_2(s)+\dots+w_nf_n(s)$$
$$\large Q(s, a) = w_1f_1(s, a)+w_2f_2(s, a)+\dots+w_nf_n(s, a)$$

> [!hint]
> The weights are learned, they serve the purpose of indicating the importance of a certain feature for a certain state.

> [!example]
> The features for the pacman example are:
> - $f_1$: distance to the nearest ghost
> - $f_2$: distance to the nearest dot
> - $f_3$: number of remaining dots
> - $f_4$: inverse square of the distance to the nearest power pellet
> 
> Now we give an example of the weights.
> 
> - $w_1$ = −2 (closer ghosts are more dangerous)
> - $w_2$ = −1 (closer dots are more beneficial)
> - $w_3$ = −0.5 (fewer dots mean progress)
> - $w_4$ = 5 (closer power pellets are very beneficial)
> 
> Imagine pacman is in a state where:
> 
> - $f_1$ = 5 (5 steps to the nearest ghost)
> - $f_2$ = 3 (3 steps to the nearest dot)
> - $f_3$ = 20 (20 dots left)
> - $f_4$ = $\frac{1}{2^2}$=0.25 (2 steps to the nearest power pellet)
> 
> The value for this state is:
> $$\large V(s)=(−2)⋅5+(−1)⋅3+(−0.5)⋅20+5⋅0.25$$
> 
> ### This is from chatgpt, check if it's right.
