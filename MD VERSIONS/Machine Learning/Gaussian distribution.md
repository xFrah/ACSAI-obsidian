The [normal distribution](../Probability/Normal%20distribution.md), also known as Gaussian distribution, is defined by two parameters:
- [mean](../Statistics/Mean.md) $\large \mu$, which is [expected value](../Statistics/Expected%20value.md) of the distribution 
- [standard deviation](../Statistics/Standard%20Deviation.md) $\large \sigma$, which corresponds to the expected squared deviation from the mean.

For every value x, the density equals to:
$$\large P(x \mid \mu, \sigma^{2}) = \frac{1}{\sqrt{2\pi \sigma^{2}}}^{\huge- \frac{(x - \mu)^{2}}{2\sigma^{2}}}$$
Where:
- $\large \mu$ is the mean and it controls the Gaussian’s center position
- $\large \sigma$ is the standard deviation and it controls the shape of the distribution.
- $\large k$ is the dimensions

![](../z_images/Pasted%20image%2020230402120530.png)


```ad-tldr
Each colum $\large x_i$ under the curve tells how many times the random variable $X$ takes value $\large x_i$.

<br>

example,

<br>

At value 5, the probability distribution tells you the probability that X takes the value 5.
```

```ad-hint
We call this distribution univariate because it consists of one [random variable](../Probability/Random%20variable.md).
```

---

## Multivariate Gaussian distribution

The multivariate normal distribution is a multidimensional generalisation of the one dimensional normal distribution. It represents the distribution of a multivariate random variable, that is made up of multiple random variables which can be correlated with each other.

$$\large f(x) = \frac{1}{\sqrt{(2\pi)^k \det\Sigma}}^{\huge-\frac{1}{2}(x - \mu)^T \Sigma^{-1}(x-\mu)}$$

Basically we have a [quadratic form](../Linear%20Algebra/Quadratic%20form.md) in the exponent
Where:
- $\large \mu$ is the [mean](../Statistics/Mean.md)
- $\large \Sigma$ is the [covariance matrix](Covariance%20matrix.md).
- $\large k$ is the dimensions

The determinant tells you how much the space is deformed. by dividing by it we are normalizing the data.

```ad-example
With values:
$$\large \mu = \begin{bmatrix}
0 \\ 1
\end{bmatrix},\quad \Sigma = \begin{bmatrix}
1 & -0.75 \\
-0.75 & 2
\end{bmatrix}$$

<br>

Recall that $\Sigma$ is a covariance matrix.

The values in the diagonal tell us the variances along the two axes and the values off the diagonal tell us the covariances between the axes.

<br>

So in this case, 1 and 2 are how much the data is spread out, and -0.75 is the covariance between the two variables, meaning that some correlation is present and the two variables might tell us something about each other.

<br>

![](../../Pasted%20image%2020230404110326.png)
```

```ad-example
title: Uncorrelated Multivariate Gaussian
With values:

$$\large \mu = \begin{bmatrix}
0 \\ 0
\end{bmatrix},\quad \Sigma = \begin{bmatrix}
1 & 0 \\
0 & 3
\end{bmatrix}$$

<br>

Here no correlation is present because the values off the diagonal are 0(recall that the values off the diagonal in a covariance matrix are the covariances between two variables).

<br>

So the variables are not telling us anything about each other as they are totally uncorrelated.

<br>

![](../../Pasted%20image%2020230404111256.png)

```


The determinant is there because if we integrate this its going to 1. If we stretch sigma we should normalize it.

The distribution above can be seen as [joint distribution](Joint%20distribution.md) $p(X, Y)$ of two random variables $X$ and $Y$.