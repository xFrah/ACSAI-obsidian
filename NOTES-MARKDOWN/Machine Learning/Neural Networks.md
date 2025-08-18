---
alias: Multi-Layer Perceptron, Multi-Layer Perceptrons, Multilayer Perceptron, Multilayer Perceptrons, MLP, MLPs
---
We can use the linear [[Multi-Class Classification|soft-max regression]] to represent a single layer of a neural network.


## The single layer

We use $k$ Perceptrons to give scores to $k$ classes based on the input $\mathbf{x}$.

$$\large\underbracket{\mathbf{z}}_{\mathbb{R}^{Kx1}} = \underbracket{\mathbf{W}}_{\mathbb{R}^{K\times d}}\underbracket{\mathbf{x}}_{\mathbb{R}^{d\times1}} + \underbracket{\mathbf{b}}_{\mathbb{R}^K}$$

Each row of the [matrix](Matrices.md) W contains the parameters of the [hyperplane](../Linear%20Algebra/Hyperplanes.md) of one class/Perceptron.
In other words, each row of W represents the feature that output neuron $z_i$ is looking for.

$$\large\mathbf{W} \mathbf{x}=\left(\begin{array}{c}-\text { neuron feature - } \\\vdots \\-\text { neuron feature }-\end{array}\right)\left(\begin{array}{c}\mid \\\mathbf{x} \\\mid\end{array}\right)$$

$$\large\sigma(\mathbf{W} \mathbf{x}  + \boldsymbol{b})=\sigma \circ \begin{bmatrix} \underline{w_{11}} & \underline{w_{12}} & \cdots & \underline{w_{1 d}} \\ w_{21} & w_{22} & \cdots & w_{2 d} \\ \vdots & \cdots & \ddots & \vdots \\ w_{k 1} & w_{m 2} & \cdots & w_{k d} \end{bmatrix}  \begin{bmatrix} x_{1} \\ x_{2} \\ \vdots \\ x_{d} \end{bmatrix} +  \begin{bmatrix} b_{1} \\ b_{2} \\ \vdots \\ b_{k} \end{bmatrix}  =\sigma \circ \begin{bmatrix} z_{1} \\ z_{2} \\ \vdots \\ z_{k} \end{bmatrix}$$

> [!info]
> We are using the same technique of the Perceptron, we are just using a lot of them.
> For a more detailed explanation look at [[Multi-Class Classification|this]].

> [!tldr]
> Each neuron's value equals to the [dot product](../Linear%20Algebra/Dot%20product.md) between the weights for that neuron and the data [vector](../Linear%20Algebra/Vectors.md) $\mathbb{x}$.

![](../z_images/Pasted%20image%2020230612021128.png)

---


## Adding layers

We can add other layers of Perceptrons to improve the expressivenes of our graph.

![](../z_images/Pasted%20image%2020230614134652.png)


By doing this, in the second layer we are basically classifying the features $\phi(x)$ picked up by the first hidden layer.

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

Now we want to derive this(its [partial derivatives](../Calculus%202/Partial%20derivatives.md)) in order to obtain the [gradient](Gradient.md) of the loss function.

$$\large\frac{\partial\mathcal{L}(x,y,z)}{\partial x} =  (\mathbf{x}z+yz)^{\prime}=(\mathbf{x}z)^{\prime}+(yz)^{\prime} = z$$
$$\large\frac{\partial\mathcal{L}(x,y,z)}{\partial y} =  (xz+\mathbf{y}z)^{\prime}=(xz)^{\prime}+(\mathbf{y}z)^{\prime} = z$$
$$\large \frac{\partial\mathcal{L}(x,y,z)}{\partial z} =  x+y$$

> [!hint]
> $(\mathbf{x}z+yz)^{\prime}=(\mathbf{x}z)^{\prime}+(yz)^{\prime}$ with respect to x, is because the [derivative](../Calculus/8.%20Differentiation.md) of a sum is the sum of the derivatives of the two components.
> 
> Recall also that $(\text{const})^\prime=0$


