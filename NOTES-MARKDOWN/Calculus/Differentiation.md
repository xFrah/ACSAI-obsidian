$$\Large f'\left( x \right) = \mathop {\lim }\limits_{h \to 0} \frac{{f\left( {x + h} \right) - f\left( x \right)}}{h}$$

This formula is like asking, how much is this function increasing from point $x$ to point $x+h$.
Where $x + h$ is a point that approaches $x$.

The result is a function that gives the slope of the original function at every point.

## Points of non differentiability

![](../z_images/Pasted%20image%2020250302100956.png)
> [!hint]
> - **Any discontinuity** in a function automatically creates a **point of non-differentiability**.
> - A function cannot possess a derivative at points **where it's not defined**.
> - The derivative is not defined when it yields $\infty$.

### Vertical Tangent

The derivative there is equal to $\infty$. Meaning the original function is completely vertical there.

![](../z_images/Pasted%20image%2020250302110114.png)

You can search for these by checking where the denominator of the derivative becomes 0.

### Discontinuity

Differentiability **requires** continuity.

> [!warning]
> A continuous function can be non-differentiable.
> > [!example]
> $\large f(x)= |x|$ is continuous, but it's still not differentiable.


### Cusp / Corner

The left-hand derivative and right-hand derivative of a point are not the same.

> [!example]
> ![](../z_images/Pasted%20image%2020250227154749.png)
> This function is continuous at $x=0$, because it **exists at every point** and the **limit from left and right** is the same.
> 
> But the derivative from left and right isn't the same, because at $x=0$ the slope changes abruptly.
> 
> In this case, the left hand derivative is $f'(x)=-1$ and the right one is $f'(x)=1$. This is called a sharp corner.

---

## Properties

The **derivative of a sum** is the **sum of the derivatives**:
![](../z_images/Pasted%20image%2020250103120948.png)

The **derivative of a scalar product** is the **scalar $\cdot$ derivative** of the function.
![](../z_images/Pasted%20image%2020250103121003.png)

**Product** rule:
![](../z_images/Pasted%20image%2020250103124725.png)

**Quotient** rule:
![](../z_images/Pasted%20image%2020250103124812.png)

## Formulas

> [!danger] Composite functions
> For example, you can't treat $e^{9(x-9)}$ as $e^x$.
> The first one is a composite function and needs to be evaluated through the chain rule.
 

The derivative of a **constant** is 0.
$$\Large d(c) \quad \Rightarrow \quad 0$$

**Power** rule:
$$\Large d(x^n)\quad \Rightarrow \quad nx^{n-1}$$

> [!hint]
> This is the reason why a variable with exponent 1 becomes 1.
> $$\large\dfrac{d}{dx} x^1 = 1\cdot x^{1-1} = x^0 = 1$$

Derivatives of **trigonometric functions**:
![](../z_images/Pasted%20image%2020250104165000.png)

![](../z_images/Pasted%20image%2020250104165949.png)

Derivatives of **exponentials**:
$$\Large d(e^x) \quad \Rightarrow \quad e^x$$
$$\Large d(a^x) \quad \Rightarrow \quad a^x\ln a$$

Derivatives of **logarithms**:

$$\Large d(\ln x)=\frac{1}{x}$$
$$\Large d(\log_a x)=\frac{1}{x\ln a}$$

> [!note]
> ![](../z_images/Pasted%20image%2020250104165839.png)


## Chain rule

We use this when we need to derive composite functions, meaning functions of functions.

$$\Large F'(x)=f'(g(x))\cdot g'(x)$$

> [!example]
> Consider:
> $$\Large f(x)=\sqrt{x-1}$$
> which can be turned into:
> $$\Large f(x)=(x-1)^{\frac{1}{2}}$$
> 
> Apply the chain rule:
> 
> $$\Large f'(x)=\underbracket{\frac{1}{2}\cdot\frac{1}{(x-1)^{\frac{1}{2}}}}_{\text{outer}}\cdot \underbracket{1}_{\text{inner}}$$
> 


---

> [!abstract] Links
> https://tutorial.math.lamar.edu/Classes/CalcI/DiffFormulas.aspx
