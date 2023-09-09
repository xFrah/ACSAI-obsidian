![](../z_images/Pasted%20image%2020230809111207.png)

> [!tldr] Linear combination Notion
> Mathematically, if you have two vectors $\mathbf{v}$ and $\mathbf{w}$, a linear combination of these vectors can be expressed as:
> 
> $$\large a\mathbf{v}+b\mathbf{w}$$
> 
> where $a$ and $b$ are scalar values.

### 1) Linear combinations

In order to check whether a [linear combination](../Linear%20Algebra/Linear%20Combination.md) can result in a specific vector, we put the vectors as the column of a matrix and we solve the [systems of linear equations](../Linear%20Algebra/Systems%20of%20Linear%20Equations.md) that we have generated.

![](../../Pasted%20image%2020230909102536.png)


### 2) Linearity of transformation

In order for a transformation to be linear, it must satisfy 2 conditions.

$$\large T(x+y) \quad \text{and} \quad T(cu)=cT(u)$$
![](../../Pasted%20image%2020230909105318.png)


### 3) Linear dependency check

> [!note] Definition of $P_2(\mathbb{R})$
> $P_2(\mathbb{R})$ represents the vector space of all polynomials of degree 2 or less with real coefficients. The elements of $P_2(\mathbb{R})$ are polynomials of the form:
> 
> $$\large ax^2+bx+c$$
> 
> where $a$, $b$ and $c$ are real numbers.


 In order to check we can either look at the thing and see that they are not multiples of each other:

![](../../Pasted%20image%2020230909135006.png)


or we gotta solve the following equation for $c_1$ and $c_2$:

$$\large c_1​(1+x)+c_2​(−x^2+2)=0$$

> [!note] How to go from this to system of linear equations
> You expand the thing:
> 
> $$\large c_1 + c_1x + c_2(-x^2) + 2c_2=0$$
> 
> Then you group by their power of $x$.
> 
> $$\large \begin{cases}
\underbracket{c_1 + 2c_2}_{constants} = 0 \\
c_1 = 0 \\
c_2 = 0
\end{cases}$$


If the only solution is $c1_​=0$ and $c2​=0$, then the set $S$ is linearly independent. If there are other(non-zero) solutions for $c_1$​ and/or $c_2​$, then the set $S$ is linearly dependent.


### 4) Checking for subspaces

