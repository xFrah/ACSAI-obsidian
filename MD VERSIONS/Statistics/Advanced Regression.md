## Simple regression equation

A regression equation describes how the mean value of a Y-variable relates to specific values of the X-variable:

$$\large E[y_i] = \beta_0 + \beta_1\cdot x_i$$
$$\text{or}$$
$$\large Y = \beta_0 + \beta_1\cdot X$$


## SSE

SSE stands for "Sum of Squared Errors", it is calculated as follows:

$$\large\text{SSE} = \sum_{i=0}^{N} (y_i - \hat{y}_i)^2$$
Where:
- $\hat{y}_i$ is the predicted value for $x_i$
- $y$ is the ground truth for $x_i$

We are basically computing a sum of the residuals, once we have our prediction:

![](../z_images/Pasted%20image%2020230516164710.png)



## How to find $\boldsymbol{b_0}$ and $\boldsymbol{b_1}$

If we want to find the two parameters, we got to minimize the SSE.

We do that by computing $b_0$ and $b_1$ as:

$$\large b_1 = \frac{\sum (x_i - \bar{x})(y_i - \bar{y})}{\sum(x_i - \bar{x})^2}$$
$$\large b_0=\bar{y} - b_1\cdot \bar{x}$$

They are called the "least squares estimates" of $\beta_0$ and $\beta_1$.

> [!warning]
> We use the notation $\beta_0$ and $\beta_1$ when we are talking about population/ground truth parameters.
> 
> We use the notation $b_0$ and $b_1$ when we are talking about fitted/predicted parameters.


## MSE

If we are trying to estimate how good our model is, we can use the "Mean Squared Error":

$$\large \text{MSE} = \frac{\text{SSE}}{n - p}$$
Where:
- $n$ is ?
- $p$ is the number of parameters, in this case 2.


> [!hint]
> The MSE is the sample variance of the errors and estimates $\sigma^2$:
> 
> $$\large E\{\text{MSE}\} = σ^2$$
> 
> Of course, then the standard deviation of errors is computed as:
> 
> $$\large s=\sqrt{\text{MSE}}$$
> 
> Which is the sample standard deviation of the errors (residuals) from the regression line. 
> It can be interpreted as the average deviation of individuals from the sample regression line.


## SST

It is the total sum of squares:

$$\large\text{SST} = \sum_{i=0}^{N} (y_i - \bar{y})^2$$

It is basically the sum of all the squared deviations from the mean.

![](../z_images/Pasted%20image%2020230516173728.png)


## $\boldsymbol{R^2}$ 

$\sqrt{R^2}=r\leftarrow$ correlation coefficient.

$$\large R^2=\frac{\text{SST} - \text{SSE}}{\text{SST}}$$

![](../z_images/Pasted%20image%2020230516174107.png)

> [!hint]
> It is interpreted as the fraction of variation in y that is explained by the fitted regression equation. It is often converted to a percentage.


