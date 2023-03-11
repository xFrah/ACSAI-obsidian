A symmetric matrixi is a [matrix](Matrix.md) that has equal values on both sides of its diagonal.

![](../z_images/Pasted%20image%2020230311123400.png)

It is describable by:
$$\Large A_{ji}=A_{ij}$$


```ad-info
title: Why are they useful?
The eigenvectors are perpendicular to each other.

That means that if we pack the eigenvectors(normalized) into a matrix, we obtain an orthogonal matrix that describes a rotation of the basis vectors to the eigenvectors.

‎ 

But the cool thing is:

If we transpose this orthogonal matrix, we get its inverse, so the counter to the original rotation.
```


```ad-hint
Non-square matrices cannot be symmetrical.
```

```ad-info
If the matrix is symmetrical, the eigenvectors are perpendicular.

Why?
```
