It measures how many standard deviations away x is from the [mean](../Statistics/Mean.md) of $\mathcal{N}(\mu,\Sigma)$
Alternatively, it measures how far away a vector is from a distribution.

The thing is, if we have a point cloud / distribution like this:

![](../z_images/Pasted%20image%2020230405214722.png)

How can you even tell how many standard deviations away a point is from the mean?
Standard deviations of what lol.

TO BE CONTINUED

```ad-hint
title: Why don't we use the Euclidean distance?
Recall that the euclidean distance is simply a straight line between two points.

<br>

Euclidean distance will work fine as long as the dimensions are equally weighted and are indipendent of each other.
```


The Mahalanobis distance is unitless, scale-invariant and takes into account the correlations of the data set.
If each of the axes are rescaled to have [variance](../Statistics/Variance.md) 1, the Mahalanobis distance corresponds to the standard Euclidean distance.

The formula is:
$$\large D_M(\vec{x}) = \sqrt{(x - \mu)^\mathsf{T} \mathbf{\Sigma}^{-1} (x - \mu)}$$

We are weighting each dimension proportionally to the [standard deviation](../Statistics/Standard%20Deviation.md).