The probabilities of observing a certain outcome when performing a series of tests with only 2 possible outcomes("success" or "failure").

p = Each trial must have the same probability of success, denoted by p.
n = Number of trials. The n trials must be indipendent.
X = The binomial [random variable](Random%20variable.md) X is the number of successes in n trials.


```ad-example
Getting heads or tails in a coin toss.

<br>

![](../z_images/Pasted%20image%2020230316143116.png)

<br>

Here the probability of getting heads is 0.5, and this is the binomial distribution of that [random variable](Random%20variable.md).
```


For n independent trials, the probability of x successes equals:
$$\large P(x)=\frac{n!}{x!(n-x)!}\pi^x(1-\pi)^{n-x}$$


```ad-example
The shape of the distribution depends on n and p:

<br>

![](../z_images/Pasted%20image%2020230316145151.png)
```


## [Mean](../Statistics/Mean.md) and [standard deviation](../Statistics/Standard%20Deviation.md)

The formulas are:
$$\large \mu = \sum(x) = np$$
and
$$\large \sigma^2=var(X)=np(1-p)$$

## Approximation with [normal distribution](../Statistics/Normal%20distribution.md)

The binomial distribution can be well approximated by the normal distribution when the expected number of success($np$) and the expected number of failures($n(1-p)$) are both at least 15.


```ad-example
- 262 police car stops in Philadelphia in 1997
- 207 of the drivers stopped were African-American
- In 1997, Philadelphia's population was 42.2% African-American.

<br>

The number of African-americans stopped suggests possible bias, being higher than we would expect.

<br>

What would be a biasless number?

$\large \mu = n * p = 262 * 0.422 = 111$

<br>

This should be the approximate number of African-American drivers that should have been stopped.

<br>

If we include the standard deviation($3\sigma$ due to [empirical rule](Empirical%20rule.md)), we get a range:

$\large\sigma=\sqrt{262(0.422)(0.578)}=8$

<br>

$\large\mu - 3\sigma=87$

$\large\mu+3\sigma=135$

<br>

So if there wasn't any racial profiling, the number of stopped African-Americans should be between [87, 135].

```
