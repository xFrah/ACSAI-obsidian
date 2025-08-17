---
aliases:
  - pushdown automata
  - push-down automata
  - pushdown automaton
  - pushdown automatons
  - push-down automatons
  - push-down automaton
---
A pushdown [[Automata|automaton]] is a machine that recognizes [[Context-Free Grammars]] and [[Context-Free Grammars#Context-free language|languages]].

It's basically an NFA, but it has its own way to "count" characters, so it doesn't have the limitation that is hunted down by the [[1.70 - Pumping Lemma|Pumping Lemma]].

It uses a "stack" with infinite memory to "count". In particular, when transitioning to a state, we can (in order):
1. Read the character
2. Pop from the stack
3. Push to the stack

The notation for transition arrows is as follows:

$$\Large \underbracket{a}_{\text{read}},\underbracket{b}_{\text{push}}\rightarrow \underbracket{c}_{\text{pop}}$$

> [!note]
> We can also push and pop $ε$ to and from the stack, meaning that we can also not use it. 
> It would be the common NFA behaviour.

> [!warning]
If you try to pop from an empty stack, the machine will stop.

> [!example]
> Assume we have a CFG with rule:
> 
> $$\Large S\rightarrow 0S1 \;| \;ε$$
> 
> which translates to the language:
> 
> $$\Large L=\{0^n1^n\;;\;n\geq 0\}$$
> 
> In this "matching" case the stack starts empty:
> - When $0$ is read, we push onto the stack.
> - When $1$ is read, we pop from the stack.
>   
> 
> 
> ![[Pasted image 20250815113448.png]]
> 
> 1. The first thing we do, is push a symbol $\$$ on the stack, which will be the base symbol of the stack. Basically if we reach it again at some point of the automaton, we should be able to accept it and go to a final state.
> 2. We create a loop for reading the $0$'s and push them onto the stack.
> 3. We make an $ε$ transition for when we need to switch to reading $1$'s.
> 4. We create a loop for reading the $1$'s and pop them from the stack.
> 5. We create a transition for reading the symbol $\$$ at the base of the stack, which signals that we can go to a finish state.

