We want to regress a $y$ from $x$, starting from a finite number of datapoints:

![](../z_images/Pasted%20image%2020230519120711.png)


So we want to learn a function $f_0$ such that $f_{\boldsymbol{\theta}}: \underbracket{x}_{\text{input}} \mapsto \underbracket{y}_{\text{output}}$, with unknown parameters ${\boldsymbol{\theta}}\doteq (\theta_0,\ldots,\theta_d)$.

---

## Linear Hypothesis

We assume that the function $f_0$ we are searching for, is linear.

$$\large f_{\boldsymbol{\theta}}(x) = \theta_0+ \theta_1\cdot x_1 + \theta_2\cdot x_2 + \ldots + \theta_d\cdot x_d$$

or

$$\large f_{\boldsymbol{\theta}}(x) = \big(\sum_{i=1}^d\theta_i\cdot x_i\big) + \theta_0$$

> [!hint]
> The number of parameters is equal to the number of dimensions, in this case 2.

---

## Loss/Cost function

$$\large\mathcal{J}(\theta;x,y)= \frac{1}{2} \sum_{i=1}^{n}\mathcal{L}\big(y_{i}, f_{\boldsymbol{\theta}}(x_i)\big)$$
where the loss is **the squared error:**

$$\large \mathcal{L}\big(y, f_{\boldsymbol{\theta}}(x)\big) = \big(f_{\boldsymbol{\theta}}(x) - y \big)^2$$

## Vectorization of loss function

We define the **design [matrix](../Linear%20Algebra/Matrix.md)** $X$, **label matrix** $y$ and the parameters as:

$$\large\def\horzbar{\rule[.5ex]{2.5ex}{0.5pt}}
X =
\left[
  \begin{array}{ccc}
    \horzbar & x^{T}_{1} & \horzbar \\
    \horzbar & x^{T}_{2} & \horzbar \\
             & \vdots    &          \\
    \horzbar & x^{T}_{n} & \horzbar
  \end{array}
\right]
\; \qquad
y =
\left[
  \begin{array}{c}
    {y}_{1} \\
    {y}_{2} \\
    \vdots \\
    {y}_{n} \\
  \end{array}
\right]
\; \qquad
\theta =
\left[
  \begin{array}{c}
    \theta_{0} \\
    \theta_{1} \\
    \vdots \\
    \theta_{d} \\
  \end{array}
\right]$$

> [!hint]
> $x_{i}^{T}$ is a vector(a datapoint in d+1 dimensions), that is transposed to fit in a row of the matrix.

> [!example] Design matrix example
> If we measure the height and weight of five individuals, we can collect the measurements in a design matrix having five rows and two columns.
> $$\large X=\begin{bmatrix}
> h_1 & w_1 \\
> h_2 & w_2 \\
> h_3 & w_3 \\
> h_4 & w_4 \\
> h_5 & w_5 \\
> \end{bmatrix}$$

Given this new vectorization, we can rewrite the cost function as:

$$\large\mathcal{J}(\theta;x,y)= \frac{1}{2} \sum_{i=1}^{n}  (\underbracket{\theta^Tx_i}_{f_{\boldsymbol{\theta}}} - y_i)^2=\frac{1}{2} \big(X\theta - y \big)^T\big(X\theta - y \big)$$

> [!hint] Formula Explanation
> $\theta^T x_i$ is the [dot product](../Linear%20Algebra/Dot%20product.md) between datapoint and parameters.
> 
> $$\large y=\begin{bmatrix}
> q & m
> \end{bmatrix} 
> \begin{bmatrix}
> x_0\rightarrow 1 \\
> x_1
> \end{bmatrix}=qx_0 + mx_1
> $$
> 
> The datapoint gets transformed by parameters like in a function, this can be also seen as the prediction.
> 
> $$\large\theta^T x_i=f(x_i)=\hat{y}$$
> 
> Given that, while remembering that the rows of X are the actual datapoints in transposed vector form:
> $$\large X\theta - y =
> 
> \begin{bmatrix}
> x_{1}^{T} \\
> x_{2}^{T} \\
> \vdots    \\
> x_{n}^{T} \\
> \end{bmatrix}
> \cdot
> \begin{bmatrix}
> \theta_{1} \\
> \theta_{2} \\
> \vdots    \\
> \theta_{n} \\
> \end{bmatrix}
> -
> \begin{bmatrix}
> y_{1} \\
> y_{2} \\
> \vdots    \\
> y_{n} \\
> \end{bmatrix}
> =
> \left[
>  \begin{array}{ccc}
>    & x^{T}_{1}\theta - y_1 &  \\
>     & x^{T}_{2}\theta - y_2 &  \\
>             & \vdots    &          \\
>     & x^{T}_{n}\theta - y_n & 
>  \end{array}
>\right]$$
>
>If we take the dot product between $(X\theta - y)$ and $(X\theta - y)^T$, we are basically taking every row(error for each datapoint) and we are squaring it.
>
>$$\frac{1}{2} \big(X\theta - y \big)^T\big(X\theta - y \big)= \frac{1}{2}
>
> \left[
>  \begin{array}{ccc}
>    x^{T}_{1}\theta - y_1 & x^{T}_{2}\theta - y_2 & \dots & x^{T}_{n}\theta - y_n
>  \end{array}
>\right]
>
> \left[
>  \begin{array}{ccc}
>    & x^{T}_{1}\theta - y_1 &  \\
>     & x^{T}_{2}\theta - y_2 &  \\
>             & \vdots    &          \\
>     & x^{T}_{n}\theta - y_n & 
>  \end{array}
>\right]
> $$





