Measures <span style="background:rgba(183, 152, 255, 0.3)">how much dispersed the data is in relation to the mean</span>.

$$ \Huge\sigma = \sqrt{\frac{\sum(x_i - \mu_x)^2}{N}}$$

Where:
- **Xi** – a point X.
- **μX** – the mean of X.

---

## Computing Standard Deviation

Standard deviation is calculated as follows:

1.  Calculate the [[Mean]] of all data points.
2.  Calculate the [[Variance]] for each data point.
3.  Square the variance of each data point <font color="#7f7f7f">(from Step 2)</font>.
4.  Sum of squared variance values <font color="#7f7f7f">(from Step 3)</font>.
5.  Divide the sum of squared variance values <font color="#7f7f7f">(from Step 4)</font> by the number of data points in the data set less 1.
6.  Take the square root of the quotient <font color="#7f7f7f">(from Step 5)</font>.


```ad-hint
title: Formula explanation

We are taking the <span style="background:rgba(183, 152, 255, 0.3)">average of the distances from the mean for each point</span>.
But, we square the distances so that they are always positive, then we sqrt everything to get the correct unit of measurament.
```


![](../z_images/Pasted%20image%2020230301152051.png)

---

## Sample standard deviation

When the data is a sample, we adjust the [variance](Variance.md) to:
$$\Large \sigma^2 = \frac{1}{N - 1} \sum_{i=1}^{n}(x_i-\mu)^2 $$
and the standard deviation to:
$$ \Large\sigma = \sqrt{\frac{\sum(x_i - \mu_x)^2}{N - 1}}$$

#### Properties of standard deviation:
- σ[s] measures the spread (variability) of the data. 
- σ[s] = 0 only when all observations have the same value. 
- σ[s] has the same units of measurement as the original observations. The variance has units that are squared. 
- σ[s]is not resistant. A few extreme values can greatly increase its value. 