| **Data Type y�** | **Expo. Family** | **Name/ML Topic** | 
|--------------------- |--------------------- |---------------------------- | 
| $\mathbb{R}$ | [Gaussian](Gaussian%20distribution.md)  LaPlace | Regression | 
| {0,1} | [Bernoulli](../Probability/Bernoulli%20distribution.md) | Binary Classification | 
| {1,K} | Categorical | Multi-class Classification | 
| $\mathbb{N}_{+}$ | Poisson | Poisson Regression (Counts) | 
| Categorical | Dirichlet | More advanced Topics |

We choose which distribution is best for us given the data type, the choice will determine what $\sigma$ we use in $f_{\boldsymbol{\theta}}(\mathbf{x}) \doteq \sigma\left(  \boldsymbol{\theta}^T\mathbf{x} \right)$.

Basically the formula will always be:

$$\large\boldsymbol{\theta} \leftarrow  \boldsymbol{\theta} +\gamma \left(y_i - \sigma(\mathbf{\theta}^T\mathbf{x}_i)\right)\mathbf{x}_i$$

### In [Logistic regression](Logistic%20Regression.md):
$$\sigma(z)= \frac{1}{1+\exp^{-z}}$$
### In [Linear regression](Linear%20Regression.md)
$$\sigma(z)= \frac{1}{\sqrt{2 \pi} \sigma}^{\LARGE-\frac{\left(y_i-\theta^{T} x_i\right)^{2}}{2 \sigma^{2}}}$$

> [!question]
> Actually, in Linear Regression we don't use any $\sigma$ function, why is it saying that we do that here?
