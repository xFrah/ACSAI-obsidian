If we cannot find the best possible parameters by using a formula or "closed form solution", you may need to use [gradient](Gradient.md) descent.

The function $\mathcal{J}(\theta;x,y)$ is a **convex quadratic function**. 

![](../z_images/Pasted%20image%2020230522115650.png)

> [!note] Function Analysis
> The [Hessian](Hessian.md) of $\mathcal{J}(\theta;x,y)$) at any vector $θ$ is the positive definite [matrix](../Linear%20Algebra/Matrix%20(ML).md) $X^TX$. Since $\mathcal{J}$ is lower bounded and grows at infinity, there is a minimum.
> 
> -   if $\operatorname{rank}({X}) =\min\{d,n\}$ then $X^TX$ is strictly positive definite. In this case the error function $\mathcal{J}$ is strictly convex, so the **minimum is unique (Ball Shape)**
> -   if $\operatorname{rank}({X}) < \min\{d,n\}$ then then $\mathcal{J}$ is not strictly convex and the minimum
> 

---

## The descent:

### 1. Initialization

We set all parameters $\theta$ to 0, or we use random values.


### 2. Loop

We compute the gradient of the loss with respect to the parameters:

$$\large\mathcal{J}(\theta;x,y)= \frac{1}{2} \sum_{i=1}^{n}\mathcal{L}\big(y_{i}, f_{\boldsymbol{\theta}}(x_i)\big)$$

1. We input the parameters into the loss function, so that we get a new function that has inputs $(x, y)$.

2. We take the gradient of the loss function.

3. We input $(x, y)$ into the gradient, which gives us the [[Partial derivatives|slope in every dimension]] of the curve at those inputs.

4. We then take a small step towards the direction of steepest descent.

5. We repeat this until convergence


### 3. Convergence

There are multiple indications that the thing has converge:

1. We can do early stopping by looking at validation loss.
2. There is no significant decrease in loss function
3. No variation in the parameters
4. Gradient [norm](../Linear%20Algebra/Norm.md) goes to zero


![](../z_images/Pasted%20image%2020230525172345.png)

---

## Cons

In order to update the parameters once, we have to iterate through all the data points first.
If the dataset is large, this may take too long.