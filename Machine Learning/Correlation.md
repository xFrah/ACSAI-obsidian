Correlation is a statistical measure that indicates <span style="background:rgba(183, 152, 255, 0.3)">how much two variables are related</span>(if they change together at a costant rate).
Specifically, it indicates the strength of their relationship.

![](../z_images/Pasted%20image%2020230223213817.png)


The stronger the relationship is, the closer to ±1 it gets.

## Pearson Correlation Coefficient

$$\Huge\rho_{X,Y} = \frac{ cov(X,Y) }{ \sigma_X \sigma_Y }$$

Where:
- **cov** – the covariance of the two series
- **σx** – the [[../Statistics/Standard Deviation]] of X
- **σy** – is the standard deviation of Y

Charateristics:
- The range of the result is [-1, +1].
- A value of exactly <span style="background:rgba(183, 152, 255, 0.3)">±1 indicates that all data points lie on a line</span>, a linear equation can describe the relationship between X and Y perfectly.
- <span style="background:rgba(183, 152, 255, 0.3)">The sign is determined by the slope</span>: a value of +1 implies that all data points lie on a line for which Y increases as X increases, and vice versa for −1. 
- <span style="background:rgba(183, 152, 255, 0.3)">0 means that there is no linear dependency</span> between variables

![](../z_images/Pasted%20image%2020230223220310.png)


## Covariance of two series

The covariance is a way of calculating the relationship between two variables and it will tell us <span style="background:rgba(183, 152, 255, 0.3)">how much two random variables vary together</span>.

The formula is:

$$\LARGE\operatorname{cov}(X,Y) = \sum(X - \mu_X)(Y - \mu_Y)$$

Where:
-   **Xi** – the values of the X-variable
-   **Yj** – the values of the Y-variable
-   **μX** – the [[../Statistics/Mean]] (average) of the X-variable
-   **μY** – the mean (average) of the Y-variable
-   **n** – the number of data points

Why?
We are basically trying to get the direction of the values in respect to the mean of X and Y, that act as new axes.

![](../z_images/Pasted%20image%2020230225203834.png)

Basically, we are summing all the areas of the squares that are formed with the new axes.
The areas are the product of the differences of a point and the means.

![](../z_images/Pasted%20image%2020230225204059.png)

<span style="background:rgba(183, 152, 255, 0.3)">One side of the square could be of negative value</span>. For this reason we can have negative areas, in the upper-left and lower-right quadrant.
This is the reason why the covariance can be negative.

Obviously, if the points are all over and not going in a specific direction, the sum will be zero because the <span style="background:rgba(183, 152, 255, 0.3)">areas with different signs will eliminate each other</span>.

On the contrary, if we have a very marked and specific direction in the data, the covariance will be 1. The more sparse the data is, the closer to 0 it gets because of all the different sign areas.

Final remark, <span style="background:rgba(183, 152, 255, 0.3)">we are not getting any information about the strength of the relation</span>, only about its direction. We will see that this will be accomplished with the Pearson Correlation Coefficient, which will indicate direction and strength of the relation.

## Covariance vs. Correlation

Covariance and correlation both primarily assess the relationship between variables.

**Covariance** measures the total variation of two random variables from their expected values. Using covariance, we can only gauge the direction of the relationship (whether the variables tend to move in tandem or show an inverse relationship). However, it does not indicate the strength of the relationship, nor the dependency between the variables.

On the other hand, **correlation** measures the strength of the relationship between variables. Correlation is the scaled measure of covariance. It is dimensionless. In other words, the correlation coefficient is always a pure value and not measured in any units.

## Why are we dividing covariance by the product of the standard deviations?

BECAUSE, the covariance gives just the sum of the areas, which could be an arbitrary big number, there are no limits. 
BUT, <span style="background:rgba(183, 152, 255, 0.3)">if we divide by the standard deviations, we are giving normalizing this value</span>.

Both the covariance and the standard deviation are divided by n, so in the equation they cancel it out.
Since the standard deviation, without n, basically takes the sum of all the all the differences between the point and the mean (squared), it will simply be a sum of all the variances of all points.

So, simply, <span style="background:rgba(183, 152, 255, 0.3)">the product of the standard deviations is the maximum value that the covariance can assume</span>.

So if we multiply those two measures, we are basically forming an area, that is guaranteed to be bigger than the covariance, since the covariance can have negative areas and the standard deviations can't.

So if covariance is equal to the product of standard deviations, it means that all points lie on the same line, because all the areas of all the points are as big as they can get.