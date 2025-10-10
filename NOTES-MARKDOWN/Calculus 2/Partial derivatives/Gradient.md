---
aliases:
  - gradient
  - gradients
---
The gradient of a function is a vector containing the [[Partial derivatives]] of said function:

$$\Large ∇f(x,y) = 
\begin{bmatrix}
f_x'(x,y)\\ 
f_y'(x,y)
\end{bmatrix}$$

> [!example]
> ![[Pasted image 20251005162531.png]]

---

## Useful for machine learning

If you input a point $(x_0, y_0, ...)$ in the input space of $f$, the vector $\nabla f(x_0, y_0, ...)$ tells you which direction you should travel to increase/decrease the value of $f$ most rapidly:

$$\large\nabla f(x_0, y_0, ...)=\begin{bmatrix}
\LARGE\frac{\partial f}{\partial x} \large(x_0, y_0, ...)\\
\LARGE\frac{\partial f}{\partial y} \large(x_0, y_0, ...)\\
\Large\vdots
\end{bmatrix}$$
