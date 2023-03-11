SVD stands for singular value decomposition.
Sometimes it is useful to decompose transformation matrices in multiple matrices that only do a type of transformation each.

The difference with [spectral decomposition](Spectral%20decomposition.md), is that SVD doesn't require a [symmetric matrix](Symmetric%20matrix.md), but just about any [matrix](Matrix.md).

![](../z_images/Pasted%20image%2020230309152504.png)


## What?

SVD says that any matrix, regardless of symmetry, rank or shape, can unconditionally be decomposed into 3 special matrices.


## Creating symmetry

Symmetric matrices are very powerful, so we artificially create symmetry to take advantage of it.

If we multiply any rectangular matrix to its transposed, we get a square matrix, that is also symmetrical.
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

