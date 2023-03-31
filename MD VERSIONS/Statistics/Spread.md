The spread or variability of Quantitive Data is how much the values are different across the observations.

But how do we measure the variability?

## Range

One way to measure the spread is to calculate the range.
The range is the difference between the largest and smallest values in the data set.

## [Standard deviation](Standard%20Deviation.md)

- Each data value has an associated deviation from the [mean](Mean.md) x - ux.
- A deviation is considered positive if it falls above the mean and negative if it falls below the mean.
- The sum of deviations is always zero, the mean is the center.
- A measure of variation can be obtained by summarizing the squared devitions of eah obsercations from the mean and calculating an average of these squared deviations.

$$ \Large\sigma = \sqrt{\frac{\sum(x_i - \mu_x)^2}{N}}$$

![](../z_images/Pasted%20image%2020230301152051.png)


```ad-hint
The square root is for when we need to come back to the original unit of measurament of our data, because we squared the deviations.
```


When the data is a sample, we adjust the [variance](Variance.md) to:
$$\Large \sigma^2 = \frac{1}{N - 1} \sum_{i=1}^{n}(x_i-\mu)^2 $$
and the standard deviation to:
$$ \Large\sigma = \sqrt{\frac{\sum(x_i - \mu_x)^2}{N - 1}}$$
because?

#### Properties of standard deviation:
- σ[s] measures the spread (variability) of the data. 
- σ[s] = 0 only when all observations have the same value. 
- σ[s] has the same units of measurement as the original observations. The variance has units that are squared. 
- σ[s]is not resistant. A few extreme values can greatly increase its value. 