Suppose we have this function:

$$\Large f(x)=\frac{x^2+4x-12}{x^2-2x}$$

Notice that when $x = 2$, the function is not defined because we are dividing by zero.
We use a limit to understand what is going on around that point.

$$\Large \lim_{x\rightarrow 2}\frac{x^2+4x-12}{x^2-2x}$$

> [!hint]
> A limit is just syntax for "plugging" in the function values close to a certain point, to understand what the function looks like when it's approaching that point.
![](../z_images/Pasted%20image%2020250105153709.png)


The solution to a limit is what $y$ the function approaches as we get closer and closer to the point in question (in this case, x = 2).

### How to compute the solution

You can either do it:
- **empirically**: actually computing the numbers close to the point.
- **algebraically**: [factor](How%20to%20factor.md) numerator and denominator to **remove the division by zero**.

For example, if we factor the function above, we get:

$$\Large \lim_{x\rightarrow 2}\frac{(x+6)(x-2)}{x(x-2)}$$

Now we simplify through $(x-2)$:

$$\Large \lim_{x\rightarrow 2}\frac{(x+6)}{x}$$

This function is equivalent but no longer undefined at $x=2$, so we plug in the numbers and get the solution:

$$\Large \lim_{x\rightarrow 2}\frac{2+6}{2}=4$$

And that's exactly the number that $f(x)$ approaches at $x=2$.

![](../z_images/Pasted%20image%2020250105153709.png)

> [!faq] Why can't we also factor the original function and get rid of the undefined spot alltogether?
> Because when we do operations on a function, we need to ensure that it actually stays the same function.
> If we remove the undefined point, we need to add it as an "existence condition" alongside the new function.
> 
> We can do it with the limit because we don't actually care what happens at the exact point, just around it.

> [!example]
> ![](../z_images/Pasted%20image%2020250106192404.png)

> [!example]
> ![](../z_images/Pasted%20image%2020250106194325.png)


---

## Continuity and Discontinuity

### Continuity

A function is said continuous if at a point $x = a$  if:

$$\Large \lim_{x\rightarrow a}f(x)=f(a)$$

$f(x)$ exists at the point and the limits around the point (from left and from right) coincide.

$$\Large \Large \lim_{x\rightarrow a^-}f(x)=f(a)\qquad \Large \lim_{x\rightarrow a}f(x)=f(a) \qquad \Large \lim_{x\rightarrow a+}f(x)=f(a)$$

> [!hint]
> Meaning there is **no jump or interruption in the function**. No discontinuity point.


### Discontinuity points

Some functions are not defined at particular points. But there can be 3 cases:

![](../z_images/Pasted%20image%2020250222105250.png)


Sometimes limits go to infinity (asymptotes) or the left and right limit just aren't the same.
These are the precise cases:
- Left limit **=** Right limit: Hole
- Left limit **≠** Right limit: Jump
- A limit is **infinite**: One or two asymptotes


> [!note] Other hole case
> It can also happen that both limits and the function are defined, but the function is just at another point.
> ![](../z_images/Pasted%20image%2020250222110121.png)


### Limit existence

A limit is said to exist if Left limit **=** Right limit:

$$\Large \lim_{x\rightarrow a^+}f(x)=\lim_{x\rightarrow a^-}f(x) = L$$

$$\Large \lim_{x\rightarrow a}f(x)=L$$

The actual function doesn't need to be defined at that point for the limit to exist.

