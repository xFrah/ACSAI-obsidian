We can approximate a function $f(x)$ by constructing a specific polynomial that mimics certain characteristics of $f(x)$.

The polynomial will have the form:

$$\Large P(x)=c_0 + c_1x + c_2x^2 + c_2x^3 + \dots + c_nc^n$$

The principle is to mimic how the derivatives of different orders behave at a specific point.

> [!example]
> At $\large x = 0$ and for 4 degrees of freedom(?).
> $$\Large f(x) = P(x)$$
> $$\Large f'(x) = P'(x)$$
> $$\Large f''(x) = P''(x)$$
> $$\Large f'''(x) = P'''(x)$$


By doing so, around that point the polynomial $P(x)$ will approximate $f(x)$.

> [!hint]
> More degrees of freedom(?) = better approximation.


## How does it work

The key idea, is that **each coefficient controls one order of derivation**.

Let's start from scratch:
We want to approximate $f(x)$ at around $x=0$ and we want to use 3 coefficients:

$$\Large P(x)=c_0 + c_1x + c_2x^2$$

> [!hint] How does each coefficient control exactly one derivative of the polynomial? Don't they interfere with each other?
>  When you derive to a specific order, the terms and coefficients that don't correspond to that order must/will disappear.
> 
> This is possible because when you derive to an order $n$:
> - the terms with exponent $<n$ will automatically disappear, so they don't interfere with the remaining coefficient.
> - the terms with exponent $> n$ will disappear too, because we selected 0 as our point ($c\cdot 0^{>n}=0$)
> 
> So for every order of derivative, only one coefficient (the one that has no $x$) will fix the output.
> 
> > [!example]
> >  $$\Large P(x)=1+ 0x-\frac{1}{2}x^2+0x^3+\frac{1}{24}x^4$$
> >  
> > For the first coefficient/normal function:
> > 
> > $$\Large P(x)=1-\frac{1}{2}x^2+\frac{1}{24}x^4$$
> > $$\Large P(0)=1-0+0= 1$$
> > 
> > For the second derivative (first one is 0):
> > 
> > $$\Large P''(x)=\frac{1}{2}{2}+ \frac{1}{24} 2x$$
> > $$\Large P''(0)=\frac{1}{2}2+ 0= 1$$
> > 
> > For the fourth derivative (third one is 0):
> > 
> > $$\Large P''''(x)=\frac{1}{24}\cdot \underbracket{24}_{1\cdot2\cdot3\cdot4}= 1$$
> > 
> > In this case, we approximated $\cos (0)$, and the derivatives were meant to be:
> > $$\large \cos(0) = 1, \quad \cos'(0)=0, \quad \cos''(0)=-1, \quad \cos'''(0)=0, \quad \cos''''(0)=1$$
> > 
> > So this is correct.

---

## How to solve exercises

![](../z_images/Pasted%20image%2020250328082321.png)

Little-o notation means a function that grows strictly slower than the argument.
In this case, it can equal to whatever grows slower than $x^2$. 
It can be a little counter-intuitive, so just do this instead:

$$\Large \text{if}\qquad\lim_{x\rightarrow 0}\frac{x^3}{x^2}=0 \qquad\text{then}\qquad x^3=o(x^2)$$

