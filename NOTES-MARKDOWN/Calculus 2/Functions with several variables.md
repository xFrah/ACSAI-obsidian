# $f: \mathbb{R}^n \rightarrow \mathbb{R}$
## Domain and range/codomain

A function $f: \mathbb{R}^n \rightarrow \mathbb{R}$ with $n$ variables, has a subset of $\mathbb{R}^n$ as domain and a subset of $\mathbb{R}$ as codomain.

## Derivative

The derivative remains the same, but we will need to take partial derivatives with respect to each single variable.


# $f: \mathbb{R} \rightarrow \mathbb{R}^n$

> [!example]
> $z = x^2 + y^2$ makes a 3D paraboloid.
> 
> ![](../../z_images/Pasted%20image%2020240927102839.png)


- Curves
- Ling integrals
- Double and triple integrals
- Vector fields
- Surfaces

> [!note] Scalar function?

> [!example]
> $$\large f(x, y) = \sqrt{1-x^2-y^2}$$
> The domain is $1-x^2-y^2>= 0$
> Which leads to $x^2+y^2<=1$, which is a circle. So the domain in this case are all the values inside the circle.
> ![](../../z_images/Pasted%20image%2020240927103602.png)


1. **Interior point**: A point $(x_0, y_0)$ belongs to the domain ($\Omega$) and is an interior point if and only if there exists an $R > 0$ such that:

$$\large {(x, y) : (x-x_0)^2 + (y-y_0)^2 < R^2} \subset \Omega$$

This means that there is an open disk centered at $(x_0, y_0)$ with radius $R$ that is entirely contained within the domain $\Omega$.

2. **Boundary point**: A point $(x_0, y_0)$ belongs to the domain ($\Omega$) and is a boundary point if and only if for every $R > 0$:

$$\large {(x-x_0)^2 + (y-y_0)^2 < R^2} \cap \Omega \neq \emptyset$$ and $$\large{(x-x_0)^2 + (y-y_0)^2 < R^2} \cap (\mathbb{R}^2 \setminus \Omega) \neq \emptyset$$
> [!danger]
> This is completely reconstructed, it is probably inaccurate.


> [!example]
>$$\large f(x)=\sqrt{x^2-y}$$
>### Domain
>
>$x^2-y>=0$, or $y <=x^2$
>![](../../z_images/Pasted%20image%2020240927105153.png)


> [!danger]
>Recap on how to compute domains of everything is needed.



> [!example]
> $$\large f(x,y) = \frac{1}{\log(x+y)}$$
> ### Domain
> - $\large x+y>0$
> - $\large\log(x+y) \neq 0 \quad\Rightarrow\quad x + y \neq 1$

> [!example]
> $$\large f(x)= \sqrt{x^2-y}$$
> 
> ### Domain
> - $\large x^2+ y>= 0 \quad \Rightarrow \quad y<= x^2$
> - $\large 1-x^2-y^2>=0 \quad \Rightarrow \quad x^2 + y^2 <=1$
>   
>   ![](../../z_images/Pasted%20image%2020240927112947.png)

> [!example]
> $$\large f(x)= \sqrt{x-\sqrt{1-2x^2-2y^2}}$$
> 
> ### Domain
> - $\large 1-2x^2-2y^2>=0 \quad \Rightarrow \quad x^2+y^2<=\frac{1}{2}$ (circle centered at 0,0 with radius $\sqrt{\frac{1}{2}}$)
> - $\large x-\sqrt{1-2x^2-2y^2}>= 0 \quad \Rightarrow \quad \sqrt{1-2x^2-2y^2}<=x$
>   - $\large 1-2x^2>= 0$
>   - $\large x>= 0$
>   - $\large 1-2x^2-2y^2 <= x^2 \quad \Rightarrow \quad 3x^2+2y^2>=1$ (ellipse)
>     
>  ![](../../z_images/Pasted%20image%2020240927115053.png)

> [!danger]
> You cannot just square both sides of an inequality LOL

> [!example]
> $$\large f(x, y) = \log(x\log(x-y))$$
> 
> ### Domain
> $\large\begin{cases}
> x\log(x-y)>0 \\
> x - y>0 \quad \Rightarrow \quad y<x \end{cases}$
>   
> For the first one:
>   - $\large x>0$
>   - $\large \log(x-y)>0$
> or
> - $\large x<0$
> - $\large \log(x-y)<0$
>  
>   ![](../../z_images/Pasted%20image%2020240927120243.png)
>   Manca un'immagine
>   ![](../../z_images/Pasted%20image%2020240927120343.png)


## Limits for function of two variables

Limit exists when both left limit and right limit exist. So if from different directions the limit approaches the same value.

> [!example]
> $$\large \lim_{(x,y)\rightarrow (0,0)}\frac{xy}{x^2+y^2} = \frac{0}{0}$$
> 
> $\large y=0 \quad \Rightarrow \quad \lim_{x\rightarrow0}f(x)= \lim_{x\rightarrow0}\frac{0}{2}=0$
> $\large x=0 \quad \Rightarrow \quad \lim_{y\rightarrow0}f(y)=\lim_{x\rightarrow0}\frac{0}{y^2}$
> wip
> 
> $y=mx$ (the easiest thing to try)
> $\large \lim_{x\rightarrow0}\frac{x(mx)}{x^2+(mx)^2}=\lim_{x\rightarrow0}\frac{m}{(m^2 + 1)} = \frac{m}{m^2 + 1}$
> 
> The limit does not exist, since it depends on the particular direction we are considering.
> 
