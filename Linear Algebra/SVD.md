SVD stands for singular value decomposition.
Sometimes it is useful to decompose transformation matrices in multiple matrices that only do a type of transformation each.

The difference with [spectral decomposition](Spectral%20decomposition.md), is that SVD doesn't require a [symmetric matrix](Symmetric%20matrix.md), but just about any [matrix](Matrix.md).

SVD says that any matrix, regardless of symmetry, rank or shape, can unconditionally be decomposed into 3 special matrices.

![](../z_images/Pasted%20image%2020230309152504.png)


## Explanation:

$$\large AV=U\Sigma$$
**Where:**
- A is any matrix.
- V are the orthonormal vectors that, once transformed by A, remain orthonormal.
- $\Sigma$ is a diagonal matrix that scales the basis vectors before they are rotated.
- U is the rotation that brings the basis vectors 


**What does it mean:**
$$\large V = \begin{bmatrix}
v_1\\v_2
\end{bmatrix},\quad
U = \begin{bmatrix}
u_1\\u_2
\end{bmatrix}, \quad
\Sigma = \begin{bmatrix}
\sigma_1 \\ \sigma_2
\end{bmatrix}$$
$$\large Av_1 = u_1\sigma_1$$<center>and</center>$$\large Av_2 = u_2\sigma_2$$
The vectors in U are the vectors of V after being transformed by A(they remain orthonormal by definition of V).

$AV$:
For some reason we found the pair of vectors that when transformed by $A$, remain orthonormal.
We now put them through A and end up with orthonormal vectors.

$U\Sigma$:
We have the scaling information in the $\Sigma$ matrix, then we rotate those scaled vectors to where they are after $AV$(by applying $U$, by $U$ definition).


## How do we get U and V?

We make spectral decomposition of AA^T, which returns a symmetrical matrix.
We can also do A^TA, which also returns another symmetrical matrix.

Those two matrices have something in common with the original matrix apparently.
V and U's columns are the eigenvectors of those two symmetrical matrices.

![](../z_images/Immagine%20WhatsApp%202023-03-12%20ore%2017.35.10.jpg)