Then we proceed with [gradient descent](Gradient%20Descent.md).

---


## Backpropagation

Instead of computing the derivatives by hand, we want to automate the process so that it can work with any loss function and can be more easily implemented.

This method traverses the network in reverse order, from the output to the input layer, according to the chain rule from calculus. 

All the derivatives from before can be rewritten using the chain rule like this: 

$$\large\frac{\partial\mathcal{L}}{\partial x} =  \big(\underbracket{(\mathbf{x}+y)}_{q}z\big)^{\prime}=\frac{\partial\mathcal{L}}{\partial q}\frac{\partial q}{\partial x}$$

Since the chain rule computes the gradient of each intermediate variable and parameter ([partial derivatives](../Calculus%202/Partial%20derivatives.md)), it will also output the [gradients](Gradient.md) $\LARGE\frac{\partial\mathcal{L}}{\partial \mathbf{W}^1}$ and $\LARGE\frac{\partial\mathcal{L}}{\partial \mathbf{W}^2}$, which is exactly what we need.


We have this fucking graph and every node is an operation/nested function.

![](../z_images/Pasted%20image%2020230619195457.png)


### 1. Starting the chain, base case

We want to derive $\mathcal{L}$, which is composed of $z$ and $q$:

$$\large \mathcal{L}(x,y,z) = q\cdot z = (x+y)\cdot z$$

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
> We want to minimize the function, but we have multiple variables so we change only one of them at a time, this time we are fixing everything but $z$:
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
> 
> $$\large\frac{\partial\mathcal{L}}{\partial y} = \frac{\partial\mathcal{L}}{\partial q}\frac{\partial q}{\partial y} = z\cdot 1= -4$$
> $$\large\frac{\partial\mathcal{L}}{\partial x} = \frac{\partial\mathcal{L}}{\partial q}\frac{\partial q}{\partial x} = z\cdot 1= -4$$
> 
> ![](../z_images/Pasted%20image%2020230625105044.png)

---


## Gradient of [SoftMax](Multi-Class%20Classification.md) + [Cross-Entropy Loss](Cross-entropy.md)


![](../z_images/Pasted%20image%2020230625131211.png)


Here is the list of layers:

$$\large\text{Input layer} \quad\rightarrow\quad \mathbf{x}$$
$$\large\text{First hidden layer} \quad\rightarrow\quad\mathbf{h} = \mathbf{W^1x}+\mathbf{b^1}$$
$$\large\text{Relu activation layer} \quad\rightarrow\quad \sigma(\mathbf{z})= \max(0,\,\mathbf{z})$$
$$\large \text{Second hidden layer} \quad\rightarrow\quad\mathbf{z} = \mathbf{W^2}\sigma+\mathbf{b^2}$$
$$\large\text{Softmax}\quad\rightarrow\quad\hat{y}=\frac{e^{z_i}}{\sum_{k=1}^K e^{z_k}}$$
$$\large \text{Cross-entropy Loss} \quad\rightarrow\quad -\sum_{x \in X} y_i\log \hat{y}_i$$

We want to get the gradient of the loss function with respect to the weights.
In order to do this, we use the chain rule on the graph above:

$$\large\frac{\partial\mathcal{L}}{\partial\mathbf{W}^1} = \frac{\partial\mathcal{L}}{\partial\mathbf{z}}\frac{\partial\mathbf{z}}{\partial\sigma}\frac{\partial\mathbf{\sigma}}{\partial\mathbf{h}}\frac{\partial\mathbf{h}}{\partial\mathbf{W}^1}$$


### 1) Defining $\mathcal{L}$

Recall the softmax formula:

$$\large\text{softmax}_i(z) = \frac{e^{z_i}}{\sum_{k=1}^K e^{z_k}}= \hat{y}_i = p,\quad \text{cross-entropy} = -\sum_{x \in X} y_i\log \hat{y}_i$$

