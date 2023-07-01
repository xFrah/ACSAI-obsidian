![](../z_images/Pasted%20image%2020230701120225.png)

### What is the dimensionality of the samples in the design [matrix](../Linear%20Algebra/Matrix.md)?

Well the exercise tells us that the columns are the samples, so there are 2 dimensions.
There are 5 samples.


### Complete $\mu$ (empirical average) and $\Sigma$ (covariance matrix)

The $\mu$ matrix is composed of the averages for each dimension.

$$\large\mu = \LARGE\begin{bmatrix}\frac{-4+9+4+0-3}{5} \\ \frac{10-4+8+0+0}{5}\end{bmatrix}$$

We compute the [covariance matrix](../Machine%20Learning/Covariance%20matrix.md) in the following way:

$$\large \Sigma = \frac{1}{n-1}XX^T=\frac{1}{4}\begin{bmatrix}
-4 & 9 & 4 & 0 & -3 \\
10 & -4 & 8 & 0 & 0
\end{bmatrix} \begin{bmatrix}
-4 & 10 \\
9 & -4 \\
4 & 8 \\
0 & 0 \\
-3 & 0
\end{bmatrix}$$
$$\large= \frac{1}{4}\begin{bmatrix}
122 & -44 \\
-44 & 180 
\end{bmatrix}=
\begin{bmatrix}
 30.5 & -11\\
 -11 & 45
\end{bmatrix}$$

> [!hint]
> There are a few methods for matrix multiplication:
> 
> 
> ### Basis vectors method
> You remember that the columns of the matrix on the left are actually basis vectors.
> So you need to substitute them to the basis vectors of the two vectors in the matrix on the right.
> 
> 
> $$\large v_1 = -4 \begin{bmatrix}
-4 \\ 10
\end{bmatrix} + 9 
\begin{bmatrix}
9 \\ -4
\end{bmatrix}+ 4 
\begin{bmatrix}
4 \\ 8
\end{bmatrix}+ 0 
\begin{bmatrix}
0 \\ 0
\end{bmatrix}-3
\begin{bmatrix}
-3 \\ 0
\end{bmatrix}$$
> $$\large v_2 = 10 \begin{bmatrix}
-4 \\ 10
\end{bmatrix} + -4 
\begin{bmatrix}
9 \\ -4
\end{bmatrix}+ 8 
\begin{bmatrix}
4 \\ 8
\end{bmatrix}+ 0 
\begin{bmatrix}
0 \\ 0
\end{bmatrix}+0
\begin{bmatrix}
-3 \\ 0
\end{bmatrix}$$
> 
> 
> ### Dot product method
> You compute the dot product between the rows of the first matrix and the columns of the second matrix.
> 
> ![](../z_images/Pasted%20image%2020230701131314.png)
> ![](../z_images/Pasted%20image%2020230701131332.png)

---


![](../z_images/Pasted%20image%2020230701134902.png)


### Describe the process that applies those transformations

1. We get the [covariance matrix](../Machine%20Learning/Covariance%20matrix.md) of the point cloud, which can be computed with $\frac{1}{n-1}XX^T$
2. Using [PCA](../Machine%20Learning/PCA.md)/[Spectral decomposition](../Linear%20Algebra/Spectral%20decomposition.md), we get the [eigenvectors](../Linear%20Algebra/Eigenvectors%20and%20Eigenvalues.md) of the covariance matrix.
3. We centre the point cloud by subtracting the mean from all the points.
4. We apply the transposed eigenvectors matrix so to bring the eigenvectors to our basis vectors.
5. Now we swap the two eigenvectors/principal components.
6. We apply the new eigenvector matrix and so that the basis vectors end up on the new eigenvectors.
7. We add the mean back to all the points.

![](../z_images/Pasted%20image%2020230701155847.png)