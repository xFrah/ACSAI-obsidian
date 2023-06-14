---
alias: Multi-Layer Perceptron, Multi-Layer Perceptrons, Multilayer Perceptron, Multilayer Perceptrons, MLP, MLPs
---

We can use the linear [[Multi-Class Classification|soft-max regression]] to represent a single layer of a neural network.


## The single layer

$$\large\underbracket{\mathbf{z}}_{\mathbb{R}^{Kx1}} = \underbracket{\mathbf{W}}_{\mathbb{R}^{K\times d}}\underbracket{\mathbf{x}}_{\mathbb{R}^{d\times1}} + \underbracket{\mathbf{b}}_{\mathbb{R}^K}$$
Each row of the [matrix](../Linear%20Algebra/Matrix.md) W contains the parameters of the [hyperplane](../Linear%20Algebra/Hyperplanes.md) of one class.

In other words, each row of W is an output neuron k, which in this case is also connected with the weight of class k.

$$\large\mathbf{W} \mathbf{x}=\left(\begin{array}{c}-\text { neuron - } \\\vdots \\-\text { neuron }-\end{array}\right)\left(\begin{array}{c}\mid \\\mathbf{x} \\\mid\end{array}\right)$$


> [!tldr]
> Each neuron's value equals to the dot product between the weights for that neuron and the data vector $\mathbb{x}$.
> 
> We then put the result through a softmax and the output will indicate whether a neuron fires or not.

![](../z_images/Pasted%20image%2020230612021128.png)

---

## Adding layers

We can add other layers to improve the expressivenes of our graph.

![](../z_images/Pasted%20image%2020230614134652.png)


By doing this, in the last layer we are basically classifying the features $\phi(x)$ picked up by the hidden layer.

$$\large\mathbf{p}=\sigma(\mathbf{W}^2\underbracket{\left(\sigma(\mathbf{W}^1 \mathbf{x}  + \boldsymbol{b}^1) \right)}_{\boldsymbol{\phi}(x)}   + \boldsymbol{b}^2)$$

![](../z_images/Pasted%20image%2020230614193952.png)

> [!info]
> In the hidden layer we use activation functions as the sigmoid(to output the probability) or ReLu(to set neuron to 0 or 1).
> 
> Nowadays we don't use sigmoid in the hidden layers.

---


