A confidence interval is the [mean](Mean.md) of your estimate + a margin of error(variation in the estimate). 
This is the range of values you expect your estimate to fall between if you redo your test, within a certain level of confidence.

The sample mean is the point estimate of the population mean.

```ad-faq
title: Population mean definition
The population mean is the mean of a variable considering the whole population.

<br>

$$\large \mu_x = \frac{sum\;of\;the\;items}{number\;of\;items}$$

<br>

The sample mean is the same but computed using only a sample of the population.

<br>

$$\large \mu_{sx} = \frac{sum\;of\;the\;items\;in\;the\;sample}{number\;of\;items\;in\;the\;sample}$$
```


The exact [standard error](Standard%20Error.md) of the sample mean is $\large \frac{\sigma}{\sqrt{n}}$.

```ad-faq
title: Standard error definition
The standard error is a statistical term that measures the accuracy with which a sample distribution represents a population by using [standard deviation](Standard%20Deviation.md). 

<br>

In statistics, a sample mean deviates from the actual mean of a population; this deviation is the standard error of the mean.
```


We don't know the population standard deviation $\large \sigma$ but we estimate it using the sample standard deviation, $\large s$.

```ad-faq
title: Sample standard deviation
It's the average of the distances of all the points from the mean.

<br>

In the case of a sample population, the sample standard deviation is the average of all the distances of all the observations in the sample from the sample mean.

<br>

$$\large s = \sqrt{\frac{1}{n-1}\sum_{i=1}^{n}(x_i - \bar{x})^2}$$
```


For large n for any population and also for every n from an underlying population that is normal, the confidence interval for the population mean is:
$$\large \mu_x +z_{\alpha/2}\frac{s}{\sqrt{n}}$$

Where:
- $\large s$ - Sample standard deviation
- $\large n$ - Number of samples
- $\large \frac{s}{\sqrt{n}}$ - Standard error
- $\large \alpha$ - Probability threshold
- $\large z_{\alpha/2}$ - Critical value of the $\large z$ distribution.


```ad-faq
title: Critical values
Critical values tell you how many standard deviations away from the mean you need to go to reach the desired confidence level for your confidence interval.

<br>

To find critical values, you need to follow those steps:
1. Choose an alpha ($\large \alpha$) value:
	The most common is 0.05
2. Decide if you need a one-tailed interval or a two-tailed interval:
	You will most likely use a two-tailed interval. For a two-tailed interval, divide your alpha by two to get the alpha value for the upper and lower tails.
3. Look up the critical value that corresponds with the alpha value:
```

