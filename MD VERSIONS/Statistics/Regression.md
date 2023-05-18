First, we need to identify [[Association|response and explanatory variables]], we call them y and x respectively.

A regression line is a line that describes how the y changes as x changes.
It is useful for making predictions on y at every given x value.

$$\Large \hat{y} = a + bx$$

Where:
- $\large a$ is the y-intercept of the line.
- $\large b$ is the slope of the line.


![](../z_images/Pasted%20image%2020230308151724.png)

---

## Error

Actually, the formula above gives just a value for each x, and that is not really realistic, becuse the relationship between x and y is non-deterministic. 
Not all subjects will have the same y at the same x.

So we add an error coefficient in the formula:
$$\Large \hat{y} = a + bx + e$$

Where $\large e$ represents:
- The variability of y given x
- Omitted variables
- Errors in the equation, because it may not be perfectly linear

---

## Residual

It measures the size of the prediction error, the vertical distance between the real point and the regression line.

This is the residual sum of squares:

$$\Large \sum{(y_i - \hat{y}_i)^2}$$
Where:
- $\large y_i$ is the real point in the data.
- $\large \hat{y}_i$ is the value of y predicted by the regression line.


```ad-note
title: Why squared?
Because it's either that or the absolute value. And in this case we don't care about the unit of measurament, we just care about minimizing the value.
```

---

## Calculating the least-squares regression line

The least squares regression is the line that minimizes the vertical distance between the actual points and their predictions, so <span style="background:rgba(183, 152, 255, 0.3)">the one that minimizes the residual sum of squares</span>.

The slope is given by:
$$\large r \frac{std(y)}{std(x)} = \frac{cov(x, y)\,\bcancel{std(y)}}{std(x)\;std(x)\bcancel{std(y)}} = \frac{cov(x, y)}{std(x)^2} = \frac{\sum(x_i - \mu_x)(y_i - \mu_y)}{\sum(x_i - \mu_x)^2}$$


Where:
- $\large r$ is the [correlation coefficient](Correlation%20coefficient.md)
$$\large r_{x,y} = \frac{ cov(x,y) }{ std(x) \, std(y) }$$
- $\large std$ is the [standard deviation](Standard%20Deviation.md):
$$ \large std = \sqrt{\sum(x_i - \mu_x)^2}$$
- $\large cov$ is the [covariance](Covariance.md):
$$\large cov=\sum(X - \mu_X)(Y - \mu_Y)$$
- $\large \mu_x$ is the [mean](Mean.md) of x
- $\large \mu_y$ is the mean of y
