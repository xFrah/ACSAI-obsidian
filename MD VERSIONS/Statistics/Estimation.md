Suppose we have an unknown population parameter we'd like to estimate.

```ad-example
title: Example of population parameters
- $\large p$ - the (unknown) proportion of American college students, 18-24, who have a smart phone
- $\large \mu$ - the (unknown) mean number of days it takes Alzheimer's patients to achieve certain milestones
```

We can't possibly survey the entire population.
So we take a random sample from the population and use it to estimate the value of the population parameter.

---

## Some definitions

```ad-cite
title: Random variables of a sample
We denote the $\large n$ random variables arising from a random sample as  uppercase letters:

<br>

$$\large X_1,X_2,⋯,X_n$$

<br>

The corresponding observed values of a specific random sample are then denoted as subscripted lowercase letters:

<br>

$$\large x_1, x_2,⋯,x_n$$
```

```ad-quote
title: Parameter Space
The range of possible values of the parameter is called the parameter space $\large \Omega$.

<br>

For example, the parameter space of a population mean $\large \mu$ is defined as:

<br>

$\large \Omega=\{\mu: 0\le \mu\le 4\}$
```

---

## Point Estimator

A point estimator is a function($\large \;u(X_1, X_2, \cdots, X_n)\;$) used to find an approximate value of a population parameter from random samples of the population.

```ad-example
The point estimator for a population mean $\large \mu$ is defined as:

<br>

$$\large \bar{X}=\dfrac{1}{n}\sum\limits_{i=1}^n X_i$$

<br>

![](../z_images/Pasted%20image%2020230323144134.png)
```


### Point estimate

Instead, the **point estimate** is the value that results from the point estimator on a real set of data.

```ad-example
If $\large x_i$ are the observed grade point averages of a sample of 88 students, then:

<br>

$$\large \bar{x}=\dfrac{1}{88}\sum\limits_{i=1}^{88} x_i=3.12$$
```


### Goodness of a Point Estimator

A good estimator has two desirable properties:

- **Unbiased:** The bias of a point estimator is defined as the difference between the [[Expected value]] of the estimator and the value of the parameter being estimated(basically the [Standard Error](Standard%20Error.md)). When the estimated value of the parameter and the value of the parameter being estimated are equal, the estimator is considered unbiased.
- **Small [standard error](Standard%20Error.md):** Lower standard error compared to other estimators. It tends to fall closer than other estimates to the parameter. Or the sample mean has a smaller standard error than the sample [median](Median.md) when estimating the population mean of a [normal distribution](../Probability/Normal%20distribution.md).

```ad-example
The sample mean is an unbiased estimator of the population [mean](Mean.md).

<br>

The sample proportion is an unbiased estimator of the population proportion.
```

```ad-note
An interval estimate is more useful than a point estimate, because it incorporeates a margin of error.

<br>

This helps us to gauge the accuracy of the point estimate(that doesn't tell us how close the estimate is likely to be to the parameter).
```
