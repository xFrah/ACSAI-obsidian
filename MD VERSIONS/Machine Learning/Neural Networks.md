---
alias: Multi-Layer Perceptron, Multi-Layer Perceptrons, Multilayer Perceptron, Multilayer Perceptrons, MLP, MLPs
---

We can use the linear [[Multi-Class Classification|soft-max regression]] to represent a single layer of a neural network.


## The single layer

$$\large\underbracket{\mathbf{z}}_{\mathbb{R}^{Kx1}} = \underbracket{\mathbf{W}}_{\mathbb{R}^{K\times d}}\underbracket{\mathbf{x}}_{\mathbb{R}^{d\times1}} + \underbracket{\mathbf{b}}_{\mathbb{R}^K}$$
Each row of the [matrix](../Linear%20Algebra/Matrix.md) W contains the parameters of the [hyperplane](../Linear%20Algebra/Hyperplanes.md) of one class.
In other words, each row of W represents the feature that output neuron k is looking for.

$$\large\mathbf{W} \mathbf{x}=\left(\begin{array}{c}-\text { neuron feature - } \\\vdots \\-\text { neuron feature }-\end{array}\right)\left(\begin{array}{c}\mid \\\mathbf{x} \\\mid\end{array}\right)$$


> [!info]
> We are using the same technique of the Perceptron, we are just using a lot of them.
> For a more detailed explanation look at [[Multi-Class Classification|this]].

> [!tldr]
> Each neuron's value equals to the [dot product](../Linear%20Algebra/Dot%20product.md) between the weights for that neuron and the data [vector](../Linear%20Algebra/Vectors.md) $\mathbb{x}$.
> 
> We then put the result through a softmax and the output will indicate whether a neuron fires or not.

![](../z_images/Pasted%20image%2020230612021128.png)

---

## Adding layers

We can add other layers to improve the expressivenes of our graph.

![](../z_images/Pasted%20image%2020230614134652.png)


By doing this, in the last layer we are basically classifying the features $\phi(x)$ picked up by the hidden layer.

$$\large\mathbf{p}=\sigma(\mathbf{W}^2\underbracket{\left(\sigma(\mathbf{W}^1 \mathbf{x}  + \boldsymbol{b}^1) \right)}_{\boldsymbol{\phi}(x)}   + \boldsymbol{b}^2)$$
or, with more layers:

$$\large \begin{aligned}
&\mathbf{z}^{[1]}=\mathbf{W}^{[1]} \mathbf{x}^{(i)}+\mathbf{b}^{[1]} \\
&\mathbf{a}^{[1]}=\sigma\left(\mathbf{z}^{[1]}\right) \\
&\mathbf{z}^{[2]}=\mathbf{W}^{[2]} \mathbf{a}^{[1]}+\mathbf{b}^{[2]} \\
&\mathbf{a}^{[2]}=\sigma\left(\mathbf{z}^{[2]}\right) \\
&\mathbf{z}^{[3]}=\mathbf{W}^{[3]} \mathbf{a}^{[2]}+\mathbf{b}^{[3]} \\
&\hat{y}^{(i)}=\mathbf{a}^{[3]}=\sigma\left(\mathbf{z}^{[3]}\right)
\end{aligned}$$

![](../z_images/Pasted%20image%2020230614193952.png)

> [!info]
> In the hidden layer we use activation functions as the [sigmoid](Sigmoid.md)(to output the probability) or ReLu.
> 
> Nowadays we don't use sigmoid in the hidden layers.

---

## Initialization

Why can't you just put all the weights to 0 or another constant value? 
Because if every neuron in a layer is the same, they all contribute equally to the loss, and when we compute the gradient, every neuron get the same update.

> [!note]
> This property is called symmetry.


So we need an asymmetric initialization, randomness breaks the symmetric so that each neuron learns different things (gradients updates are different).

---

## Learning the parameters

Assume we have the following loss function:

$$\large \mathcal{L}(x,y,z) = (x+y)z$$

Now we want to derive this(its [partial derivatives](../Calculus/Partial%20derivatives.md)) in order to obtain the [gradient](Gradient.md) of the loss function.

