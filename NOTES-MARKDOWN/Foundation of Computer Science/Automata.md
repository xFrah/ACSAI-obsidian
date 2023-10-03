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

How do i prove that the if A and B are regular, the union(for example) of A and B is still regular?
We create a general automaton and show that it recognizes the resulting language.


> [!warning]
> This is a proof that will probably be included in the exam. Slide 2 page 10.

> [!note] Remember
> A language is regular if every string is accepted by at least one automata.


### Closure under union

> [!hint] Intuition
> Let $A=\{good, bad\}$ and $B=\{boy, girl\}$ be two regular languages.
> Their union will be $A\cup B = \{good, bad, boy, girl\}$. We need to make an automata that accepts this language, knowing that there are automatons that accept $A$ and $B$.
>  
> The solution is to make an automaton that sends the strings to both the automatas that accepted $A$ and $B$. One of the two automata will accept it.


![](../z_images/Pasted%20image%2020230927125118.png)


### Closure under concatenation


> [!warning]
> These are not all the possible permutations, only the ones that start with a string from the first set. 

> [!hint] Intuition
> Let $A=\{good, bad\}$ and $B=\{boy, girl\}$ be two regular languages.
> Their concatenation will be $A\cup B = \{goodboy, badboy, badboy, badgirl\}$. 
> 
> The solution is to make an automaton that accepts the strings that belong to the set $A$ and continue with strings from set $B$.


![](../z_images/Pasted%20image%2020230927124627.png)


### Closure under star

> [!hint] Intuition
> Star is the concatenation of a language with itself as many times as you want.
> 
> The solution is to take the original automata and make arrows that go from the final states to the initial states. If the string is finished it stays in the accepted state, if not it begins again from the start. 
> This can accept every permutation.


![](../z_images/Pasted%20image%2020230927124701.png)