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