> [!hint] What was softmax again?
> The function softmax assigns decimal probabilities to each neuron/class in a multi-class problem.
> 
> $$\LARGE [-\infty, \;\infty] \rightarrow [0,\; 1]$$
> 
> It takes the vector $z$ as input and outputs a vector of same length $k$.


Based on these two functions, the loss function is:

$$\large\begin{split}\begin{aligned}\mathcal{L}(\mathbf{y}, \hat{\mathbf{y}}) &=  - \sum_{j=1}^q y_j \log \frac{e^{z_j}}{\sum_{k=1}^q e^{z_k}} \\&= \sum_{j=1}^q y_j \log \sum_{k=1}^q e^{z_k} - \sum_{j=1}^q y_j z_j\\&= \log \sum_{k=1}^q e^{z_k} - \sum_{j=1}^q y_j z_j.\end{aligned}\end{split}$$
 
Now that we have the loss function, we can go down the chain.

$$\large\frac{\partial\mathcal{L}}{\partial\mathbf{W}^1} = \frac{\partial\mathcal{L}}{\partial\mathbf{z}}\frac{\partial\mathbf{z}}{\partial\mathbf{W}^1}$$


### 2) Gradient of Loss function $\large\frac{\partial\mathcal{L}}{\partial\mathbf{z}} \rightarrow$ vector of length $k$

We take the derivative of $\mathcal{L}$ with respect to class $j$, which is equal to:

$$\large\frac{\partial\mathcal{L}}{\partial_{z_j}} (\mathbf{y}, \hat{\mathbf{y}} \,\text{or z}) = \frac{e^{z_j}}{\sum_{k=1}^q e^{z_k}} - y_j = \mathrm{softmax}(\mathbf{z})_j - y_j$$

> [!example]
> If we do that for every neuron, given the following predictions and ground truth...
> 
> $$\large \hat{y} = [0.2,\;0.7, \;0.1]\quad y =[0, \;1, \;0]$$
> 
> ... we get this:
> $$\large \frac{\partial\mathcal{L}}{\partial z}  = [0.2, \;0.7-1, \;0.1] = \underbracket{[0.2, \;-0.3, \;0.1]}_{gradient}$$
> 

> [!hint]
> Since the output is a [vector](../Linear%20Algebra/Vectors.md) composed of [partial derivatives](../Calculus%202/Partial%20derivatives.md), we can call it a [gradient](Gradient.md)!
> 
> $$\large\begin{bmatrix}
\LARGE\frac{\partial \mathcal{L}}{\partial z_1} \\
\LARGE\frac{\partial \mathcal{L}}{\partial z_2} \\
\LARGE\vdots
\end{bmatrix}$$


We go further down the chain:

$$\large\frac{\partial\mathcal{L}}{\partial\mathbf{W}^1} = \frac{\partial\mathcal{L}}{\partial\mathbf{z}}\frac{\partial\mathbf{z}}{\partial\mathbf{W}^1} \quad\rightarrow\quad \frac{\partial\mathcal{L}}{\partial\mathbf{z}}\underbracket{\frac{\partial\mathbf{z}}{\partial\mathbf{\sigma}}\frac{\partial\mathbf{\sigma}}{\partial\mathbf{W}^1}}_{\frac{\partial\mathbf{z}}{\partial\mathbf{W}^1}}$$

### 3) Gradient of Second layer $\large\frac{\partial z}{\partial\mathbf{\sigma}} \rightarrow$ matrix

We recall that

$$\large\mathbf{z} = \mathbf{W}\sigma+\mathbf{b}$$

So the derivative with respect to $\sigma$:

$$\large \frac{\partial\mathbf{z}}{\partial\mathbf{\sigma}}=\mathbf{W}$$

### 4) Gradient of ReLu $\large\frac{\partial \sigma}{\partial\mathbf{h}} \rightarrow$ vector/diagonal matrix of {0, 1}

