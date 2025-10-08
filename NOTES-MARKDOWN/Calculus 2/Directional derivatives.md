Partial derivatives represent the rate of change of $f$ as we vary $x$ (holding $y$ fixed) and as we vary $y$ (holding $x$ fixed) respectively. 
We now need to discuss how to find the rate of change of $f$ if we allow both $x$ and $y$ to change simultaneously (in another new direction that isn't an axis).

![[Pasted image 20251008113749.png]]

We define the unit vector representing the direction as:

$$\large \vec{u}=\begin{bmatrix}
a\\b
\end{bmatrix}$$

We define the function that we want to get the derivative of as:

$$\large g( h ) = f( {{x_0} + ah,{y_0} + bh})$$
where:
- $(x_0, y_0)$ are the starting point.
- $(a, b)$ are the direction vector components
- $h$ is how far along the direction we are going

> [!hint]
> Everything is a fixed number, except for $h$. We can actually derive this.

---

## Formula using the gradient

You can also use the gradient to compute a directional derivative.
Assume we have this gradient and direction vector $\vec{u}$:

$$\Large ∇f=\begin{bmatrix}
2x\\2y
\end{bmatrix}\qquad\vec{u}=\begin{bmatrix}
2\\1
\end{bmatrix}$$

> [!warning]
> We use $\vec{u}=\begin{bmatrix}2\\1\end{bmatrix}$ just for simplicity, but in real calculations, we need it to be normalized to have magnitude 1.


Then we take the dot product between the gradient and the vector, and we get the actual directional derivative.

$$\Large f'_u=∇f\cdot\vec{u}=2x\cdot 2+2y\cdot 1$$
