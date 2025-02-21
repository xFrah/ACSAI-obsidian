We have two ways of solving inequalities:
- **Number line method** (testing for positivity): used when we have a **continuous function**.
- Using **systems** (looking for overlaps): used when we have a **piecewise function** (square root, modulus, etc...).

> [!hint] Why the system method?
> The goal is to get a system (or piecewise function) that **mirrors exactly the behaviour of our function**, so that we can process it better.

## Inequalities with absolute value

The argument of a modulus gets its sign flipped when it's negative, we can **represent it as a piecewise function**.

$$\Large|2x-3|>x+6$$

We have to **get rid of the absolute value**, so we translate this into a system.

$$
\Large\begin{array}{cc}
\underbracket{
\left\{
\begin{array}{ll}
2x - 3 \geq 7 \\
2x - 3 > x+6
\end{array}
\right.
}_{\text{argument is positive}}
&
\underbracket{
\left\{
\begin{array}{ll}
2x -3 < 0 \\
-2x +3 > x+6
\end{array}
\right.
}_{\text{argument is negative}}
\end{array}
$$

The modulus is a special case: 
- when the **argument is positive**, **nothing changes** (*first system*)
- when the **argument is negative**, its **sign gets flipped** (*second system*).

Then we solve the two systems.

> [!hint]
> $$\large \text{Inequalities} = \text{Intervals}$$
> The solution to a system of inequalities is the interval where all those intervals overlap.


$$
\Large\begin{array}{cc}
\left\{
\begin{array}{ll}
x \geq \frac{3}{2} \\
x > 9
\end{array}
\right.
&
\left\{
\begin{array}{ll}
x < \frac{3}{2} \\
x  < -1
\end{array}
\right.
\end{array}
$$

![](../z_images/Pasted%20image%2020250215140930.png)

Those are two different solutions/intervals:

$$\Large x>9 \qquad x< -1$$

And the final solution is written as:

$$\Large x>9 \quad \vee \quad x>9$$

> [!hint]
> All points that are in either one of these intervals.

> [!hint] Inequalities with 2 moduli
> When we have **two moduli**, like $|arg_0|$ and $|arg_1|$, we need to consider all combinations:
> 
> 1. $arg_0 ≥ 0$ and $arg_1 ≥ 0$
> 2. $arg_0 ≥ 0$ and $arg_1 < 0$
> 3. $arg_0 < 0$ and $arg_1 ≥ 0$
> 4. $arg_0 < 0$ and $arg_1 < 0$
> 
> For example, if we have $|2x - 1| < |x + 2|$, we would need to set up **four systems**:
> $$
> \large\begin{array}{cc}
> \underbrace{
> \left\{
> \begin{array}{ll}
> 2x - 1 \geq 0 \\
> x + 2 \geq 0 \\
> 2x - 1 < x + 2
> \end{array}
> \right.
> }_{System\ 1}
> &
> \underbrace{
> \left\{
> \begin{array}{ll}
> 2x - 1 \geq 0 \\
> x + 2 < 0 \\
> 2x - 1 < -(x + 2)
> \end{array}
> \right.
> }_{System\ 2}
> \\[2em]
> \underbrace{
> \left\{
> \begin{array}{ll}
> 2x - 1 < 0 \\
> x + 2 \geq 0 \\
> -(2x - 1) < x + 2
> \end{array}
> \right.
> }_{System\ 3}
> &
> \underbrace{
> \left\{
> \begin{array}{ll}
> 2x - 1 < 0 \\
> x + 2 < 0 \\
> -(2x - 1) < -(x + 2)
> \end{array}
> \right.
> }_{System\ 4}
> \end{array}
> $$
> 

---

## Inequalities with roots

A square root is defined only when the argument is positive and we can't convert it to a normal function, so we **represent it as a piecewise function**.

The goal here is to **get rid of the square root**, and we do that by squaring everything, but there are two procedures depending on the type of inequality.

> [!hint] Sign problem
> The two procedures differ because of a single problem, loss of sign when we square the right part.
> In one case we will **add an interval to the solution**, in the other we will **remove it**.


### $\sqrt{f(x)}> g(x)$

$$\Large \sqrt{x+3}>4$$

We have to **get rid of the square root**, so what we do is **square everything**.

$$\Large \begin{cases} x+3 > 4^2 \\ \dots \end{cases}$$

> [!hint]
> If we just square everything, then the square root limitation of **argument always > 0 isn't enforced anymore**, so we need to enforce it in the system.
> 
> Otherwise, this is **NOT** equal to a square root.

$$\Large \begin{cases} x+3 > 4^2 \\ x+3 \geq 0\end{cases}$$

The following is a representation of both intervals, with the blue one being where both intervals are defined:

![](../z_images/Pasted%20image%2020250220125502.png)

![](../z_images/Pasted%20image%2020250220132516.png)

##### But what if the right side is negative?

When we square a negative number, **we lose information on the sign**.
And that is important information, because it's a whole different **interval that we are not including**.

For example:
$$\Large \sqrt{x+3}>-4$$

This would yield the same exact system as before:
$$\Large \begin{cases} x+3 > 4^2 \\ x+3 \geq 0\end{cases}$$

But the square root is always greater than a negative number, so the green interval from before should be included too, how do we fix this?

We need to "manually" include the interval that we lost:

$$\Large \begin{cases} -4 <0 \\ x+3 \geq 0\end{cases}$$
So in this case:

$$
\Large\begin{array}{cc}
\left\{
\begin{array}{ll}
x+3 > 4^2 \\ x+3 \geq 0
\end{array}
\right.
&
\left\{
\begin{array}{ll}
-4<0 \\
x +3 \geq 0
\end{array}
\right.
\end{array}
$$

![](../z_images/Pasted%20image%2020250220131633.png)

![](../z_images/Pasted%20image%2020250220133158.png)

As you can see in the image, the solutions of these two systems combined give the result:

$$\Large x>-3$$

> [!hint]
> You can **just recognize that a square root can't be smaller than a negative number** and say that the interval is defined as long as the square root is defined (*argument is positive*) (*second system*).


### $\sqrt{f(x)}< g(x)$

$$\Large \sqrt{x+3}<4$$

As usual, we square both sides and we check that the square root exists:

$$\Large \begin{cases} x+3 < 4^2 \\ x+3 \geq 0\end{cases}$$
![](../z_images/Pasted%20image%2020250220134526.png)
And that's right in this case...

##### But what if the right side is negative?

$$\Large \sqrt{x+3}<-4$$
$$\Large \begin{cases} x+3 < 4^2 \\ x+3 \geq 0\end{cases}$$

As usual, we are losing information on the sign by squaring, but this time we need to remove an interval instead of adding it.
Without an additional condition, these would be the intervals:

![](../z_images/Pasted%20image%2020250220134526.png)

But here we need to remove the interval where the right side is negative at least, because **that is when we lose information**.

Here the interval we need to remove is $-4<0$:

$$\Large \begin{cases} x+3 < 4^2 \\ x+3 \geq 0\\-4>0\end{cases}$$
Which makes the system impossible in this specific instance.

> [!hint]
> If you look at the original inequality, you can already tell that it's impossible because a square root can never be negative.

> [!warning]
> ##### OBVIOUSLY
> In these examples the right part is always constant, but all these intuitions are for when the right part is a function.

> [!note] Non-even roots
> $$\Large x+2>=^3\sqrt{x+2}$$
> 
> The condition $\text{arg}\geq0$ is no more.
> We put both sides to the **power of 3** and **solve as a polynomial**.
> 
> $$\Large A>= \sqrt{B}^3 \quad <=> \quad A^3 >= (^3\sqrt{B})^3$$
> $$\large(x+2)^3 >= (x+2)$$
> $$\large(x+2)((x+2)^2-1)>=0$$
> $$\large(x+2)(x+3)(x+1)$$
> ![](../../z_images/Pasted%20image%2020241008090316.png)
> 
> $$\large x \in [-3, -2]\cup [-1, +\inf)$$
> 
> $a^3-b^3=(a-b)(a^2+ab+b^2) \qquad \forall a,b \in \mathbb{R}$
> ???


---

## Inequalities with polynomials

Here you need to [factor](How%20to%20factor.md) the polynomials to get the basic factors and then put them on the number line to study where the sign is positive.

$$\Large x^2-4x+4\geq0$$

We factor it:

$$\Large (x-2)(x-2)\geq 0$$

Then we put every factor into the number line and we compute the positivity:

![](../z_images/Pasted%20image%2020250221110721.png)

And the formal result is:

$$\Large x \in \mathbb{R}=(-\infty, +\infty)$$


---

## Fractional inequalities

$$\Large \frac{(x-1)(x^2-4x+4)}{x-3}>=0$$

When everything is polynomial, put numerator $\geq 0$ and denominator $>0$, then factor everything and add each factor to the number line:

$\large x-1 \geq 0 \quad \rightarrow \quad x\geq1$
$\large x^2-4x+4\geq0 \quad \rightarrow\quad x\geq 2 \quad\&\quad x\geq 2$
$\large x-3>0 \quad \rightarrow \quad x > 3$

Now we use the number line:

![](../z_images/Senza%20titolo-2.png)
$$\Large x \in \quad(-\infty,1] \lor \{2\}\lor(3,+\infty)$$


> [!hint] What are we actually doing?
> The original question is: **When is this function positive?**
> We find the answer by:
> - decomposing the function in **little sub-functions that multiply each other** (factors)
> $$\large \frac{\underbracket{f(x)}_{x-1}\cdot \underbracket{g(x)}_{x-2} \cdot \underbracket{h(x)}_{x-2}}{\underbracket{m(x)}_{x-3}}\geq 0$$
> - check where the little functions are positive and where they are negative
> - multiply their sign at each point to get the overall sign (at each point).
>   
> This works because the little functions always multiply each other at every point, and their signs get multiplied too, so when we have two negative factors it multiplies to positive.
> ![](../z_images/Senza%20titolo-1%203.png)
> 
> The two is included because the $\geq$ counts as a positive sign too (and negative otherwise).


> [!example]
> $$\large \frac{x-\sqrt{x+2}}{x^2-3x+2}>0$$
> $A=x-\sqrt{x+2}>=0$
> $B=x^2-3x+2>0 \quad \Rightarrow \quad (x-1)(x-2)$
> 
> $\large B>0$
> ![](../../z_images/Pasted%20image%2020241008091605.png)
> $B>0 \quad <=> \quad x \in (-\inf, 1)\cup(2,+\inf)$
> 
> $\large A>=0$
> 
> $x>=\sqrt{x+2}$ (right side is positive for sure, but left side we are not sure)
> 
> $\begin{cases} x+2>= 0 \\ x>= 0 \\ x^2>=(^2\sqrt{x+2})^2\end{cases} \quad \Rightarrow \quad \begin{cases} x\in [-2,+\infty) \\ x \in [0, +\infty) \\ x^2-x-2>=0\end{cases}$
> 
> $x=\frac{1+-\sqrt{1+8}}{2}=\frac{1+-3}{2} = -2 \quad \& \quad 1$
> $x^2-x-2=(x+1)(x-2)>=0 \quad <=> \quad x\in \underbracket{(-\infty, 1)}_{\text{not needed}}\cup[2, +\infty)$
> 
> $A>=0 \quad <=> \quad x\in[2, +\infty)$
> 
> $\large \frac{A}{B}>=0$
> ![](../../z_images/Pasted%20image%2020241008092926.png)
> 
> $\frac{A}{B}>=0 \quad <=> \quad x \in (1, 2) \cup (2, +\infty)$
> 
> > [!hint]
> In 
> $$\large a^2-b^2=\underbracket{(a+b)}_{>=0}(a-b)$$
> $(a+b)$ is always positive, so we don't take it into account while computing the sign.

