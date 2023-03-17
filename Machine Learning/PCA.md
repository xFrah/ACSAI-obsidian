chapter 12 of bishop book.

Given an input of D dimensions, our objective is to find a subspace that maximizes the [variance](../Statistics/Variance.md) of the data, as we need compress the data but as make it as lossless as we can.


```ad-tldr
title: Motivation
- Compress the dimensions, but keep most of information.
- Preserve tha variance of the data as much as possible.
```


## How to choose dimensionality of subspace?

We measure the variation in the data, when it goes below 95% of what it was before, we stop.
So we keep the minimum number of dimensions that retains > 95% of the variation.

We delete the eigenvalues with less energy?????????
Variance is the sum of all [[Eigenvectors and Eigenvalues|eigenvalues]]?????

```ad-example
Starting from a 2D point cloud, we can reduce the dimensions by 1 if the energy remains > 95%.
Before:
> ![](../z_images/Pasted%20image%2020230309162713.png)

After:
> ![](../z_images/Pasted%20image%2020230309162805.png)

After reconstruction:
> ![](../z_images/Pasted%20image%2020230309162850.png)

All that variance has been lost.
```


## How to:

Suppose we have a point cloud X:

![](../z_images/Pasted%20image%2020230309160942.png)

## 1. Standardize the data
First step, we standardize the data :
$$\large X' = \frac{X-\mu}{\sigma}$$

We just shifted the [mean](../Statistics/Mean.md) to 0 and rescaled all axis, so that the [standard deviation](../Statistics/Standard%20Deviation.md) is 1.


```python
center = X.mean(axis=0) #X shape is 100x2 
std = X.std(axis=0) 
Xp = (X-center)/std

```
Output:
![](../z_images/Pasted%20image%2020230309160917.png)

## 2. Find the [covariance](../Statistics/Covariance.md) matrix

The eigenvalues of hte 
```python
C = np.cov(X, rowvar=False) 
Sigma, U = np.linalg.eig(C) 
```

```python
print(C.shape)
> (2, 2)

print(Sigma.shape, U.shape, Sigma)
> ((2,), (2, 2), array([0.47772418, 6.90110921]))
```

```python
total_energy = Sigma.sum() 
var_exp = [(i / total_energy) for i in Sigma] 
cum_var_exp = np.cumsum(var_exp)
```


Praticamente stiamo cercando di trovare lo unit vector che massimizza la somma di tutti i dot product tra un ipotetico variabile unit vector(che stiamo cercando) e tutti i vettori nel dataset.


Re-explanation of the professor:

You center the point cloud to the origin.
covariance matrix = $\large X^T X \frac{1}{2}$ we can compute it like this because the data is centered.

now we do the [spectral decomposition](../Linear%20Algebra/Spectral%20decomposition.md) of the [covariance matrix](Covariance%20matrix.md).
we solve it
its going to give us a vector lambda.
U = each column vector is a direction. They are perpendicular. Those are the components that we need.

$\large \frac{1}{N}X^T X=U \Sigma U^T$

we select the eigenvector with the smallest eigenvalue and we remove that dimension.

Data decorrelation:
you take x and you project it with U^T.
By doing this we are decorrelating the data.

WTFFFFFFFFFFFF

## SEE THIS:
http://ufldl.stanford.edu/tutorial/unsupervised/PCAWhitening/


https://stats.stackexchange.com/questions/194278/meaning-of-reconstruction-error-in-pca-and-lda 



## Large dimensionality problem, [[Spectral decomposition|SD]] vs [[SVD]]

The covariance matrix has DxD entries, so it can be very large if the input has very high dimensionality.

So we do directly SVD instead of spectral decomposition so that we can avoid to compute XX^T.

We do SVD of X itself.

**Spectral:**

$\large \frac{1}{N} XX^T = U\Sigma U^T$

**SVD:**

$\large X = U S V^T$

$\large \frac{1}{N}(USV^T)(USV^T)^T$

$\large \frac{1}{N}^T USV^T\,VS^TU^T = \frac{1}{N}US^2U^T$

in this case we don't pass through the covariance matrix.


#### Another take

Since the dataset is transposable, which means that we can either do the decomposition of X or X^T and the significance remains the same.

Which means that we can compute the svd that takes less computational time.
The whole point of using SVD here is that we can avoid calculating U or U by doing the inverse formula, having the other variables.

So for example, if V($X^TX$) is the bigger one, we calculate U and $\Sigma$ by calculating the covariance matrix($XX^T$), or viceversa?

## PCA on images


