Used to **prove** that certain **languages are non-regular**.
If the lemma is satisfied, it **doesn't mean that the language is necessarily regular** (it could be proven non-regular through other means).

> [!hint]
> A language is regular if and only if there **exists a finite automaton that accepts it**.
> For an automata, recognizing a language implies **accepting every string contained** in it, and **rejecting every string not contained** in it.

> [!important]
> All **finite languages are regular**. We can make a DFA for every string in the language and then unite them all into one.


Assume we have a example of finite automaton (DFA) like this one:

![](../z_images/Pasted%20image%2020241119125349.png)
Is it possible to always guarantee that loop in the middle? 
The answer is **YES**, but we need to prove it.

> [!hint] Why not use NFA's?
> You can't guarantee a loop with NFA, because there is no guaranteed path. Especially considering we can have infinite **ε** paths.
> 
> ![](../z_images/Pasted%20image%2020241119125243.png)

---

## Why is it useful

Consider the language C = {$w | w$ has an equal number of 0s and 1s}, we want to prove that it's not regular.

> [!important]
> For an automata, recognizing a language implies **accepting every string contained** in it, and **rejecting every string not contained** in it.


We take as example the string **0011** and we construct an automata that accepts it:

![](../z_images/Pasted%20image%2020241121151608.png)

In this specific case, you can see that while it accepts **0011**, it also accepts **0111**, which is NOT in the language (because it has unequal amount of **0**'s and **1**'s).

> [!attention]
> This phenomenon can be summed up as the notion that **a DFA can't keep track of the history of it's states**, so in this specific case, it can't count the number of **1**'s and **0**'s, hence it's impossible to construct an automata that distinguishes the two strings mentioned.


**This scenario can be detected by using the pumping lemma**, which is explained below.

---

## The actual Pumping Lemma

If A is a regular language, **these conditions must be respected for every string** $s$, which is divided into 3 parts $xyz$:
1. $xy^iz$ for every $i$ is always in $A$
2. $|y|>0$
3. $|xy|<=|s|$

The goal is to **find a string that doesn't respect these conditions**, to show that $A$ is not regular.

## Usage

Choose a string, choose $i$ and test all possible decompositions into $xy^iz$.


