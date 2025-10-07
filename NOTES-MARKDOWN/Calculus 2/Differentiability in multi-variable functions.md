A function $f(x,y)$ is differentiable at a point $(x_0,y_0)$ if it can be **well-approximated by its tangent plane** near that point.

$$\large \lim_{(h,k)\to(0,0)} \frac{f(x_0 + h, y_0 + k) - f(x_0, y_0) - f_x(x_0, y_0)h - f_y(x_0, y_0)k}{\sqrt{h^2 + k^2}} = 0
$$

Where:
- $f(x_0+h,y_0+k)$ is the actual function value at a nearby point
- $f(x_0,y_0)+f_x(x_0,y_0)h+f_y(x_0,y_0)k$ is the **tangent plane approximation** (using partial derivatives)
- The numerator measures the **error** between the actual function and its linear approximation
- The denominator $\sqrt{h^2+k^2}$ measures the **distance** from $(x_0,y_0)$

> [!hint] Understanding the formula
> - First term: the true $z$ near $(x_0, y_0)$ (distant $\sqrt{h^2 + k^2}$).
> - Second term: the $z$ resulting from the plane fitted using partial derivatives of the real functions, near $(x_0, y_0)$ (distant $\sqrt{h^2 + k^2}$).
> 
> By **subtracting them in the numerator, they give an error**, which represents how close the plane given the partial derivatives is to the real function, at a generic point near $(x_0,y_0)$.
> The **denominator represents the euclidean distance** from $(x_0, y_0)$. 
> Basically if the error decreases faster than the distance between $(x_0, y_0)$ and $(x_0+h,y_0+k)$, then the function is differentiable.
> 
> $$\large \lim_{(h,k)\to(0,0)} \frac{z_{\text{real}} - z_{\text{plane}}}{\sqrt{h^2 + k^2}} = 0$$
> 
> ![[Pasted image 20251007181808.png]]


> [!hint]
> The limit equals 0 if the error shrinks faster than the distance, meaning the tangent plane is a genuinely good approximation.
