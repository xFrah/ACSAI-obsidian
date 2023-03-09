Getting the covariance of two series is a way of calculating the relationship between two variables and it will tell us <span style="background:rgba(183, 152, 255, 0.3)">how much two random variables vary together</span>.

The formula is:

$$\LARGE\operatorname{cov}(X,Y) = \sum(X - \mu_X)(Y - \mu_Y)$$

Where:
-   **Xi** – the values of the X-variable
-   **Yj** – the values of the Y-variable
-   **μX** – the [[Mean]] (average) of the X-variable
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

Final remark, <span style="background:rgba(183, 152, 255, 0.3)">we are not getting any information about the strength of the relation</span>, only about its direction. We will see that this will be accomplished with the Pearson [Correlation Coefficient](Correlation%20coefficient.md), which will indicate direction and strength of the relation.