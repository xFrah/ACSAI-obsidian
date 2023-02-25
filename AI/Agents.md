1. The agent is a software that <span style="background:rgba(183, 152, 255, 0.3)">acts</span> upon actuation.
2. The actions of the agent have an effect on the environment.
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
- Environment
- Actuators: Conditions that make the agent act. Real???
- Sensors: Component that enables the agent to perceive the environment.

## Environment

##### Charateristics:
- Observability
	- Fully observable
	- Partially observable
	- Unobservable: no sensors.
- Multiplicity
	- Single agent
	- Multi-agent
		- Competitive
		- Cooperative
- Deterministic v. non-Deterministic
	- Stochastic?
- Episodic v. Sequential
- Static v. Dynamic v. Semi-Dynamic
- Discrete v. Continuous
- Actions's effect
	- Known
	- Unknown