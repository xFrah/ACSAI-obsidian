Imagine we take the derivative of a function like this:

![](../z_images/Pasted%20image%2020230522120629.png)

> [!note] Remember
> The derivative is a function that returns the rate of change at a point in the curve.

> [!hint]
> Single vs Multiple Dimensions:
> - If your function has a single dimension, you just gotta choose at which $x$ we want to compute our slope.
> - If we have multiple dimensions, once you choose your $x$, you also have to choose your $y$.


If we input all the arguments($x$ and $y$), we get the slope at a certain 3D point of the curve *(total derivative)*.
Sometimes tho, we don't want points, we want functions that describe the rate of change in an individual dimension of the 3d curve *(partial derivatives)*.

In the example above, if we fix $y=0$ and let $x$ move freely, we get this function:

![](../z_images/Pasted%20image%2020230522121259.png)

This function is the partial derivative of the curve if we derive on $x$.

---

## Notation

A partial derivative of $f(x, y)$ where we fix our $y$ and let $x$ move freely, can be written as:

$$\large \frac{\partial f}{\partial x}$$

Where:
- $\partial$ means partial derivative specifically.
- $f$ is the multivariate function we want to derive.
- $x$ is the variable that can still move freely.

---

## How to compute

Every variable that is not the variable we using gets turned into a constant.
So if we want to take the derivative of...

$$\large f(x,y) = y^3x^2$$

... with respect to $x$, we treat $y$ as a constant $c$ and use the usual derivation rules.

$$\large\begin{align*}\frac{\partial f}{\partial x}(x) = 2c^3x.\end{align*}$$

---

