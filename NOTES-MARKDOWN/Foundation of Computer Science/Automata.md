Finite automata are models for computesr with a finite amount of memory, because the memory are the states.

A finite automaton is a 5 tuple (set of states, alphabet, transition function($Q \times \Sigma \rightarrow Q$), start state, set of accepted final states)

When an automaton receives an input string, it reads the characters one by one and passes them to the transition function.

This leads the automaton to an arrival state, which may or may note be in the set of accepted final states, if it is, we accept the input, if it is not, we reject it.


## Regular languages

A language L is said regular if there exists a finite automaton that accepts L.

> [!example] Exercise
> The language of all binary strings that contain the string $001$ as a substring is regular?
> We must find an automaton that accepts it.
> 
> So we must seek the patter of two zeros followed by a 1.
> 
>  1. Haven't just seen any symbols of the pattern
>  2. Have just seen a 0
>  3. Have just seen 00
>  4. Have seen all 001

---


## Non-deterministic automata

There are several choices for any change of state. Each state can have multiple exiting arrows for a single symbol.

When computing in this scenario, you make multiple copies of the automata leading to all possible paths, **the ones that can't accept the input just die**.

> [!tldr]
> When there is a non-deterministic state change, the instance of the automata gets forked.


The machine accepts if there exists at least one of the computation branches that ends in an accepted state.

![](../z_images/Pasted%20image%2020230927112857.png)


> [!hint] Formal definition
> The crucial difference is in the transition function: 
> - In a DFA, the transition function produces the next state;
> - In an NFA, the transition function produces the set of possible next states.
>   
>   ![](../z_images/Pasted%20image%2020230927113542.png)

---


## Equivalence of NFA and DFA

They both can do the same thing. For every non deterministic automaton, there exists a deterministic automaton that can accept the same language.

> [!warning]
> This is a proof that will probably be included in the exam. Slide 2 page 10.
