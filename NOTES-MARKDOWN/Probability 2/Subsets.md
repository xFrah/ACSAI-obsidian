How many ways are there to choose $k$ elements from a set of $n$ elements?

## With ordering

Assume we have the array $[1, 2, 3, 4, \dots, n]$ and we want to create a subset of it.

**We choose the first element**: we have $n$ choices for the first element.

**We choose the second element**: we have $n - 1$ choices for the second element.

**We choose the last element**($k_{\text{th}}$): eventually, we will have chosen $k$ elements, so we subtract $k$ elements from $n$: $n-k\underbracket{+1}_{\text{we got 1 choice}}$

So by [multiplication rule](Multiplication%20rule.md):
$$\large n(n-1)\dotsm(n-k+1)=\frac{n!}{(n-k)!}$$
> [!hint]
> Assume we the array has lenght $5$ and we want a subset of length $2$:
> 
> $$\large \frac{5\cdot4\cdot3\cdot2\cdot1}{3\cdot2\cdot1}$$
> 
> The denominator kills the combinations that would happen if we didn't stop at element $k$ (after $5\cdot 4$).
> 


## Without ordering

In order to do this, it's practical to first choose $k$ ordered elements, and then remove the [permutations](Permutations.md) of the subset.

$$\large \begin{pmatrix}
n\\k
\end{pmatrix}=\frac{n!}{k!(n-k)!}$$

> [!hint]
> $k!$ gets rid of the permutations of the subset of length $k$.

> [!danger]
>![](../z_images/Pasted%20image%2020240710165523.png)


# Subsets with repetitions

## With ordering

This shit is stupid:

$$\large \underbracket{n × n × · · · ×n}_{k\text{ times}}$$

## Without ordering

### WIP