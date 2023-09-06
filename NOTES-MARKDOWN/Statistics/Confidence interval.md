### Confidence Level 

The confidence level is the overall capture rate if the method is used many times. 
The sample mean will vary from sample to sample, but the method estimate ± margin of error is used to get an interval based on each sample. 
C% of these intervals capture the unknown population mean 𝜇. 
In other words, **the actual mean will be located within the interval C% of the time.**

The population mean for a certain variable is estimated by computing a confidence interval for that mean.

The formula for the confidence interval is:

$$\large \text{Confidence interval} = \text{sample mean} ± \text{margin of error}$$

![](../z_images/Pasted%20image%2020230514133232.png)


In order to find the confidence interval, we must find the margin of error first:

$$\large \text{Margin of error} = z^* \cdot \text{Standard Error}$$

> [!hint] Formula Explanation
> For each C% there is a specific [z-score](Z-score.md), that gives you the bounds of the interval.
> 
> The margin of error is just the un-normalized bound, because we are converting the z-score to a real value.

> [!question] Where to find values for $z^*$?
> You can find the values for $z^*$ in the c-table or z-table.


Ex. **When a General Social Survey asked 1326 subjects, "Do you believe in science?", the proportion who answered yes was 0.82.**

**Construct the 95% confidence interval.**

The sample proportion is equal to 0.82, now we just need the [standard error](Standard%20Error.md) in order to calculate the margin of error.

$$\large \text{Standard error}=\sqrt{\frac{0.82 \times 0.18}{1326}} = 0.011$$

> [!question] Why this formula?
> This is the standard error formula for the sample proportion:
> $$\large e=\sqrt{\frac{pq}{n}}$$
> 
> It's different from the one we use for the sample mean:
> $$\large e=\frac{\sigma}{\sqrt{n}}$$


$$\large \text{Margin of error} = 1.96 \cdot 0.011=0.0215$$

So the confidence interval would be

$$\large CI_{95\%} = 0.82 ± 0.0215= [0,7985, 0,8415]$$

> [!hint] How to interpret
> We are 95% confidence that between 79.8% and 84.2% of people believe in science.

> [!hint]
> If sample size increases, the margin of error decreases, and thus the CI becomes narrower.

> [!example] Effect of [standard deviation](Standard%20Deviation.md), sample size and α on the confidence interval.
>  - lower standard deviation → lower margin of error → narrower CI 
>  - higher standard deviation → higher margin of error → wider CI 
>  - lower sample size → higher margin of error → wider CI 
>  - higher sample size → lower margin of error → narrower CI 
>  - lower α → higher level of confidence 1-α →higher margin of error → wider CI 
>  - higher α → lower level of confidence 1-α → lower margin of error → narrower CI

