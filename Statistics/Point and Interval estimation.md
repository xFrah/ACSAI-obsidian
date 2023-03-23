A point estimate is a singlen umber that is our best guess for the parameter.

An interval estimate is an interval of numbers within which the parameter value is believed to be.


```ad-note
An interval estimate is more useful than a point estimate, because it incorporeates a margin of error.

<br>

This helps us to gauge the accuracy of the point estimate(that doesn't tell us how close the estimate is likely to be to the parameter).
```

```ad-example
A General Social Survey asked to a sample of 1900 persons: “do you believe in hell?”. 1387 responded yes. 

<br>

The point estimate for the proportion of adult Americans who would respond yes equals 1387/1900 = 0.73 (point estimate). 

<br>

The interval estimate is [0.71,0.75], it predicts a margin of error of 0.02.
```


## Point estimators

Point estimators are functions that are used to find an approximate value of a population parameter from random samples of the population.

They use the sample of a population to calculate a point estimate or a statistic that serves as the best estimate of an unknown [parameter](https://corporatefinanceinstitute.com/resources/knowledge/other/parameter/) of a population.

![](../z_images/Pasted%20image%2020230323144134.png)

```ad-example
When finding the average age of kids attending kindergarten, it will be impossible to collect the exact age of every kindergarten kid in the world. 

<br>

Instead, a statistician can use the point estimator to make an estimate of the population parameter.
```


A good estimator has two desirable properties:

- **Unbiased:** The bias of a point estimator is defined as the difference between the [[expected value]] of the estimator and the value of the parameter being estimated. When the estimated value of the parameter and the value of the parameter being estimated are equal, the estimator is considered unbiased.

Also, the closer the expected value of a parameter is to the value of the parameter being measured, the lesser the bias is.

```ad-example
The sample mean is an unbiased estimator of the population [mean](Mean.md).

<br>

The sample proportion is an unbiased estimator of the population proportion.
```

- **Small [standard error](Standard%20Error.md):** Lower standard error compared to other estimators. It tends to fall closer than other estimates to the parameter. Or the sample mean has a smaller standard error than the sample [median](Median.md) when estimating the population mean of a normal distribution.


## Confidence Intervals

A confidence interval is an interval containing themost beliavable values for a parameter.

Confidence level: the probability that this method produces an interval that contains the parameter.

#### How to construct them:

1. We start with the [[Sampling distributions|sampling distribution]] of a sample proportion