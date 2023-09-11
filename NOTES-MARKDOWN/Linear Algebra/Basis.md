A set of [vectors](Vectors.md) $S=\{v_1, v_2, \dots, v_n\}$ in a [vector space](Vector%20spaces.md) $V$ is called a basis for $V$ if:
1) $S$ [[Spanning set|spans]] $V$.
2) $S$ is [linearly independent](Linear%20dependence.md).


> [!example]
> ![](../z_images/Pasted%20image%2020230816174951.png)

> [!warning]
> What the fuck is this?
> ![](../z_images/Pasted%20image%2020230816175045.png)

> [!warning]
> What the fuck is this pt.2
> 
> ![](../z_images/Pasted%20image%2020230816175239.png)

---

## A few theorems

> [!quote] Theorem 1
> If $S=\{v_1, v_2, \dots, v_n\}$ is a basis for a vector space $V$, then every set containing more than $n$ vectors is [linearly dependent](Linear%20dependence.md).
> 
> $\mathbb{R}^2$ has two basis vectors, while $\mathbb{R}^3$ has 3.
> 

> [!quote] Theorem 2
> If a vector space $V$ has one basis with $n$ vectors, then every other basis for $V$ should have $n$ vectors.

> [!quote] Dimension of Vector Space
> If a vector space $V$ has a basis consisting of $n$ vectors, then the number $n$ is called the dimension of $V$ and denoted by $\text{dim}(V)=n$
> 
> ![](../z_images/Pasted%20image%2020230816180314.png)


### COMPLETE PAGE 4-6 in Basis paper

---

## How to find a basis for a matrix

### Row space

If we wanted to find the Row Space of a given [matrix](Matrix%20(ML).md) $A$, we would need to use elementary row operations to convert $A$ into row echelon form.

The non-zero row vectors in [R.E.F](Gaussian%20Elimination.md). form a basis for the row space of $A$.

> [!example]
> ![](../z_images/Pasted%20image%2020230817124515.png)


### Column space

We either do the same thing with $A^T$, or:

We take the R.E.F. again, then the columns of matrix B, which are Linearly independent because they have leading 1's, are also Linearly independent in A, and these columns in A form the basis of the column space of A.

> [!example]
> ![](../z_images/Pasted%20image%2020230817131432.png)

> [!note]
> This method doesn't necessarily give the same basis that results from the Transpose method.

---

## How to find basis for a subspace

The technique above can be also used for this.
We have the set $S=\{v_1, v_2, \dots, v_k\}$ that [spans](Spanning%20set.md) a subspace in $\mathbb{R}^n$.
The idea is to use the vectors in $S$ as the rows of a matrix $A$, then rewrite $A$ in [R.E.F](Gaussian%20Elimination.md).

> [!example]
> ![](../z_images/Pasted%20image%2020230817125734.png)

---