$$\large\frac{\partial\mathcal{L}(x,y,z)}{\partial x} =  (\mathbf{x}z+yz)^{\prime}=(\mathbf{x}z)^{\prime}+(yz)^{\prime} = z$$
$$\large\frac{\partial\mathcal{L}(x,y,z)}{\partial y} =  (xz+\mathbf{y}z)^{\prime}=(xz)^{\prime}+(\mathbf{y}z)^{\prime} = z$$
$$\large \frac{\partial\mathcal{L}(x,y,z)}{\partial z} =  x+y$$

> [!hint]
> $(\mathbf{x}z+yz)^{\prime}=(\mathbf{x}z)^{\prime}+(yz)^{\prime}$ with respect to x, is because the derivative of a sum is the sum of the derivatives of the two components.
> 
> Recall also that $(\text{const})^\prime=0$


Then we proceed with [gradient descent](Gradient%20Descent.md).

---

## Learning the parameters... but faster

Instead of computing the derivatives by hand, we want to automate the process so that it can work with any loss function and can be more easily implemented.

For these reasons we re-write everythign using the [chain rule](../Calculus/Chain%20Rule.md) of derivation.
We have this fucking graph and every node is an operation.

![](../z_images/Pasted%20image%2020230619195457.png)


### 1. Starting the chain, base case

We want to derive $\mathcal{L}$, which is composed of $z$ and $q$:

$$\large \mathcal{L}(x,y,z) = q\cdot z$$

So we compute the partial derivatives of $\mathcal{L}$ with respect to $q$ and with respect to $z$:

$$\large\frac{\partial\mathcal{L}}{\partial q}=z, \frac{\partial\mathcal{L}}{\partial z}=q$$


### 2. Going down the chain

But we know that $q$ is actually a whole other function $q(x, y)$, so we have got to derive it aswell with respect to its two inputs:

$$\large\frac{\partial\mathcal{q}}{\partial x}=1, \frac{\partial\mathcal{q}}{\partial y}=1$$

We now have the derivatives of every piece of the graph:

$$\large\frac{\partial\mathcal{L}}{\partial q}=z, \frac{\partial\mathcal{L}}{\partial z}=q, \frac{\partial\mathcal{q}}{\partial x}=1, \frac{\partial\mathcal{q}}{\partial y}=1$$


### 3. Put the chain together

Now we use the chain rule to put it all together and take the derivative with respect to $x$:

$$\large\frac{\partial\mathcal{L}(x,y,z)}{\partial x} =  \big(\underbracket{(\mathbf{x}+y)}_{q}z\big)^{\prime}=\frac{\partial\mathcal{L}}{\partial q}\frac{\partial q}{\partial x}$$

So in this case the result would be:

$$\large \frac{\partial\mathcal{L}}{\partial q}\frac{\partial q}{\partial x} = z \cdot 1$$

> [!hint]
> This is possible because we remember the chain rule...
> 
> $$\large\frac{d}{dx}\left(f(g(x))\right) = f'(g(x)) \cdot g'(x)$$
> 
> ... and we know how to apply it:
> 
> $$\large\frac{d}{dx}\mathcal{L}(q(x)\cdot z)=(q(x)\cdot z)^\prime \cdot q'(x)=\frac{\partial\mathcal{L}}{\partial q}\frac{\partial q}{\partial x}$$

> [!example]
> We input some values into the graph:
> 
> ![](../z_images/Pasted%20image%2020230621195556.png)
> 
> Now we compute the derivative of the loss function and it comes out as 1.
> 
> $$\large\frac{\partial\mathcal{L}}{\partial \mathcal{L}}=1$$
> 
> This will act as a base for recursion, in order to apply the changes to the rest of the graph.
> 
> ![](../z_images/Pasted%20image%2020230621200004.png)
> 
> We want to minimize the function, but we have multiple variables so we change only one of them at a time, this time we are fixing everything but $z$.
> 
> What is the value of the gradient of $\mathcal{L}$ on $z$?
> 
> $$\large\frac{\partial\mathcal{L}}{\partial z}= q = 3$$
> 
> ![](../z_images/Pasted%20image%2020230621200143.png)
> 
> Now we fix everything but $q$:
> 
> $$\large\frac{\partial\mathcal{L}}{\partial q}= z = -4$$
> 
> ![](../z_images/Pasted%20image%2020230621200326.png)
