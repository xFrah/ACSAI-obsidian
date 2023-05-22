A Gaussian Mixture is a function composed by several [[Gaussian distribution|gaussian distributions]].
If we have k clusters in our dataset, we will have k gaussians.

Each gaussian k in the mixture has those 3 parameters:
- $\mu$ - the mean/center.
- $\Sigma$ - the width/slope/shape/[covariance](../Statistics/Covariance.md) in all the dimensions.
- $\pi_k$ - a mixing probability defining how big the gaussian should be in the mixture.

![](../z_images/Pasted%20image%2020230418102907.png)

The mixing coefficients are probabilities, and so their sum is 1:
$$\large\sum^{K}_{k=1}\pi_k = 1$$

---

## How to fit?

In supervised learning, we just get $\mu$ and $\Sigma$ of the clusters.
In unsupervised learning, we use the [Expectation Maximization](Expectation%20Maximization.md) algorithm for GMMs.

---

