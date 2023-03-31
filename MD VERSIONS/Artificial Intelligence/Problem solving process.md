1. Goal formulation: Limit objectives
2. Problem Formulation: Abstract model of the world
3. Search: Simulate actions sequences till a solution is found or it is found that no solution exists
4. Execution

Assumption:
- [Environment](Environment.md) is fully observable, deterministic and known.
- The [agent](Agent.md) can ignore percepts during execution (open loop?)
- In an unknown envirnment, execute random action!

Wtf complete the lesson!!!!!!! The search problem dude.
s -> 2^A = P(A), Weierstrass???
2^a le possibili azioni da prendere???? diom

![](../z_images/Pasted%20image%2020230303143326.png)

State space = all the possible states
Goal states =
Action is what triggers the transition from one space to another.
Often the actions are connected to a cost.

A solution is walk, from initial state to goal state.
A solution should be measured by the performance measure.

Partial function = We can't do every action from every state, some states can only allow certain actions(sliced arrow)
Total function = We can do every action in every state with every action

A = {toRM, toLT, toNA, toFR}
S = {RM, LT, FR, NA}
Actions = {(RM, toLT, LT), (RM, toFR, FR), (RM, toNA, NA)} the last action is forbidden for rome, because it cant go to NA
(state, action, next_state)

