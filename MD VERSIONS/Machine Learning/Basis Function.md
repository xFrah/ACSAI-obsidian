A basis function is a transform that adds dimensionality/features to the x space in a function.
We can start with $d$ dimensions/features to end up with $m$:

$$\large\mathbf{x} = 
\begin{bmatrix}
x \\ 1
\end{bmatrix}, \quad \boldsymbol{\phi}(\mathbf{x}) =
\begin{bmatrix}
x^2 \\ x \\ 1
\end{bmatrix}$$

which results in the following change of $f_{\boldsymbol{\theta}}(\mathbf{x})$:

$$\large \boldsymbol{\theta}^T\mathbf{x} = 
\theta_0  + \theta_1\cdot x
\quad\rightarrow \quad 
\boldsymbol{\theta}^T\boldsymbol{\phi}(\mathbf{x}) = 
\theta_0  + \theta_1\cdot x +\theta_2\cdot x^2$$

> [!hint]
> As you can see, there are as much parameters as there are features.

