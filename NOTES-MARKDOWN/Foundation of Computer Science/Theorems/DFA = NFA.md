For any NFA, there exists an equivalent DFA.

$$\Large L(M)=L(N)$$
## Proof

The idea here is to demonstrate that we can convert every NFA to a DFA that accepts the same language.
First, we need to remember how the [[Automata#NFA to DFA conversion|conversion from NFA to a DFA]] actually works.

Then, we define our NFA and our new DFA:
- $\large N = (Q,Σ,δ,q_0,F)$
- $\large M = (Q',Σ,δ',q_0',F')$

![[Pasted image 20250809164122.png]]


### Building the new DFA

1. We define $Q'$ as a set of subsets of $Q$, essentially a set of groups of states of the NFA.

2. We define the transition function for the converted DFA as:
	
$$\Large δ'(R,a) = \bigcup_{r\in R}δ(r,a)$$
	Where $R$ is a state of the new DFA (set of states from $Q$) and $r$ is a state from $R$.

> [!hint]
> This means that the next state in the new DFA, given $(R, a)$, equals to the unions of all the possible next states in the NFA, given all the $(r_i, a)$ in $R$.


3. $q_0'$ is a state of $Q'$ that contains ONLY the starting state from the NFA.

$$\Large q_0' = \{q_0\}$$

> [!hint]
> It's a set of states $R$ containing only one $r_i$.


4. $F'$ is a set of states frpm $Q'$, with each state having at least one accept state from the NFA inside of it.

