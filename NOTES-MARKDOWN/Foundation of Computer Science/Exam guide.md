![[Pasted image 20250809121914.png]]
![[Pasted image 20250809121918.png]]

## Exercises

1. Given the language, write the correspondent [[PDA]]
2. Given the following grammar, write the correspondent [[Finite Automata|automaton]]
3. Given the automata, write the grammar
4. Turn the following automata into a right-linear grammar
5. Is the following language regular?
6. Determine if a language is regular, provide a [[Regular grammars|regular grammar]], or prove that it's not
7. Is the following language context-free?
8. Given the language, write the grammar
9. Write the [[Context-Free Grammars|CFG]] equivalent to the following language
10. Given the [[Finite Automata|DFA]], write the [[Regular Expressions|Regex]]
11. Given the Regex, write the [[Finite Automata|NFA]]

### Given the language, write the correspondent [[PDA]]

[[PDA]]'s are used when you have "simmetry" in the grammar (usually between 2 symbols).

Order of operation:
1. Read the character
2. Pop from the stack
3. Push to the stack

Notation for transition arrows:

$$\Large \underbracket{a}_{\text{read}},\underbracket{b}_{\text{push}}\rightarrow \underbracket{c}_{\text{pop}}$$

1. First thing in the exercise, we need to push the delimiter symbol $\$$.

2. Then you push the first symbols, and pop the other "symmetric" symbols. 

3. Then if you can pull $\$$ from the stack and go to a final state, do it.

> [!hint]
> Sometimes, the language that you need to convert to a PDA has a union.
> In that case you just construct another branch of the PDA.

> [!hint]
> Sometimes you don't need the stack, and you can use the [[PDA]] as an [[Finite Automata|NFA]].

> [!warning]
> DO SOME EXERCISES!

---

### Given the following grammar, write the correspondent automata

Apparently, we are talking about [[Regular Grammars]], and conversion should be possible only with right-linear grammars.

- Turn each variable on the left into a state.
- The start symbol becomes the initial state.
- The states with a transition to $ε$ become a final state.
	- You can also add a final state $\Sigma$ if multiple transitions go to only terminals.

> [!warning]
> DO SOME EXERCISES!
