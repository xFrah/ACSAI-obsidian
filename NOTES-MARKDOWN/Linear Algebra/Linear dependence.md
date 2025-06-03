---
alias: linearly dependent, linearly independent, linear dependencies, linear dependence, linear independence
---
A set of [vectors](Vectors.md) is said to be linearly dependent if at least one vector in the set can be expressed as a [linear combination](Linear%20Combination.md) of the other vectors.

We can check for linear dependence/independence between multiple vectors by writing down the following equation:

$$\large c_1v_1+c_2v_2+\dots+c_kv_k=0$$

> [!hint]
> Vectors are linearly independent when there are no scalars $c1$​ and $c2​$ other than zero that can make the linear combination equal to the zero vector.


The equation above gives us an homogeneous [system of linear equations](Systems%20of%20Linear%20Equations.md), and we now gotta check if it has an unique solution or not.

There are two cases:

### The coefficient matrix is a square

In this case we just find the [determinant](Determinant.md).
If $\text{det}(A)\neq 0$ then $c_1=c_2=\dots=c_k=0$ and the system is linearly independent.

> [!example]
> ![](../z_images/Pasted%20image%2020230815171246.png)

### The coefficient matrix is rectangular

Use [Gaussian Elimination](Gaussian%20Elimination.md) or [Gauss-Jordan Elimination](Gaussian%20Elimination.md) on the augmented [matrix](Matrix%20(ML).md) to find the solution.
If $c_1=c_2=\dots=c_k=0$ then the vectors are linearly independent.

> [!example]
> ![](../z_images/Pasted%20image%2020230815171231.png)

