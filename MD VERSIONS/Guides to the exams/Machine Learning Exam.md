## Exercise 1

![](../z_images/Pasted%20image%2020230702135011.png)

### What is the dimensionality of the samples in the design [matrix](../Linear%20Algebra/Matrix.md)?

Well the exercise tells us that the columns are the samples, so there are 2 dimensions.
There are 5 samples.


### Complete $\mu$ (empirical average) and $\Sigma$ (covariance matrix)

The $\mu$ matrix is composed of the averages for each dimension.

$$\large\mu = \LARGE\begin{bmatrix}\frac{-4+9+4+0-3}{5} \\ \frac{10-4+8+0+0}{5}\end{bmatrix}\large = \begin{bmatrix}
1.2 \\ 2.8
\end{bmatrix}$$

We compute the [covariance matrix](../Machine%20Learning/Covariance%20matrix.md) in the following way:

$$\large X_\text{new}=X-\mu = \begin{bmatrix}
-5.2 & 7.8 & 2.8 & -1.2 & -4.2 \\
7.2 & -6.8 & 5.2 & -2.8 & -2.8
\end{bmatrix}$$
$$\large \Sigma = \frac{1}{n}XX^T=\frac{1}{5}\begin{bmatrix}
-5.2 & 7.8 & 2.8 & -1.2 & -4.2 \\
7.2 & -6.8 & 5.2 & -2.8 & -2.8
\end{bmatrix} \begin{bmatrix}
-5.2 & 7.2 \\
7.8 & -6.8 \\
2.8 & 5.2 \\
-1.2 & -2.8 \\
-4.2 & -2.8
\end{bmatrix}$$
$$\large= \frac{1}{5}\begin{bmatrix}
114.8 & -60.8 \\
-60.8 & 140.8 
\end{bmatrix}=
\begin{bmatrix}
 22.96 & -12.16\\
 -12.16 & 28.16
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


![](../z_images/Pasted%20image%2020230702135031.png)


### Describe the process that applies those transformations

1. **We center the point cloud by subtracting the mean from all the points.**
2. We get the [covariance matrix](../Machine%20Learning/Covariance%20matrix.md) of the point cloud, which can be computed with $\frac{1}{n-1}XX^T$
3. Using [PCA](../Machine%20Learning/PCA.md)/[Spectral decomposition](../Linear%20Algebra/Spectral%20decomposition.md), we get the [eigenvectors](../Linear%20Algebra/Eigenvectors%20and%20Eigenvalues.md) of the covariance matrix.
4. We apply the transposed eigenvectors matrix so to bring the eigenvectors to our basis vectors.
5. Now we swap the two eigenvectors/principal components.
6. We apply the new eigenvector matrix and so that the basis vectors end up on the new eigenvectors.
7. We add the mean back to all the points.

![](../z_images/Pasted%20image%2020230702131306.png)


### What happens to the covariance matrix

The variance stays the same but the covariance changes sign:

```
[[1 -0.8]
 [-0.8 1]]
 
[[1 0.8]
 [0.8 1]]
```


### What happens to the determinant

The absolute value of the determinant doesn't change at all because the space doesn't get stretched or shrinked, just rotated.


### Increase the PCs by 5%

Whe need to apply a stretching transformation after step 4.
In order to do that, we need to change the basis vectors with something 5% bigger.

$$\large \begin{bmatrix}
1 & 0 \\
0 & 1
\end{bmatrix} = \begin{bmatrix}
1.05 & 0 \\
0 & 1.05
\end{bmatrix}$$
---


![](../z_images/Pasted%20image%2020230702135049.png)


### Explain why it's bad to use [PCA](../Machine%20Learning/PCA.md) in this case

The classifier won't work because we are projecting the data in a dimension where the classifier can't tell the difference between the two classes.

These will be the 2 principal components.

![](../z_images/Pasted%20image%2020230702120305.png)


If we project all data on the first PC, we get something like this:

![](../z_images/Pasted%20image%2020230702120808.png)


You can't distinguish classes in this scatterplot.


### What would make the classifier work?

Killing the first principal component and projecting everything on the second.

---


## Exercise 2

![](../z_images/Pasted%20image%2020230702135122.png)
![](../z_images/Pasted%20image%2020230702123954.png)

![](../z_images/Pasted%20image%2020230702135152.png)


### Write the density in equation form

Since he doesn't actually want us to compute the results(I THINK), we are gonna write the equations(not the [gaussian](../Machine%20Learning/Gaussian%20distribution.md) one).

The following formula gives the density of the [GMM](../Machine%20Learning/Gaussian%20Mixture%20Model.md) at a point $x$, which basically means the total height of all the gaussians summed at that point.

$$\large p(x) = \sum_{i} \pi_i \cdot \mathcal{N}(x; \mu_i;\sigma_i^2)$$
$$\large p(x) = 0.57\cdot \mathcal{N}(x; 1.80;46.81)+ 0.11 \cdot \mathcal{N}(x; 1.13;6.91)+ 0.22 \cdot \mathcal{N}(x; 1.05;3.31)+0.10 \cdot\mathcal{N}(x; 1.12;7.62)$$

---


![](../z_images/Pasted%20image%2020230702132523.png)


### Why the determinant in the denominator?

> [!note]
> The determinant $|\Sigma|$ of a matrix encodes the change in volume that results from a transformation.


In the Gaussian pdf, we have: 
- $\Sigma$ in the exponent, which changes the shape of the curve
- $|\Sigma|$ in the denominator, which makes the volume equal to 1.

![](../z_images/Pasted%20image%2020230702134431.png)


The one in the denominator is there to counter-act the change in volume that the $\Sigma$ in the exponent causes(because the volume of a pdf must amount to 1).


### Why is $\mu$ not in the denominator?

In Masi's words:

> [!quote]
> The location parameter $\mu$ is just translating the distribution in space somewhere thus does not affect the volume.

---


![](../z_images/Pasted%20image%2020230702140631.png)


### Write the equation that computes the [[Gaussian Mixture Model|responsibilities]]

$$\large\gamma_{k} =\frac{
 \mathcal{N}(x_i;\mu_k,\Sigma_k)\cdot\pi_k}
{\sum_j\mathcal{N}(x_i;\mu_j,\Sigma_j)\cdot\pi_j}$$
