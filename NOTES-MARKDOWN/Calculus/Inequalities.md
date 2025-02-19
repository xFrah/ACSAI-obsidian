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

The goal here is to get rid of the square root, but there are two procedures depending on the type of inequality:

### $\sqrt{f(x)}> g(x)$

$$\Large \sqrt{x+3}>4$$

We have to **get rid of the square root**, so what we do is **square everything**.

$$\Large \begin{cases} x+3 > 4^2 \\ \dots \end{cases}$$

> [!hint]
> If we just square everything, then the square root limitation of **argument always > 0 isn't enforced anymore**, so we need to enforce it in the system.
> 
> Otherwise, this is **NOT** the same equation.

$$\Large \begin{cases} x+3 > 4^2 \\ x+3 \geq 0\end{cases}$$

> [!hint]
> Also consider that if the right side is negative, then we can skip everything because it's always defined when $\text{arg}\geq0$.

### $\sqrt{f(x)}< g(x)$


> [!warning]
> ##### What happens when the right side is negative(**the inequality isn't defined**), but we don't know because we squared it?
> When the positivity of the right side isn't apparent(ie. *it's a function*), we need to enforce its positivity through a condition in the system:
> 
> $$\large \begin{cases} (\sqrt{\text{arg}})^2 \geq \text{right side}^2 \\ \text{arg} \geq 0 \\ \underbracket{\text{right side} > 0}_{\text{new condition}}\end{cases}$$
> 
> If we don't do this, we lose information on the sign, because the squared version doesn't include it.
> 
> This is to ensure that we don't include more intervals than we should. Without this condition, we would be saying that a negative number is greater than 


---

> [!example]
> $$\large \frac{(x-1)(x^2-4x+4)}{x-3}>=0$$
> 
> $x-1 >= 0 \quad <=> \quad x>=1 \quad <=> \quad x\in [1,+\inf)$
> $x^2-4x+4>=0 \quad <=> \quad x \in \mathbb{R}=(-\inf, +\inf)$ (equal to $(a+b)^2$? which is always positive.
> $x-3>0 \quad <=> \quad x > 3 \quad <=> \quad x \in (3, +\inf)$
> 
> ![](../../z_images/20241008_084917%201.jpg)

> [!example]
> $$\large x+2>=^3\sqrt{x+2}$$
> 
> $A>= \sqrt{B}^3 \quad <=> \quad A^3 >= (^3\sqrt{B})^3$
> $(x+2)^3 >= (x+2)$ (the original inequality is equal to this one)
> $(x+2)((x+2)^2-1)>=0$
> $(x+2)(x+3)(x+1)$
> ![](../../z_images/Pasted%20image%2020241008090316.png)
> 
> $$\large x \in [-3, -2]\cup [-1, +\inf)$$
> 
> $a^3-b^3=(a-b)(a^2+ab+b^2) \qquad \forall a,b \in \mathbb{R}$
> ???

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