The derivative of ReLu is a diagonal matrix that can only have 0 and 1s on the diagonal:

$$\large\frac{\partial\mathbf{\sigma}}{\partial \mathbf{h}} = \operatorname{diag(\{0,1\}_{ii})}$$

Since the output is a diagonal matrix/[jacobian](Jacobian.md) full of 0s, it is not implemented as a full matrix in practice but as **the diagonal vector**, because it would be very memory-inefficient.

![](../z_images/Pasted%20image%2020230629110500.png)

> [!hint] What was $\sigma$ again?
> $$\large\sigma(z)= \max(0,\,z) \quad \text{ReLu}$$
> 
> ![](../z_images/Pasted%20image%2020230628141400.png)
> 
> It outputs a vector of length $k$, same as vector $z$.

> [!faq] Wtf? Why?
> https://math.stackexchange.com/a/4081490


### 5) Gradient of First layer $\frac{\partial\mathbf{h}}{\partial\mathbf{W}^1} \rightarrow$ scalar/vector with one value

Remember that here h returns a vector of scores for each class or feature of W.

$$\large\mathbf{h} = \mathbf{W}\mathbf{x}+\mathbf{b}$$

Instead of considering the whole vector, we take the function for a single score/element of h...

$$\large \mathbf{h}_i = (\mathbf{W}_i)^T\mathbf{x}+b_i = \sum_j \mathbf{W}_{ij} x_j + \mathbf{b}_i$$

... and we derive it:

$$\large\frac{\partial \mathbf{h}}{\partial \mathbf{W_{ij}}} = x_j$$

> [!hint] Why this derivative?
> Basically the [dot product](../Linear%20Algebra/Dot%20product.md) between $\mathbf{W_j}$ and $x$ is just doing this:
> 
> $$\large\mathbf{h}_i=\sum_j\mathbf{W_{ij} x_j}\quad\rightarrow\quad \mathbf{W}_{i,0} \cdot x_0 + \mathbf{W}_{i,1} \cdot x_1 + \dots + \mathbf{W}_{i,n}\cdot x_n$$
> 
> If we take the derivative with respect to a single $\mathbf{W_j}$, all the products/constants are turned into 0s, and we are left with a single element of the form $\mathbf{W_j} \cdot x_j$, then we turn $\mathbf{W_j}$ into a 1 and all that remains is $x_j$.
> 
> $$\large\frac{\partial\mathbf{h}}{\partial\mathbf{W}_{ij}} = \begin{bmatrix}           \quad \LARGE\frac{\partial\mathbf{h}_0}{\partial\mathbf{W}_{ij}} \large= 0 + \dots + 0\quad \\           \LARGE\frac{\partial\mathbf{h}_1}{\partial\mathbf{W}_{ij}} \large= 0 + \dots + 0 \\           \vdots \\           \LARGE\frac{\partial\mathbf{h}_i}{\partial\mathbf{W}_{ij}} \large= 0+x_{j}+0\\            \vdots \\            \LARGE\frac{\partial\mathbf{h}_n}{\partial\mathbf{W}_{ij}} \large=0 + \dots + 0         \end{bmatrix} \qquad \frac{\partial\mathbf{h}}{\partial\mathbf{W}_{ij}} = \begin{bmatrix}           0 \\           0 \\           \vdots \\           x_{j}~~i^{\text{th}} \text{row}\\            \vdots \\            0         \end{bmatrix}$$
> 
> ![](../z_images/Pasted%20image%2020230629145859.png)


### Let's wrap it up

![](../z_images/Pasted%20image%2020230629183351.png)
![](../z_images/Pasted%20image%2020230629234007.png)
![](../z_images/Pasted%20image%2020230629234024.png)
![](../z_images/Pasted%20image%2020230629234038.png)
![](../z_images/Pasted%20image%2020230629234048.png)
