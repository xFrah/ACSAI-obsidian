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

> [!example]
> We try linear regression with $m = 1$:
> 
> ![](../z_images/Pasted%20image%2020230531092032.png)
> 
> We can clearly see that the error is high, so let's try with more features, we set $m=2$:
> 
> ![](../z_images/Pasted%20image%2020230531092552.png)
> 
> It's better, but still not enough, we try with $m=3$:
> 
> ![](../z_images/Pasted%20image%2020230531092757.png)
> 
> $m=4$:
> 
> ![](../z_images/Pasted%20image%2020230531092826.png)
> 
> $m=5$:
> 
> ![](../z_images/Pasted%20image%2020230531092849.png)
> 
> $m=6$:
> 
> ![](../z_images/Pasted%20image%2020230531092902.png)
> 
> 




