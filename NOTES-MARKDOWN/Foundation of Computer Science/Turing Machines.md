---
aliases:
  - tm
  - tm's
  - tms
---
A turing machine is a type of automata that generalizes all other types of automata ([[Finite Automata|DFA]], [[Finite Automata|NFA]] and [[PDA]]).

![[Pasted image 20250818105414.png]]


It does so by allowing both reading and writing and unbounded work space.

## Features

- Infinite tape divided into cells as memory, 
- A head that reads/writes a symbol and moves left or right, 
- A finite set of states (including a start and halting/accept states),
- A transition table that dictates what to write, how to move, and which state to enter based on the current state and read symbol.
- Inputs are accepted or rejected immediately, it stops computation as soon as an invalid input happens.

The machine starts with the input on the tape and blanks elsewhere; it repeatedly applies its transition rules until it halts (accept/reject) or runs forever.

> [!example]
> ![[Pasted image 20250818111824.png]]![[Pasted image 20250818111835.png]]


## Formal definition

![[Pasted image 20250818112021.png]]

### Configurations

![[Pasted image 20250818112236.png]]![[Pasted image 20250818112417.png]]

### Accepting languages

![[Pasted image 20250818112442.png]]

---

## Linear Bounded Automaton

![[Pasted image 20250818114809.png]]

---

## Enumerators

![[Pasted image 20250818115112.png]]![[Pasted image 20250818115124.png]]

> [!note]
> The enumerator enumerates a language if it prints **all and only** the strings in the language.
