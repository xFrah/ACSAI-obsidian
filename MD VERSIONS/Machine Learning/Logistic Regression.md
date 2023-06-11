This technique is used as a discriminative classifier.

> [!quote] Definition
> Discriminative means we model $p(y|x)$ what is the probability for the label $prob(Y=y)$ given $x$?


We model the [conditional probability](../Probability/Conditional%20Probability.md) of $y\, | \,x$:

$$\large\begin{cases}p(y=1\,| \,\mathbf{x};\boldsymbol{\theta}) = f_{\boldsymbol{\theta}}\\p(y=0\,|\, \mathbf{x};\boldsymbol{\theta}) = 1- f_{\boldsymbol{\theta}}\end{cases}$$

where $f_\theta$ equals to:

$$\large f_{\boldsymbol{\theta}}(\mathbf{x}) \doteq \sigma\left(  \boldsymbol{\theta}^T\mathbf{x} \right)$$

and $\sigma$ equals to the [sigmoid](Sigmoid.md) function:

$$\large\sigma(z)= \frac{1}{1+\exp^{-z}} \quad\rightarrow\quad f_{\boldsymbol{\theta}}(\mathbf{x}) \doteq \frac{1}{1+\exp^{-\boldsymbol{\theta}^T\mathbf{x}}}$$

> [!hint] Explanation
> Recall that a sigmoid function will look like this:
> ![](../z_images/Pasted%20image%2020230606145350.png)
> 
> We use the output of the sigmoid as a probability that $y=1$, for every value of $x$.
> In fact we can use it as a classifier with parameters $\theta$:
> 
> $$\large\text{If} \quad x=0 \quad\text{then} \quad p(y=1\,|\,0;\theta)=0.5$$
> 
> ![](../z_images/Pasted%20image%2020230607093521.png)
> 
>When we change the parameters $\theta$ we change the shape of the sigmoid(its extension in all dimensions):
> 
> ![](../z_images/Pasted%20image%2020230606204042.png)

> [!note]
> 
> $$\large\lim_{z\mapsto \infty}\sigma(z)=1 \quad\text{and}\quad\large\lim_{z\mapsto -\infty}\sigma(z)=0$$
> 

---

## Learning parameters in Logistic Regression

We use the same statistical approach that we used with linear regression.
Keep in mind that $f_\theta$ is defined as:

$$\large f_{\boldsymbol{\theta}}(\mathbf{x}) \doteq \frac{1}{1+\exp^{-\boldsymbol{\theta}^T\mathbf{x}}}$$

For a single point, the conditional probability of $y$ can be written as:

$$\large p(y\mid\mathbf{x};\boldsymbol{\theta}) = \big(f_{\boldsymbol{\theta}}\big)^y\big(1-f_{\boldsymbol{\theta}}\big)^{1-y}$$

> [!note]
> 
> In the case of [linear regression](Linear%20Regression.md), the [conditional probability](../Probability/Conditional%20Probability.md) of $y$ was:
> 
> $$\large p\left(y_i \mid x_i ; \theta\right)=\frac{1}{\sqrt{2 \pi} \sigma}^{\Huge-\frac{\left(y_i-\theta^{T} x_i\right)^{2}}{2 \sigma^{2}}}$$
> 
> We used a [Gaussian distribution](Gaussian%20distribution.md), but here in Logistic Regression we use a [Bernoulli distribution](../Probability/Bernoulli%20distribution.md).

![](../z_images/Pasted%20image%2020230610213536.png)

For multiple points, it is:

$$\large L(\theta;\mathbf{X};\mathbf{y})=p(\vec{y} \mid {\mathbf{x}_1,\ldots,\mathbf{x}_n} ; \theta)=\prod_{i=1}^{n}\left(f_{\boldsymbol{\theta}}\left(x_i\right)\right)^{y_i} \;\left(1-f_{\boldsymbol{\theta}}(x_i)\right)^{1-y_i}$$

![](../z_images/Pasted%20image%2020230610213720.png)