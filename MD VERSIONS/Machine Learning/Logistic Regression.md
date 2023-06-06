This technique is used as a discriminative classifier.

> [!quote] Definition
> Discriminative means we model $p(y|x)$ what is the probability for the label $prob(Y=y)$ given $x$?

We model **[conditional probability](../Probability/Conditional%20Probability.md) of y | x:**

$$\large\begin{cases}p(y=1\,| \,\mathbf{x};\boldsymbol{\theta}) = f_{\boldsymbol{\theta}}\\p(y=0\,|\, \mathbf{x};\boldsymbol{\theta}) = 1- f_{\boldsymbol{\theta}}\end{cases}$$

where $f_\theta$ equals to:
$$\large f_{\boldsymbol{\theta}}(\mathbf{x}) \doteq \sigma\left(  \boldsymbol{\theta}^T\mathbf{x} \right)$$

and $\sigma$ equals to the [sigmoid](Sigmoid.md) function:
$$\large\sigma(z)= \frac{1}{1+\exp^{-z}}$$
with:
$$\large\lim_{z\mapsto \infty}\sigma(z)=1 \quad\text{and}\quad\large\lim_{z\mapsto -\infty}\sigma(z)=0$$
