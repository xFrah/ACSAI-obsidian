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

It uses a "stack" with infinite memory to "count".
Assume we have a CFG with rule:

$$\Large S\rightarrow 0S1 \;| \;ε$$
which translates to the language:

$$\Large L=\{0^n1^n\;;\;n\geq 0\}$$

In this kind of automaton, when transitioning to a state, we have to:
1. Read the character
2. Pop from the stack
3. Push to the stack

