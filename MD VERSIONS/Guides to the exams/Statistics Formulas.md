## General formulas

##### Sample standard deviation
$$\large\sigma_s=\sqrt{\frac{\sum(x_i - \bar{x})^2}{N-1}}$$
## Simpel regression

##### Covariance:
$$\large \text{cov}(x,y)=\sum (x-\bar{x})(y-\bar{y})$$
##### Correlation coefficient
$$\large r = \frac{\text{cov}(x,y)}{\sqrt{\sum (x - \bar{x})^2\sum (y - \bar{y})^2}}$$
##### Angular coefficient
$$\large m=r(\frac{\sigma_y}{\sigma_x})$$
##### Intercept
$$\large q = \bar{y}-m\bar{x}$$

## Normal distribution

##### z-score
$$\large z = \frac{x - \mu}{\sigma}$$

##### Test statistic(s-score with $\sigma=\text{SE}$)
$$\large z = \frac{x - \mu}{\text{SE}}$$

## Binomial distribution

##### Probability at x
$$\large P(x)=\frac{n!}{(n-x)!x!}p^xq^{n-x}$$

##### Mean
$$\large \mu=np$$
##### Variance
$$\large \text{var}(X) = np(p-1)$$

## Sampling distributions

##### Standard deviation of sample proportion
$$\large\sigma_{\hat{P}}=\sqrt{\frac{pq}{n}}$$
##### Standard error of sample proportion
$$\large e=\sqrt{\frac{pq}{n}}$$
##### Standard deviation of sample mean
$$\large \sigma_s = \frac{\sigma}{\sqrt{n}}$$
##### Standard error of sample mean
$$\large e=\frac{\sigma}{\sqrt{n}}$$

## Confidence intervals

##### Confidence interval
$$\large \text{Confidence interval} = \text{sample mean} ± \text{margin of error}$$
##### Margin of error
$$\large \text{Margin of error} = z^* \cdot \text{Standard Error}$$

## Significance level

##### Multiplier: Just the z-score of the bound of the significance level


## Lil more aggressive Regression

##### SSE
$$\large\text{SSE} = \sum_{i=0}^{N} (y_i - \hat{y}_i)^2$$
##### SST
$$\large\text{SST} = \sum_{i=0}^{N} (y_i - \bar{y})^2$$
##### $R^2$
$$\large R^2=\frac{\text{SST} - \text{SSE}}{\text{SST}}$$