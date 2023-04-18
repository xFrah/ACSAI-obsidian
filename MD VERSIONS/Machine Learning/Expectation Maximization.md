We want to estimate the parameters of each gaussian in a [Gaussian Mixture Model](Gaussian%20Mixture%20Model.md).

![](../z_images/Pasted%20image%2020230418142138.png)

This is pretty easy if we already know which point belongs to which [[Gaussian distribution|gaussian]]:

![](../z_images/Pasted%20image%2020230418142204.png)

We can just compute the [mean](../Statistics/Mean.md) and [[Standard Deviation|standard deviations]] from the points, resulting in this GMM:

![](../z_images/Pasted%20image%2020230418142233.png)

But what if we don't actually know the clusters in advance?

---

## The algorithm

It's a lot like [K-means](K-means.md), because we are trying to solve a similar optimization problem:

![](../z_images/Pasted%20image%2020230418143320.png)


0) We set random parameters for the gaussians:
>![](../z_images/Pasted%20image%2020230418144751.png)

1) We assign the labels according to the [Mahalanobis Distance](Mahalanobis%20distance.md) of points from distributions.
> ![](../z_images/Pasted%20image%2020230418144930.png)

2) Update parameters:
> ![](../z_images/Pasted%20image%2020230418145110.png)

4) Repeat step 1 and step 2 until convergence:
>![](../z_images/Pasted%20image%2020230418145204.png)
>![](../z_images/Pasted%20image%2020230418145242.png)
>At step 4 we have already converged.

