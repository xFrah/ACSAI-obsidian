We know that we can actually combine multiple [transformations](Transformations.md) into just one [matrix](Matrix.md).

This matrix would applied would have the same result than if we applied the individual matrices one after the other.

![](../z_images/Pasted%20image%2020230311131627.png)

And this is called composition of matrices, but did you know that we can also do the opposite process?


## Decomposition

Whenever you have a [symmetric matrix](Symmetric%20matrix.md) S, we can always and unconditionally decompose it in a sequence of three simple matrices:

![](../z_images/Pasted%20image%2020230311142752.png)

What is happening is that:
$Q^T$) We rotate the plane so that the [[Eigenvectors and Eigenvalues|eigenvectors]] end up on the basis [vectors](Vectors.md).
$A$) Once we have the eigenvectors there, we scale them.
$Q$) We rotate the plane so that the eigenvectors end up shere they were before. But now they are scaled.

---

## More detail:

![](../z_images/Pasted%20image%2020230311142934.png)

(The steps are not in order)
- $Q$ is an [[Transformations|orthogonal matrix]], which means that it's a rotation. Its columns are the eigenvectors of S.
	- It makes the basis vectors rotate to the eigenvectors.
	![](../z_images/Pasted%20image%2020230311153429.png)
- $Q^T$ is the inverse of Q, which means that it counters the rotation of Q perfectly.
- A is a diagonal matrix, which means that all the values except the ones on the diagonal, are zero. 
	- Its purpose is to scale the axes. We rotated everything so that we could scale the eigenvectors with this simple matrix.
	![](../z_images/Pasted%20image%2020230311153401.png)

```ad-hint
You can only do this with symmetric matrices.
```
