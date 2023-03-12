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

First step, we standardize the data :
$$\large X' = \frac{X-\mu}{\sigma}$$

We just shifted the [mean](../Statistics/Mean.md) to 0 and rescaled all axis, so that the [standard deviation](../Statistics/Standard%20Deviation.md) is 1.


```
# standardize 
center = X.mean(axis=0) #X shape is 100x2 
std = X.std(axis=0) 
Xp = (X-center)/std

```
Output:
![](../z_images/Pasted%20image%2020230309160917.png)

Then we ???


```
C = np.cov(X, rowvar=False) 
Sigma, U = np.linalg.eig(C) 
# If rowvar is True (default), then each row represents a variable, 
# with observations in the columns. Otherwise, the relationship 
# is transposed: each column represents a variable, while the # rows contain observations.
```

```
print(C.shape)
> (2, 2)

print(Sigma.shape, U.shape, Sigma)
> ((2,), (2, 2), array([0.47772418, 6.90110921]))
```

```
total_energy = Sigma.sum() 
var_exp = [(i / total_energy) for i in Sigma] 
cum_var_exp = np.cumsum(var_exp)
```

![](../z_images/Pasted%20image%2020230309161558.png)


Praticamente stiamo cercando di trovare lo unit vector che massimizza la somma di tutti i dot product tra un ipotetico variabile unit vector(che stiamo cercando) e tutti i vettori nel dataset.

