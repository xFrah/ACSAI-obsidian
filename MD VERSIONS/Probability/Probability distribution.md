A probability distribution is a function that <font color="#b2a2c7">describes the likelihood or probability of different possible outcomes</font> in a random event or experiment. 
<font color="#b2a2c7">It maps each possible outcome to its probability</font>, such that the sum of the probabilities of all possible outcomes is equal to 1.

```ad-example
title: Toss 2 coins:
| Toss 2 coins | Probability |
| --- | --- |
| 0 heads | 0.25 |
| 1 head | 0.5 |
| 2 heads | 0.25 |

<br>

![](../z_images/Pasted%20image%2020230315150630.png)
```

We can compute [variance](../Statistics/Variance.md) and [standard deviation](../Statistics/Standard%20Deviation.md) of a probability distribution, which should give us an idea of how it really is.

## Discrete and continuous random variables:

![](../z_images/Pasted%20image%2020230315151024.png)

## Distributions for discrete random variables:

#### [Mean](../Statistics/Mean.md) of a probability distribution

Can be computed by:
$$\large\mu=\sum x·p(x)$$
It is basically a weighted average, because values of x that are more likely receive greater weight p(x).

It is also called the expected value of X.


## Distributions for continuous random variables

A continuous [random variable](Random%20variable.md) has infinite possible values in an interval(ex. age, height, weight, income).

It's probability distribution is specified by a density curve and the probability of an interval is given by the area under the curve over the interval(we take the integral).

![](../z_images/Pasted%20image%2020230315151714.png)

#### Expected value and variance

![](../z_images/Pasted%20image%2020230315152117.png)

#### Types of continuous distributions

![](../z_images/Pasted%20image%2020230315151735.png)


#### Probabilities for bell-shaped distributions(symmetrical)

- The [mean](../Statistics/Mean.md), [median](../Statistics/Median.md) and [mode](../Statistics/Mode.md) are equal.
- Location is determined by the mean $\large \mu$.
- [Spread](../Statistics/Spread.md) is determined by the standard deviation $\large \sigma$.
- The random variable has an infinite theoretical range, from $-\infty$ to $+\infty$.
- The distribution is completely specified by the two parameters mean and variance.
	- ![](../z_images/Pasted%20image%2020230315152851.png)
