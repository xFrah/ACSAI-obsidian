---
aliases:
  - Regular language
  - language
  - languages
---
A language L is said regular if there exists a finite automaton that accepts L.

> [!example] Exercise
> The language of all binary strings that contain the string $001$ as a substring is regular?
> We must find an automaton that accepts it.
> 
> So we must seek the pattern of two zeros followed by a 1.
> 
>  1. Haven't just seen any symbols of the pattern
>  2. Have just seen a 0
>  3. Have just seen 00
>  4. Have seen all 001

---

## Closure properties

A collection of objects is closed under some operation if applying that operation to members of the collection returns an object in the collection.

> [!example]
> In the set of natural numbers, addition is such an operation, while division is not.


Regular languages are closed(the result is a regular language) under these 3 operations:

- **Union**
- **Concatenation**
- **Star**: concatenation of a language with itself as many times as you want.

But we need to [[1.45,1.47,1.49 - Closures of Regular Languages|prove this]]. 
And they are also better explained [[Regular Expressions|here]].

> [!example]
> ![](../z_images/Pasted%20image%2020230927123636.png)

> [!note]
> A string is accepted by an [automata](Finite%20Automata.md) if and only if the automata starting at the initial state ends in an accepting state after reading the string.
> A language accepted by an automata is a set of strings accepted by the automata.

---

## Other minor operations

![](../z_images/Pasted%20image%2020231003121324.png)