| **Data Type y�** | **Expo. Family** | **Name/ML Topic** | 
|--------------------- |--------------------- |---------------------------- | 
| $\mathbb{R}$ | Gaussian  LaPlace | Regression | 
| {0,1} | Bernoulli | Binary Classification | 
| {1,K} | Categorical | Multi-class Classification | 
| $\mathbb{N}_{+}$ | Poisson | Poisson Regression (Counts) | 
| Categorical | Dirichlet | More advanced Topics |

We choose which distribution is best for us given the data type.

The choice will determine what $\sigma$ we use in $f_{\boldsymbol{\theta}}(\mathbf{x}) \doteq \sigma\left(  \boldsymbol{\theta}^T\mathbf{x} \right)$
