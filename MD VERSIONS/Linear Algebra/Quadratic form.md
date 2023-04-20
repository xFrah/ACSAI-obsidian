Let's say you have this kind of expression:
$$\large ax^2 + bxy + cy^2$$
This thing's name is quadratic form, it just means that all the things that are inside of it are quadratic.

We want to express this in a vectorized matter.


## A first, simple example

We begin our journey by looking at a simple example.
Imagine we want to vectorize the expression:
$$\large ax+by+cz$$
We can do it like this:
$$\large\begin{bmatrix}
a \\ b \\ c
\end{bmatrix}\cdot
\begin{bmatrix}
x \\ y \\ z
\end{bmatrix}$$
If we take the [dot product](Dot%20product.md) between the vector of coefficients and the vector of variables, we get the original expression.

The notation for this expression is $\large V\cdot X$.


```ad-hint
Recall that the [dot product](Dot%20product.md) between two [vectors](Vectors.md) is basically multiplying the elements with same index and summing all of the results together.
```


## Now, for the quadratic form

The classic notation will become too complex with too many dimensions so we want a simpler way to write it.

```ad-info
In the formula:
$$\large ax^2 + bxy + cy^2$$

<br>

Usually, instead of $b\cdot xy$ we would think of it as $2b\cdot xy$, it is more convenient in this way because?
```

The correct way to express a quadratic form with a [matrix](Matrix.md) is to:
1. Take a 2x2 matrix:
$$\Large \begin{bmatrix}
a & b \\
b & c
\end{bmatrix}$$

Where $a$ and $c$ are on the diagonal, and $b$ is on the other diagonal.
This is always a [symmetric matrix](Symmetric%20matrix.md).

2. We multiply the vector of variables $\large \begin{bmatrix}x\\ y\end{bmatrix}$:

$$\Large \begin{bmatrix}
a & b \\
b & c
\end{bmatrix}\begin{bmatrix}x\\ y\end{bmatrix}$$

The result is a vector:

$\large x\begin{bmatrix}a\\ b\end{bmatrix} + y\begin{bmatrix}b\\ c\end{bmatrix}=\begin{bmatrix}ax\\ bx\end{bmatrix} + \begin{bmatrix}by\\ cy\end{bmatrix}=\begin{bmatrix}ax + by \\ bx + cy\end{bmatrix}$


3. We multiply the transposed vector of variables $\large \begin{bmatrix}x\\ y\end{bmatrix}$:

$$\Large 
\begin{bmatrix}
x & y
\end{bmatrix}
\begin{bmatrix}
a & b \\
b & c
\end{bmatrix}
\begin{bmatrix} 
x\\ y
\end{bmatrix}$$

The result is a scalar/expression:

$\large \begin{bmatrix}x & y\end{bmatrix}\begin{bmatrix}ax + by \\ bx + cy\end{bmatrix}=$

$\large = ax + by\begin{bmatrix}x\end{bmatrix} + bx+cy\begin{bmatrix}y\end{bmatrix}$

$\large =\begin{bmatrix}ax^2+bxy\end{bmatrix}+\begin{bmatrix}bxy+cy^2\end{bmatrix}$

$\large =\begin{bmatrix}ax^2 + bxy + bxy + cy^2\end{bmatrix}$

$\large = ax^2 + 2bxy + cy^2$


4. Profit

We just got back the whole original expression, but now we can express it in a much simpler way:

$$\Large x^tAx$$

Where:
- $\large x$ is the vector of variables
- $A$ is the matrix of coefficients


## Vector to scalar

It is a vector to scalar function.
It is used for characterizing Definiteness of matrices.

Because for any x != 0, the definiteness of the quadratic form can give you information about the eigenvalues.

![](../z_images/Pasted%20image%2020230321143357.png)

