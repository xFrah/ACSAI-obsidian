The long-run average value of random variables.

![](../z_images/Pasted%20image%2020230506172400.png)


Each one of those bars represent the probability for $P(X=x)$ to happen.

| x   | 1   | 2   | 3   | 4   |
| --- | --- | --- | --- | --- |
| P(X=x) | 0.2 | 0.3 | 0.3 | 0.2 |


In order to get the expected value, we must multiply each outcome with their respective probability. The result will be a weighted average, so the most probable outcome.

In this case: $E(x) = (1*0.2) + (2*0.3) + (3*0.3) + (4*0.2) = 2.5$

The actual formula would be:
$$\large E(X) = \sum_{i=1}^n x_i P(X=x_i) = \mu_X$$


```ad-hint
title: Further intuition
If you think about it, this is really the equivalent of a mean.
In the mean, all items have the same weight, so you just divide by the number of items.

<br>

Meanwhile, the expected value weighs every single item.

<br>

The thing is:

<br>

$$\large \underbracket{\frac{1+1+1+2+2+3}{6}}_{\text{Mean}}=\underbracket{\frac{3}{6}(1)+\frac{2}{6}(2)+\frac{1}{6}(3)}_{\text{Expectation}}$$

<br>

They are the same thing, it's just a different way to weigh the items.

The mean weighs by putting in more items of the same kind, the expected value actually weighs every single value.
```
