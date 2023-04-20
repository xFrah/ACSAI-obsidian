A symmetric matrix is a [matrix](Matrix.md) that has equal values on both sides of its diagonal.

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

---

## Creating symmetry

Symmetric matrices are very powerful, so we artificially create symmetry to take advantage of it.

If we multiply any [rectangular matrix](Rectangular%20matrix.md) to its transposed, we get a square matrix, that is also symmetrical.
$$\Large \begin{bmatrix}
1 & 2 & 3 \\
4 & 5 & 6
\end{bmatrix}\begin{bmatrix}
1 & 4 \\
2 & 5 \\
3 & 6
\end{bmatrix}^T = \begin{bmatrix}
14 & 32 \\
32 & 77
\end{bmatrix}$$

We can also do it both ways:
$$\Large\begin{bmatrix}
1 & 4 \\
2 & 5 \\
3 & 6
\end{bmatrix}^T \begin{bmatrix}
1 & 2 & 3 \\
4 & 5 & 6
\end{bmatrix}= \begin{bmatrix}
17 & 22 & 27\\
22 & 29 & 36 \\
27 & 36 & 45
\end{bmatrix}$$

So we just created two square symmetrical matrices from a singular rectangular matrix.

We all these two matrices:
$$\Large S_L=\begin{bmatrix}
14 & 32 \\
32 & 77
\end{bmatrix}, \quad S_R=\begin{bmatrix}
17 & 22 & 27\\
22 & 29 & 36 \\
27 & 36 & 45
\end{bmatrix}$$

