Sets are collections of elements
There are three different ways to describe sets.
1. Textual: EX. IDs of the courses of spapienza
2. Extensional: Enumerations of elements in the set.
3. Intensional: Indication of the conditions that the elements in the set must fulfil, EX. x belongs to the set if x is a course of sapienza.

![](../z_images/Pasted%20image%2020230303144805.png)

Axiom of extensionality:
We don't care about duplicates, {a, b, c} is equal to {a, a, b, c}

Cardinality(|S|):
The count of the elements within the set, |{a, b, c}| = 3.

Countably infinite:
A set S is countably infinite if it has the cardinality of N.

Finite set:
A set S is finite if there exists n ∈ N and |S| ≤ n

Infinite set:
If the cardinality of S is higher than א, then the set is infinite.

Empty set:
We denote empty sets as {} or ∅, its cardinality is 

Singleton:
Set of cardinality 1.

Power-Set:
Given a set A, 2^A is the power-set of A. (Set of all subets of A)
2^A because 0 and 1 are the symbols, 0 indicates that the element is not in the set, 1 indicates that it is. So if we get all the combinations of this sequence, we get all the possible subsets for that elements.

{a, b, c}
{0, 0, 0} -> {}
{0, 0, 1} -> {c}
{0, 1, 0} -> {b}
{0, 1, 1} -> {b, c}
{1, 0, 0} -> {a}
{1, 0, 1} -> {a, c}
{1, 1, 1} -> {a, b, c}


## Cross product

A cross product of two sets is the set of all ordered pairs that have one element from each operand:

<center>A × B ≝ a, b a ∈ A, b ∈ B}</center>

A tuple is an element of the cartesian product of sets.
Can a tuple have variable length.
Tuples:
We call tuples the elements of a product of k sets, where k ∈ N\{0}
EX. Pair, triple, quadruple, quintuple, sextuple, septuple, octuple, ..., k-tuple

Let A, B, and C be sets A = 1,2 , B = a, b, c , C = {x, y}
Then A × B × C = (1, a, x ), (1, a, y) , (1, b, x ), (1, b, y) , (1, c, x ), (1, c, y), (2, a, x), (2, a, y) , (2, b, x), (2, b, y), (2, c, x ), (2, c, y)


## Multi-set

Multiple-membership sets allow for multiple occurrences of the same element to occur.
Technically, a multi-set is a function.

It maps any set to a natural number.


## Sequences

Sequences are [functions](Functions.md) whose domain is the set of positive integers.
Think of an array, it can map shit to indexes evenly spaced?
