A Gaussian Mixture is a function composed by several gaussians.
If we have k clusters in our dataset, we will have k gaussians.

Each gaussian k in the mixture has those 3 parameters:
- $\mu$ - the mean/center.
- $\Sigma$ - the width/slope/shape in all the dimensions.
- $\pi_k$ - a mixing probability defining how big the gaussian should be in the mixture.

![](../z_images/Pasted%20image%2020230418102907.png)

The mixing coefficients are probabilities, and so their sum is 1:
$$\large\sum^{K}_{k=1}\pi_k = 1$$

