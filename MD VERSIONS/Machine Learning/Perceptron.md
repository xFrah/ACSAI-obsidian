> [!note] A few notes
> - We study this algorityhm mostly for **historical importance and didatic duty**
> - Nowdays it is not anymore practically used

![](../z_images/Pasted%20image%2020230604174005.png)


Look at this graph, understand that:
- $\theta$ is a [[Vectors|vector]] on the 2D space.
- $x$ is a vector on the 2D space.
- $\theta^T x$ is the dot product between the two vectors.

> [!hint] [Dot product](../Linear%20Algebra/Dot%20product.md) recap
> Recall that the dot product is basically multiplying the magnitude of one vector by the magnitude of the projection of the other(on the first vector).
> 
> ![](../z_images/Pasted%20image%2020230305172741.png)
> 
> Basically, the dot product:
> - equals $0$ when the vectors are perpendicular.
> - equals $|v|^2$ when the vectors lie in the same direction.
> - is negative when the vectors go in opposite directions, and viceversa.


By setting the parameter vector $\theta$ we are splitting the space and use it as a classificator. 
We don't give a shit about the value of the dot product, **we just need the sign**, which represents which part of the space the datapoint lies in.

![](../z_images/Pasted%20image%2020230604181653.png)

---

## So what actually is a perceptron?

This is the formula of the perceptron:
$$\large f_{\boldsymbol{\theta}}(\mathbf{x}) \doteq \sigma\left(  \boldsymbol{\theta}^T\mathbf{x} \right)$$
where:
$$\large\sigma(z)= \begin{cases} +1, & \mbox{if } z\ge0 \\ 0, & \mbox{if } z<0\end{cases}$$

We compute the dot product as explained before, then we output 1 if the result is positive, else 0.
1 corresponds to one side of the space, 0 to the other.

---

## How to fit parameters

We update the parameters until convergence by using this formula:

$$\large\boldsymbol{\theta} \leftarrow  \boldsymbol{\theta} +\gamma \left(y - \sigma(\mathbf{\theta}^T\mathbf{x})\right)\mathbf{x}$$

> [!hint] Formula Explanation
> 
> This formula adds the vector $\gamma \left(y - \sigma(\mathbf{\theta}^T\mathbf{x})\right)\mathbf{x}$ to the parameter vector $\theta$ in order to correct the shot in case of misclassification.
> 
> ![](../z_images/Pasted%20image%2020230604190444.png) 
> In this example the dot product is negative and so the output is 0, but it should be 1, so there has been a missclassification and we need to update the parameters.
> 
> Considering that $y=\{0, 1\}$:
> $$\large y - \sigma(\mathbf{\theta}^T\mathbf{x}) = \{-1, 0, +1\}$$
> 
> Now we are ready to understand the following:
> - In the correct case (both negative and positive point), $\boldsymbol{\theta} \leftarrow  \boldsymbol{\theta}$ is kept the same:
> $$\boldsymbol{\theta} \leftarrow  \boldsymbol{\theta} +0\cdot\gamma \mathbf{x}$$
>  - Given $(\mathbf{x}, y=1)$ but $\sigma\left(\mathbf{\theta}^T\mathbf{x}\right)=0$ then update $\theta$ with a bit of $+x$. (add a bit of $x$ to $\theta$).
>  $$\boldsymbol{\theta} \leftarrow  \boldsymbol{\theta} +1\cdot\gamma \mathbf{x}$$
>  - Given $(\mathbf{x}, y=0)$ but $\sigma\left(\mathbf{\theta}^T\mathbf{x}\right)=1$ then update $\theta$ with a bit of $-x$. (subtract a bit of $x$ to $\theta$):
>    
> $$\boldsymbol{\theta} \leftarrow  \boldsymbol{\theta} +(-1)\cdot\gamma \mathbf{x}$$
> 
> ![](../z_images/Pasted%20image%2020230604192208.png)

---

## Perceptron's weaknesses

- It loops forever if the data is **NOT** linearly separable.
- Even if the data is linearly separable, it may take an amount of time that is **infeasible** in practice to use it.
- Does not converge to an optimal solution such as SVM, but it just returns a generic separating hyper-plane.