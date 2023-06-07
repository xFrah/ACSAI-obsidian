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
