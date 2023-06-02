By using a [basis function](Basis%20Function.md), we can transform the dimensions(vector $\mathbf{x}$) and still use [linear regression](Linear%20Regression.md) to fit a curve.

$$\large\mathbf{x} = 
\begin{bmatrix}
x \\ 1
\end{bmatrix}, \quad \boldsymbol{\phi}(\mathbf{x}) =
\begin{bmatrix}
x^2 \\ x \\ 1
\end{bmatrix}$$

$$\large \boldsymbol{\theta}^T\mathbf{x} = 
\theta_0  + \theta_1\cdot x
\quad\rightarrow \quad 
\boldsymbol{\theta}^T\boldsymbol{\phi}(\mathbf{x}) = 
\theta_0  + \theta_1\cdot x +\theta_2\cdot x^2$$


The thing now looks like this:

$$\large f(x)=\boldsymbol{\theta}^T\boldsymbol{\phi}(\mathbf{x})$$

> [!hint]
> We can still use linear regression to fit due to fact that the relationship between $\mathbf{x}$ and the parameters $\boldsymbol{\theta}$ is still linear.
> 
> We kind of just added some dimensions and parameters.

> [!hint]
> You can also think of normal linear regression with this formula, but with $\boldsymbol{\phi}(\mathbf{x})$ doing nothing.


Let $M$ be the number of output dimensions of the basis function.

![](../z_images/Pasted%20image%2020230602125608.png)

---

## What about the overfitting?

If you debug the coefficients in the image above, you will see that overfitting is related to the size of the parameters.
The bigger the order of the polynomial, the bigger the parameters.

![](../z_images/Pasted%20image%2020230602131410.png)

We use a technique called Weight Decay or $\large\ell_2$ Regularization.

---

## $\boldsymbol{\ell_2}$ Regularization or Weight Decay

We add a penalty cost to the loss function:

$$\large\mathbf{\theta}^{\star} = \arg\min_{\mathbf{\theta}} (\,\mathcal{J}_{\text{data}}(\mathbf{\theta};\mathbf{x},y)  +\lambda\mathcal{J}_{\text{reg.}}(\mathbf{\theta})\,)$$

Here is the closed form solution for getting the parameters as we set the gradient to 0:
$$\nabla_{\theta}\mathcal{J}(\mathbf{\theta};\mathbf{x},y) = \frac{1}{2} \sum_{i=1}^{n}\mathcal{L}\big(y_{i}, f_{\boldsymbol{\theta}}(\mathbf{x}_i)\big) + \frac{\lambda}{2} \boldsymbol{\theta}^T \boldsymbol{\theta}=0 
\quad \rightarrow \quad 
(\lambda \mathbf{I} + \mathbf{X}^T\mathbf{X})\boldsymbol{\theta} = \mathbf{X}^T\mathbf{y}
\quad \rightarrow \quad 
\boldsymbol{\theta} = (\lambda \mathbf{I} + \mathbf{X}^T\mathbf{X})^{-1} \mathbf{X}^T\mathbf{y}$$


> [!hint] Formula Explanation
> Of course we remember that the closed form solution is usually computed as:
> 
$$\nabla_{\theta} \mathcal{J}(\theta;X,y)= \nabla_{\theta} \frac{1}{2} \sum_{i=1}^{n}\mathcal{L}\big(y_{i}, f_{\boldsymbol{\theta}}(\mathbf{x}_i)\big) = 0 \quad\rightarrow \quad X^TX\theta = X^Ty \quad\rightarrow \quad\theta = \underbracket{(X^TX)^{-1}X^T}_{\text{pseudo inverse}}y$$
> 
> Where the loss function is usually the least squares:
> 
> $$\sum_{i=1}^{n}\mathcal{L}\big(y_{i}, f_{\boldsymbol{\theta}}(\mathbf{x}_i)\big) = \big(X\theta - y \big)^T\big(X\theta - y \big)$$
> 
> Here we are just adding the term $\Large\frac{\lambda}{2} \normalsize\boldsymbol{\theta}^T \boldsymbol{\theta}$ to the mixture, which means that we are squaring the parameters and summing them:
> $$\large\sum^{m}_{i=0}\theta_i^2$$
> 
> so that the loss increases as the parameters get bigger, thus preventing overfitting to a degree.




