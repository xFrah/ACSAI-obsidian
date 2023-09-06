---
alias: GMM, GMMs, Gaussian Mixture Models
---

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


## Responsibilities in a GMM

In a Gaussian Mixture Model, $r_{ic}$ stands for the probability that the point $x_i$ belongs to cluster $c$.

$$\large\gamma_{k} =\frac{
 \mathcal{N}(x_i;\mu_k,\Sigma_k)\cdot\pi_k}
{\sum_j\mathcal{N}(x_i;\mu_j,\Sigma_j)\cdot\pi_j}$$

Where:
- The numerator stands for the height of the selected gaussian at that point
- The denominator is the height of the mixture model at that point, that would be the sum of all the gaussians.

> [!tldr]
> The gaussian that has higher responsibility for a given datapoint is the one that explains the datapoint the best.

---


## How to fit?

In supervised learning, we just get $\mu$ and $\Sigma$ of the clusters.
In unsupervised learning, we use the [Expectation Maximization](Expectation%20Maximization.md) algorithm for GMMs.

---

