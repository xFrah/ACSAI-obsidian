How many possible orderings of $n$ elements are there?

Imagine we have an array of elements $[1, 2, \dots, n]$ and we want to re-order it.
**We select the first element** from the array: we have $n$ possible choices and $n$ possible combinations
**We select the second element**: we have n-1 possible choices for this element.

$$\large |\Omega ×\Omega_{\backslash e_1}|= n\cdot (n-1)$$

> [!hint]
> This is the [multiplication rule](Multiplication%20rule.md).


The total number of choices can also be expressed by:

$$\large n! = n(n − 1)(n − 2)· · · 1.$$