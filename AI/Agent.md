1. The agent is a software that <span style="background:rgba(183, 152, 255, 0.3)">acts</span> upon actuation.
2. The actions of the agent have an effect on the [environment](Environment.md).
3. The <span style="background:rgba(183, 152, 255, 0.3)">agent perceives the environment</span> through sensors.

An agent could be viewed as a function that takes the perceived universe P and the universe of actions A.
With function agent, P partially determines A.
Partially because the agent can potentially ignore part of P.
P should be a sequence of perceptions. We map it to one action at a time.
TODO: Rewrite with formula.

## Good behavior

- Consequentialism: Evaluation based on consequences.
- Performance measure: Notion of desirability.
- Reward: +1 point for ...

We should <span style="background:rgba(183, 152, 255, 0.3)">design the performance based on how well the model performs</span>, not on how we think hit should achieve the result.

For each possible percept sequence, a rational agent should select an action that is expected to maximise its performance measure.

## Ingredients

- Performance measure: measure of how well the model is performing
- [Environment](Environment.md)
- Actuators: Conditions that make the agent act. Real???
- Sensors: Component that enables the agent to perceive the environment.


## Rationality

Ingredients:
- Performance measure
- Agent's prior knowledge of the environment
- Actions the agent can perform
- Agent's percept sequence to date

Rationality is not omniscience tho, we are learning to extend prior knowledge, or else the agent would lack autonomy???


## Reflex Agent:

```
if status == Dorty:
	return Suck
else if location == A
	return Right
else if status == B
	return Left
```

![](../z_images/Pasted%20image%2020230227170710.png)


## Model-based reflex agent:

It requires a transition model and a sensor model. Idk man...

![](../z_images/Pasted%20image%2020230227170740.png)

## Goal-based and utility-based agents:

- #### Goal based:
	Keeps track of the world state and a set of goals that it's trying to achieve. Then it <span style="background:rgba(183, 152, 255, 0.3)">chooses an action that will eventually lead to the achievement of its goals</span>.
	This is done by basically understanding what its action do, predicting the outcome of the action and then actually acting on it to achieve the goal.
	![](../z_images/Pasted%20image%2020230227170839.png)

- #### Utility based:
	To avoid conflicting goals, we have a performance measure based on utility. <span style="background:rgba(183, 152, 255, 0.3)">It will choose the action that is expected to have the best utility</span>.
	![](../z_images/Pasted%20image%2020230227170931.png)

## Learning agent:
The system adapts to the environment. There is a <span style="background:rgba(183, 152, 255, 0.3)">performance assessment to know if the learning is working</span> or not, <span style="background:rgba(183, 152, 255, 0.3)">the learning agent actually changes the performance agent to try and improve</span> its performance.

![](../z_images/Pasted%20image%2020230227172131.png)


## World state representation

- **Atomic** representation: Indivisibile states, <span style="background:rgba(183, 152, 255, 0.3)">automata-like</span>.
- **Factored** representation: Set of attributes, <span style="background:rgba(183, 152, 255, 0.3)">such as coordinates</span> or scalar values.
- **Structured** representation: Relations between concepts, objects, relational databases. (ex. <span style="background:rgba(183, 152, 255, 0.3)">if we want every car in the room to be black</span>)

![](../z_images/Pasted%20image%2020230227172725.png)