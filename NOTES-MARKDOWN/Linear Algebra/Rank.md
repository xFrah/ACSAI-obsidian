First off, the row [vectors](Vectors.md) and column vectors span their individual [vector spaces](Vector%20spaces.md).

![](../z_images/Pasted%20image%2020230817123253.png)


The vector spactor spaces spanned by the row vectors and column vectors are called respectively Row space(R.S.) an Column space(C.S.).

---

## Definition of Rank

If $A$ is an $m$x$n$ [matrix](Matrices.md), then the Row Space and the Column Space of $A$ have the same dimension.
This dimension is called the rank of $A$ and is denoted by $\text{rank}(A)$.
More precisely, the rank is the **number of dimensions in the Column Space**.

> [!hint] Intuitive explanation
> The rank is the **dimensionality in the output of a transformation**.
> If the space gets squished into a line, the rank is 1, if the space gets squished onto a plane, the rank is 2, ecc...
> 
> Intuitively, if a matrix has dimensionality 2 and the rank is 1, it means that the determinant is 0, because we have squished the space.

> [!example]
> In this example we use the method described as the second method for computing the basis of the column space in the [Basis file](Basis.md).
> ![](../z_images/Pasted%20image%2020230817191929.png)

