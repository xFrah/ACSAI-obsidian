---
alias: Softmax, Argmax
---

We use multiple [[Perceptron|Binary Classifiers]] to divide the space into multiple [hyperplanes](../Linear%20Algebra/Hyperplanes.md) representing different classes.

![](../z_images/Pasted%20image%2020230611134416.png)
The points are assigned to the farthest hyperplane, because the bigger the [dot product](../Linear%20Algebra/Dot%20product.md) is, the more confident we are in that class.

$$\large\operatorname{sign}\big(\mathbf{w}^T\mathbf{x}_i + b\big) > 0$$

A point $\mathbf{x}$ belongs to class $k$ if 

$$\large \mathbf{w}^T_k\mathbf{x} + b_k  > \mathbf{w}^T_j\mathbf{x} + b_j \;\; \text{of every other class j}$$

> [!hint]
> It's as if we were using multiple [perceptrons](Perceptron.md) at once.

---

## Let's vectorize even more

For a single point we could do this to get the scores for all the classes:

$$\large\underbracket{\mathbf{y}}_{\mathbb{R}^{Kx1}} = \underbracket{\mathbf{W}}_{\mathbb{R}^{K\times d}}\underbracket{\mathbf{x}}_{\mathbb{R}^{d\times1}} + \underbracket{\mathbf{b}}_{\mathbb{R}^K}$$

For multiple points we can also do this:

$$\large\underbracket{\mathbf{Y}}_{\mathbb{R}^{Kxn}} = \underbracket{\mathbf{W}}_{\mathbb{R}^{K\times d}}\underbracket{\mathbf{X}}_{\mathbb{R}^{d\times n}} + \underbracket{\mathbf{b}}_{\mathbb{R}^K}$$

> [!hint]
> Each $\mathbf{W}_k$ works as a "prototype" of each class.
> We can interpret each row, $\mathbf{W}_k$ of $\mathbf{W}$ as a **template/prototype** for class $k$.
> 
> Below is the visualization of each learnt $\mathbf{W}_k$ for CIFAR-10:
> 
> ![](../z_images/Pasted%20image%2020230611204455.png)
> 
> This makes sense when you consider that each prediction is just the dot product of these prototypes and the datapoint. It just tells you how similar those are.
> 
> ![](../z_images/Pasted%20image%2020230611204724.png)


---

## How to train

> [!note] Argmax and Softmax
> 
> ### Argmax
> Argmax is a function that given a [vector](../Linear%20Algebra/Vectors.md) of numbers, returns the [index of the] highest element.
> $$\large[0.1, 0.2, 0.3] \quad\rightarrow\quad 2$$
> 
> ### Softmax
> Softmax is a mathematical function that converts a vector of numbers into a vector of probabilities, where the probabilities of each value are proportional to the relative scale of each value in the vector.
> 
> $$\large[0.1, 0.2, 0.3] \quad\rightarrow\quad [0.300, 0.332, 0.367]$$


Since this is multi-class classification, we use [cross-entropy](Cross-entropy.md) as the loss function.

> [!attention]
> As you may fucking remember, the loss functions contain both the prediction and the ground truth.
> If we want to compute the [gradient](Gradient.md) of the loss function and proceed with [gradient descent](Gradient%20Descent.md), we need the prediction function to be [differentiable](../Calculus/8.%20Differentiation.md)(we should be able to evaluate its derivative at any point).


In order to extract the prediction from the [matrix](../Linear%20Algebra/Matrix%20(ML).md) $\mathbf{Y}$, we can either use Argmax or Softmax.


### Argmax

If we use argmax to get the predicted class out of the output, for each point we just get the class index:

![](../z_images/Pasted%20image%2020230611183202.png)

BUT THIS SHIT AIN'T DIFFERENTIABLE(because of the steps), SO WE CAN'T COMPUTE THE GRADIENT OF THE LOSS FUNCTION. 
And the biggest problem is that even if it was differentiable, the gradients would be zero almost everywhere, so we wouldn't know where to go(during gradient descent).


### Softmax

On the other hand, if we use softmax, for every point we get another vector containing the probabilities of each class being the right class. AND IT IS DIFFERENTIABLE, so we can use it in the loss function.

![](../z_images/Pasted%20image%2020230611202656.png)

Above we can see the probability that the points belong to the third class.

---

## Softmax regression

Let's reiterate, now we extract the predictions with softmax function $\sigma$ as follows:

$$\large f_{\boldsymbol{\theta}}(\mathbf{x}) \doteq \boldsymbol{\sigma}\left(  \mathbf{W}\mathbf{X} + \mathbf{b} \right)$$
with $\sigma$ being the softmax function:

$$\large\boldsymbol{\sigma}_i(z)= \frac{e^{z_i}}{\sum_{k=1}^K e^{z_k}}$$

> [!hint]
> We model the probability of each class as:
> 
> $$\large\begin{cases}p(y=1\;|\; \mathbf{x};\mathbf{W},\mathbf{b}) = p_1 = \boldsymbol{\sigma}_1\left(  \mathbf{W}\mathbf{X} + \mathbf{b} \right)\\p(y=2\;|\; \mathbf{x};\mathbf{W},\mathbf{b}) = p_2 =  \boldsymbol{\sigma}_2\left(  \mathbf{W}\mathbf{X} + \mathbf{b} \right)\\\ldots \\p(y=K\;|\; \mathbf{x};\mathbf{W},\mathbf{b}) = p_K =  \boldsymbol{\sigma}_K\left(  \mathbf{W}\mathbf{X} + \mathbf{b} \right)\\\end{cases}$$
> 


Now we can compute the cross entropy, which we gotta minimize.

$$\large L(\mathcal{D}, W, \mathbf{b})=\frac{1}{|\mathcal{D}|} \sum_{(\mathbf{x}, y) \in \mathcal{D}} \underbracket{-\log \left(\frac{\exp({\mathbf{W}\mathbf{x}+\mathbf{b})}}{\sum_{k=1}^K\exp({\mathbf{W}_k\mathbf{x}+\mathbf{b}_k)}}\right)}_{\text {cross-entropy loss for }(\mathbf{x}, y)}$$


![](../z_images/Pasted%20image%2020230611204757.png)