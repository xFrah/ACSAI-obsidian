---
aliases:
  - Automaton
---
## Finite Automata (DFA)

A finite automaton is a 5 tuple (set of states, alphabet, transition function($Q \times \Sigma \rightarrow Q$), start state, set of accepted final states)

When an automaton receives an input string, it **reads the characters one by one** and **passes them to the transition function**.

This leads the automaton to an arrival state, which may or may note be in the set of accepted final states, if it is, we accept the input, if it is not, we reject it.

> [!note]
> Every state in a DFA has an outgoing arrow for each symbol of the alphabet.

---

## Non-deterministic automata (NFA)

Each state can have multiple exiting arrows for a single symbol.

When computing in this scenario, if a symbol takes to multiple paths, you make multiple copies of the automata leading to all possible paths, **the ones that can't accept the input just die**.

> [!tldr]
> When there is a non-deterministic state change, the instance of the automata gets forked.


The machine **accepts** if there exists **at least one** of the computation branches that **ends in an accepted state**.

![](../z_images/Pasted%20image%2020230927112857.png)


> [!hint] Formal definition
> The crucial difference is in the transition function: 
> - In a DFA, the transition function produces the next state;
> - In an NFA, the transition function produces the set of possible next states.
>   
>   ![](../z_images/Pasted%20image%2020230927113542.png)

---

## Equivalence of NFA and DFA

They both can do the same thing. For every non deterministic automaton, there exists a deterministic automaton that can accept the same language ([[1.39 - DFA = NFA|proof here]]).

### NFA to DFA conversion

Instead of states, the new DFA will have groups of states from the original NFA.
You can think of them as: "The set of possible states that we can reach from a particular point without any other input"

![](../z_images/Pasted%20image%2020241011114755.png)


This is the converted DFA:

![](../z_images/Pasted%20image%2020241011114809.png) 

> [!hint] Tips for drawing the converted DFA
> If the original NFA has $k$ states, the converted DFA will have $2^k$ states.
> So you can just draw every possible combination of states, and THEN draw the arrows.


In the NFA the starting state is 1, but without any further input we can also reach 3, so in the DFA, the starting state is {1, 3}.

If from this {1, 3} state we input a, we could go back to 1, which without further input, can lead to 3, so we are still in {1, 3}.

If we instead input b, we will go to {2}.

> [!hint]
> 2 is alone in its group, it means that without any further input, we cannot go anywhere from here. Or that in NFA we would certainly be in state 2 at this point.


At this point, if we input a, we can either go to 2 or 3. So if we input a, without further input, we can be either in state 2 or 3. 
