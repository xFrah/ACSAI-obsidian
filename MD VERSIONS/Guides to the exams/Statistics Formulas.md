## General formulas

##### Sample [standard deviation](../Statistics/Standard%20Deviation.md)
$$\large\sigma_s=\sqrt{\frac{\sum(x_i - \bar{x})^2}{N-1}}$$
## Simpel [regression](../Statistics/Regression.md)

##### [Covariance](../Statistics/Covariance.md):
$$\large \text{cov}(x,y)=\sum (x-\bar{x})(y-\bar{y})$$
##### [Correlation coefficient](../Statistics/Correlation%20coefficient.md)
$$\large r = \frac{\text{cov}(x,y)}{\sqrt{\sum (x - \bar{x})^2\sum (y - \bar{y})^2}}$$
##### Angular coefficient
$$\large m=r(\frac{\sigma_y}{\sigma_x})$$
##### Intercept
$$\large q = \bar{y}-m\bar{x}$$

## [Normal distribution](../Statistics/Normal%20distribution.md)

##### [z-score](../Statistics/Z-score.md)
$$\large z = \frac{x - \mu}{\sigma}$$

##### Test statistic(s-score with $\sigma=\text{SE}$)
$$\large z = \frac{x - \mu}{\text{SE}}$$

## Bernoulli distribution

##### Probability at x
$$\large P(x)=\frac{n!}{(n-x)!x!}p^xq^{n-x}$$

##### [Mean](../Statistics/Mean.md)
$$\large \mu=np$$
##### [Variance](../Statistics/Variance.md)
$$\large \text{var}(X) = np(p-1)$$

## [Sampling distributions](../Statistics/Sampling%20distributions.md)

##### [Standard deviation](../Statistics/Standard%20Deviation.md) of sample proportion
$$\large\sigma_{\hat{P}}=\sqrt{\frac{pq}{n}}$$
##### [Standard error](../Statistics/Standard%20Error.md) of sample proportion
$$\large e=\sqrt{\frac{pq}{n}}$$
##### [Standard deviation](../Statistics/Standard%20Deviation.md) of sample [mean](../Statistics/Mean.md)
$$\large \sigma_s = \frac{\sigma}{\sqrt{n}}$$
##### [Standard error](../Statistics/Standard%20Error.md) of sample [mean](../Statistics/Mean.md)
$$\large e=\frac{\sigma}{\sqrt{n}}$$

## Confidence intervals

##### [Confidence interval](../Statistics/Confidence%20interval.md)
$$\large \text{Confidence interval} = \text{sample mean} ± \text{margin of error}$$
##### Margin of error
$$\large \text{Margin of error} = z^* \cdot \text{Standard Error}$$

## [Significance level](../Statistics/Significance%20Level.md)

##### Multiplier: Just the z-score of the bound of the [significance level](../Statistics/Significance%20Level.md)


## Lil more aggressive [Regression](../Statistics/Regression.md)

##### SSE
$$\large\text{SSE} = \sum_{i=0}^{N} (y_i - \hat{y}_i)^2$$
##### SST
$$\large\text{SST} = \sum_{i=0}^{N} (y_i - \bar{y})^2$$
##### $R^2$
$$\large R^2=\frac{\text{SST} - \text{SSE}}{\text{SST}}$$