An agent is anything that perceives its environment and acts accordingly.

> [!example]
> **Human agent:**
> ● Sensors: Eyes, Ears, Skin, Tongue, Nose
> ● Actuators: Hands, Legs, Mouth, etc. etc...
> **Robotic Agent:**
> ● Sensors: Cameras, Lidars
> ● Actuators: Motors (wheels, legs, grippers)


## Agent function

An agent is specified by an agent function

$$\large f: P\rightarrow a$$
where:
- $P$ is the perception vector of the environment
- $a$ is an action from the set of possible actions

## Rational agent

An agent that always does the right thing for the current state of the environment.

It basically takes the action that is **expected** to maximise its performance.


> [!note]
> Using only a priori knowledge is sub-optimal.
> A rational agents should be autonomous, it should learn
through experience and update its initial beliefs.


## Utility function

The performance measure done by the agents is called utility function.
This function helps the agent understand what's the worst and best action to take.

## Different types of agents

- **Reflex** agent: Selects an action based only on the current perception, ignores past history.
	
> [!example]
> ![](../z_images/Pasted%20image%2020240510113321.png)

- **Model-based Reflex** agent: Has an internal model of the world to keep track of environment, including what it can't see at the moment.
	
- **Goal-based**(**planning**) agent: Receives a goal information that describes what situations are desirable. *This requires considering the impact of future actions*.
	
> [!hint]
> We do this through the utility function, which helps us distinguish between better and worse ways of succeeding in the task.


## World state representations

- **Atomic**: Each state of the world is indivisible
	
> [!example]
> [Search](Search.md), game playing(chess), ecc...
	
- **Factored**: Each state is split into variables and two states can share some variables.
	
- **Structured**: Allows to describe objects within the environment with their own set of characteristics attributes and relationships.
	
> [!example]
> First order logic
