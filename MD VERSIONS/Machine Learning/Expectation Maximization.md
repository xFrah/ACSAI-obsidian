We want to estimate the parameters of each gaussian in a [Gaussian Mixture Model](Gaussian%20Mixture%20Model.md).
Imagine we have a 1D dataset:

![](../z_images/Pasted%20image%2020230418142138.png)


This is pretty easy if we already know which point belongs to which [[Gaussian distribution|gaussian]]:

![](../z_images/Pasted%20image%2020230418142204.png)


We can just compute the mean and [[Standard Deviation|standard deviations]] from the points, resulting in this GMM:

![](../z_images/Pasted%20image%2020230418142233.png)


But what if we don't actually know the clusters in advance?

---

## The algorithm

It's a lot like [K-means](K-means.md), because we are trying to solve a similar optimization problem:

![](../z_images/Pasted%20image%2020230418143320.png)


### 0) Initialization: We set random parameters for the gaussians:

![](../z_images/Pasted%20image%2020230418144751.png)


### 1) E-step: Assign the labels

This is done by computing the responsibilities for each point. We assign the label with highest [[Gaussian Mixture Model|responsibility]].

![](../z_images/Pasted%20image%2020230418144930.png)


### 2) M-step: Update parameters:

This step consists in updating the parameters of the gaussians: mean $\mu_c$, [covariance](../Statistics/Covariance.md) $\Sigma_c$ and size $\pi_c$.

$\large\begin{aligned} &\mu_{k}=\frac{1}{N_{k}} \sum_{n=1}^{N} \gamma_{k}^{(n)}\mathbf{x}^{(n)} \\&\Sigma_{k}=\frac{1}{N_{k}} \sum_{n=1}^{N} \gamma_{k}^{(n)}\left(\mathbf{x}^{(n)}\mu_{k}\right)\left(\mathbf{x}^{(n)}-\mu_{k}\right)^{T} \\&\pi_{k}=\frac{N_{k}}{N} \text { with } N_{k}=\sum_{n=1}^{N} \gamma_{k}^{(n)}\end{aligned}$

TODO: make it similar to this:
![](../z_images/Pasted%20image%2020230420171130.png)

![](../z_images/Pasted%20image%2020230418145110.png)


### ?) Repeat step 1 and step 2 until convergence:

![](../z_images/Pasted%20image%2020230418145204.png)
![](../z_images/Pasted%20image%2020230418145242.png)

At step 4 we have already converged.


## lol?

Each step increases the log-likelihood of our model until convergence.

![](../z_images/Pasted%20image%2020230420172459.png)



```ad-seealso
title: Sources
### Clustering (4): Gaussian Mixture Models and EM
https://www.youtube.com/watch?v=qMTuMa86NzU
```
