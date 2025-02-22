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
- **algebraically**: factor numerator and denominator to **remove the division by zero**.

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

> [!abstract] Limit existence
> A limit is said to exist if Left limit **=** Right limit:
> 
> $$\Large \lim_{x\rightarrow a^+}f(x)=\lim_{x\rightarrow a^-}f(x) = L$$
> 
> $$\Large \lim_{x\rightarrow a}f(x)=L$$

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
