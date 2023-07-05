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


> [!danger] How do we compute a determinant?
> It might be in the exam.


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

> [!danger]
> It would be best to go back and study the specifics of the [Expectation Maximization](../Machine%20Learning/Expectation%20Maximization.md) algorithm.


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

The exercise is telling us that at $x=0$, each gaussian has the same height, they just have different mixing coefficients.

$$\large\gamma_{k} =\frac{
 0.95\cdot\pi_k}
{\sum_{j}0.95\cdot\pi_j}$$

So the responsibilities are just the mixing coefficients.

---


![](../z_images/Pasted%20image%2020230702204630.png)


### Generate 10K samples from the GMM and reproject them

In this case, after [PCA](../Machine%20Learning/PCA.md) we are left with 10k images in the form of vector of 50 pixels that can have value in between [0, 255].

But Masi also gives us the mean of the original images and the U matrix used to compress them.

> [!hint]
> This is useful because we can reverse the process and get a compressed version of the original images.


If we want to generate those samples using a [GMM](../Machine%20Learning/Gaussian%20Mixture%20Model.md), **repeat the following process 10K times**:

1. By using inverse transform sampling on the cumulative mass function of the mixing coefficients, we select which digit we want to generate.

> [!hint]
> This is because the gaussians don't have all the same size, so some are more probable to be picked or more present in the GMM.
> 
> To solve this, we do a weighted random pick of the gaussian.

2. We sample from the selected gaussian.
3. We reproject the sampled image from the subspace to its original dimensions by multiplying it by $U^T$ and adding $\mu_\text{pca}$.

![](../z_images/Pasted%20image%2020230703000945.png)

---


## Exercise 3

![](../z_images/Pasted%20image%2020230703123206.png)

> [!danger]
> Go back and study [Gini impurity](../Machine%20Learning/Impurity%20functions.md) and [Missclassification](../Machine%20Learning/Impurity%20functions.md)!


![](../z_images/Pasted%20image%2020230703123230.png)


### [Entropy](../Machine%20Learning/Entropy.md) of tree

The entropy of the tree is given by the entropy of the last leaves weighed by the number of elements contained in them:

$$\large \frac{2}{11}H(D) + \frac{6}{11}H(E) + \frac{3}{11}H(C)$$

---


![](../z_images/Pasted%20image%2020230703133256.png)


### Inference on a sample

Masi gives us the sample [-1, -1000].

We know that:
1. If $x_1 <= 23$ then we go to leaf $B$.
2. Then if $x_2 <= 0$ then we go to leaf $D$.

![](../z_images/Pasted%20image%2020230703133537.png)


Since there is equal probability that the class is square and triangle, it's best to say that the algorithm is unsure here.

---


![](../z_images/Pasted%20image%2020230703133832.png)


### How to reduce overfitting in a [decision tree](../Machine%20Learning/Decision%20trees.md)

We cannot use the following strategies because:
- **Minimizing the leaf size**: Would change the depth of the tree
- **Capping the maximum depth**: Would change the depth of the tree
- **Conditional leaf generation**(A node will be split if this split induces a decrease of the impurity greater than or equal to a value): Would change the depth of the tree

So we use **Bagging and Ensamble**, which is a technique that consists in splitting the dataset and training a decision tree on each one of the splits.

Then to make inference we average the outputs of the [random forest](../Machine%20Learning/Decision%20trees.md) and we have got our model with reduced variance.

---


![](../z_images/Pasted%20image%2020230703145717.png)

### How to make random weighed prediction based on the elements in the leaves

We apply inverse transform sampling on the probabilities of the elements in the leaves????????????????????

---


## Exercise 4

![](../z_images/Pasted%20image%2020230703151648.png)

![](../z_images/Pasted%20image%2020230703151707.png)


### What are TPR and FPR?

The true positive rate, also referred to sensitivity or recall, is **used to measure the percentage of actual positives which are correctly identified**.

FPR is the opposite.

### What is the ROC curve and how do we compute it?

[ROC](../Machine%20Learning/ROC.md) curve is a performance measurement for the classification problems at various threshold settings.

It plots TPR and FPR at various threshold values.

An example of threshold would be 0.7, which is the minimum confidence the algorithm must have to output a positive.

---


## Exercise 5

![](../z_images/Pasted%20image%2020230705110526.png)

![](../z_images/Pasted%20image%2020230705110537.png)

### How many parameters?

Layer 1) We have 2048 weights for each neuron of the first layer, so:

$$\large 2048 \cdot 1024 = 20.971.52$$

**BUT THIS LAYER IS NOT TRAINABLE, SO IT DOESNT COUNT.**

Layer 2) We have 1024 weights for each neuron of the second layer, so:

$$\large 1024 \cdot 512 = 524.288$$

Layer 3) We have 512 weights for each neuron of the second layer, so:

$$\large 512 \cdot 10 = 5.120$$

When we sum them all toghether, we get the total number of pararmeters:

$$\large 524.288 + 5.120=529.408$$

---


![](../z_images/Pasted%20image%2020230705111857.png)

wtf?


---


![](../z_images/Pasted%20image%2020230705114313.png)


### Draw the DAG 

![](../z_images/Pasted%20image%2020230705130054.png)

![](../z_images/Pasted%20image%2020230705134109.png)


### Compute the [gradient](../Machine%20Learning/Gradient.md) using the [chain rule](../Calculus/Chain%20Rule.md)

At the last gate, we compute the derivatives with respect to each component of $\mathcal{L}$:

$$\large\mathcal{L}=\text{sqrt}\cdot \text{plus} \quad\rightarrow\quad \frac{\partial \mathcal{L}}{\partial \text{plus}}=\text{sqrt},\quad \frac{\partial \mathcal{L}}{\partial \text{sqrt}}=\text{plus}$$

Now, in order to apply the chain rule, we would need to know the derivatives of $\text{sqrt}$ and $\text{plus}$.

$$\large\text{sqrt}=\sqrt{x}\quad\rightarrow\quad \frac{\partial \text{sqrt}}{\partial x}=\frac{1}{2} \cdot x^{\frac{1}{2}-1}=\frac{1}{2x}$$
$$\large\text{plus}=\text{cube}+\text{sqrt}\quad\rightarrow\quad\frac{\partial \text{plus}}{\partial \text{cube}}=\text{sqrt}, \quad \frac{\partial \text{plus}}{\partial \text{sqrt}}=\text{cube}$$
The only remaining thing is $\text{cube}$.

$$\large\text{cube}=y^3\quad\rightarrow\quad\frac{\partial \text{cube}}{\partial \text{y}}=3y^2$$

Let's kill a fucking gate.

#### WIP