> [!example]
> ![](../z_images/Pasted%20image%2020250107111902.png)
> 1. Jump (limit doesn't exist and function is defined)
> 2. Continuous (limit exists and function is defined)
> 3. Hole (limit exists, function is defined but not equal to the limit)

> [!note] Intermediate Value Theorem
> ![](../z_images/Pasted%20image%2020250107112106.png)

---

## Infinities

> [!note]
> $$\large\frac{1}{\infty}\text{ approaches }0$$
> $$\large \frac{1}{0} \text{ approaches }\infty$$


### Division by zero

Consider the limit:

$$\Large \lim_{x\rightarrow0}\frac{1}{x}$$

If we directly plug in the value, we get a division by zero and we can't do anything about it.
But what about aroun that point?

$$\Large \lim_{x\rightarrow0^-}\frac{1}{x} = -\infty\qquad\lim_{x\rightarrow0^+}\frac{1}{x}=\infty$$

![](../z_images/Pasted%20image%2020250224095202.png)

> [!hint]
> From the left side ($\lim_{x \to 0^-} \frac{1}{x}$):
> $$\begin{align*}
> \text{When } x &= -0.1, \frac{1}{x} = -10 \\
> \text{When } x &= -0.001, \frac{1}{x} = -1000 \\
> \text{When } x &= -0.00001, \frac{1}{x} = -100000 \\
> \end{align*}$$
> 
> From the right side ($\lim_{x \to 0^+} \frac{1}{x}$):
>
> $$\begin{align*}
\text{When } x &= 0.1, \frac{1}{x} = 10 \\
\text{When } x &= 0.001, \frac{1}{x} = 1000 \\
\text{When } x &= 0.00001, \frac{1}{x} = 100000 \\
\end{align*}$$


### Polynomial growth

Consider the function:

$$\Large f(x)=x^2$$

The function grows arbitrarily large in both directions:

$$\Large\lim_{x\rightarrow\infty^-}x^2 = \infty \qquad \lim_{x\rightarrow\infty^+}x^2 = \infty$$

![](../z_images/Pasted%20image%2020250224101302.png)

---

## Order of infinities

Some function grow faster than others.
If we have two functions that go to infinity inside another function, we say that the function goes to the infinity that grows faster.

$$\Large \ln(x)<x^a<e^x<x!$$

### How to solve exercises

1. Always group/factor out the largest exponential (largest one in the whole function)

$$\Large \mathop {\lim }\limits_{t \to  - \infty } \frac{{{t^2} - 5t - 9}}{{2{t^4} + 3{t^3}}} = \mathop {\lim }\limits_{t \to  - \infty } \frac{{{t^4}\left( {\frac{1}{{{t^2}}} - \frac{5}{{{t^3}}} - \frac{9}{{{t^4}}}} \right)}}{{{t^4}\left( {2 + \frac{3}{t}} \right)}}$$

2. Use the fact that $\Large\frac{n}{\infty}$ goes to 0 to kill numbers.

$$\Large\mathop {\lim }\limits_{t \to  - \infty } \frac{{\frac{1}{{{t^2}}} - \frac{5}{{{t^3}}} - \frac{9}{{{t^4}}}}}{{2 + \frac{3}{t}}}\\ \Large = \lim_{t \to  - \infty} \frac{0 - 0 - 0}{2 + 0} = \frac{0}{2}$$

> [!example]
> $$\Large \lim_{z \to \infty} \frac{4z^2 + z^6}{1 - 5z^3}$$
> Try to simplify, because some factors might cancel out:
> $$\Large \lim_{z \to \infty} \frac{z^3 \left( \frac{4}{z} + z^3 \right)}{z^3 \left( \frac{1}{z^3} - 5 \right)}$$
> $$\Large \lim_{z \to \infty} \frac{ \frac{4}{z} + z^3}{\frac{1}{z^3} - 5}$$
> We are done simplifying, substitute the value of $z$:
> $$\Large \lim_{z \to \infty} \frac{ \frac{4}{\infty} + \infty}{\frac{1}{\infty} - 5}$$
> $\Large\frac{n}{\infty}$ goes to 0:
> $$\Large \lim_{z \to \infty} \frac{ 0 + \infty}{0 - 5}=\frac{\infty}{-5}=-\infty$$

> [!warning]
> More exercises are needed here.

---

## Properties

![](../z_images/Pasted%20image%2020250105155334.png)![](../z_images/Pasted%20image%2020250105155345.png)

## Some other facts

![](../z_images/Pasted%20image%2020250105155516.png)


For polynomials, we just need to evaluate the function at that point.

![](../z_images/Pasted%20image%2020250105155701.png)

> [!hint]
> Nice enough means that the limit from left and right are always equal and they are also equal to the limit evaluated at exactly that point.

---

## Teorema dei carabinieri

### WIP

![](../z_images/Pasted%20image%2020250106222021.png)
![](../z_images/Pasted%20image%2020250106222031.png)
https://tutorial.math.lamar.edu/Classes/CalcI/ComputingLimits.aspx

![](../z_images/Pasted%20image%2020250106222012.png)

---

## Limits with infinities

![](../z_images/Pasted%20image%2020250106222208.png)


Asymptote definition:
![](../z_images/Pasted%20image%2020250106222412.png)


![](../z_images/Pasted%20image%2020250107105300.png)

**When we take a limit at infinity for a polynomial all we need to really do is look at the term with the largest power and ask what that term is doing in the limit since the polynomial will have the same behavior.**


![](../z_images/Pasted%20image%2020250107105433.png)

---

> [!note] Math definition of the limit
> ![](../z_images/Pasted%20image%2020250107112409.png)
> 
> https://tutorial.math.lamar.edu/Classes/CalcI/DefnOfLimit.aspx
