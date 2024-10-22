---
aliases:
  - Regular language
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

But we need to prove this.

> [!example]
> ![](../z_images/Pasted%20image%2020230927123636.png)

> [!note]
> A string is accepted by an [automata](Automata.md) if and only if the automata starting at the initial state ends in an accepting state after reading the string.
> A language accepted by an automata is a set of strings accepted by the automata.

---

## Closure proofs


How do i prove that the if A and B are regular, the union(for example) of A and B is still regular?
We create a general automaton and show that it recognizes the resulting language.

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

---

## Other minor operations

![](../z_images/Pasted%20image%2020231003121324.png)