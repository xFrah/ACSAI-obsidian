We can use the linear [[Multi-Class Classification|soft-max regression]] to represent a single layer of a neural network.


## The single layer

$$\large\underbracket{\mathbf{z}}_{\mathbb{R}^{Kx1}} = \underbracket{\mathbf{W}}_{\mathbb{R}^{K\times d}}\underbracket{\mathbf{x}}_{\mathbb{R}^{d\times1}} + \underbracket{\mathbf{b}}_{\mathbb{R}^K}$$
Each row of the [matrix](../Linear%20Algebra/Matrix.md) W contains the parameters of the [hyperplane](../Linear%20Algebra/Hyperplanes.md) of one class.
In other words, each row of W is an output neuron k, which in this case is also connected with the weight of class k.

> [!hint]
> $$\large\mathbf{W} \mathbf{x}=\left(\begin{array}{c}-\text { neuron - } \\\vdots \\-\text { neuron }-\end{array}\right)\left(\begin{array}{c}\mid \\\mathbf{x} \\\mid\end{array}\right)$$

![](../z_images/Pasted%20image%2020230612015828.png)

---

## The firing of a neuron

With...
$$\large \boldsymbol{\sigma}\left(  \mathbf{W}_k^T\mathbf{x} + \mathbf{b}_k \right)$$
... we can represent the firing of a single neuron/class k:

![](../z_images/Pasted%20image%2020230612021128.png)