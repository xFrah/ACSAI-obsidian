Assume we have a function:

$$\Large f(x,y)=\frac{xy}{x^2+y^2}$$

which graphs like this:

![[Pasted image 20251004113928.png]]


You can see both in the formula and in the graph, that $(0,0)$ is undefined.
But does its limit exist?

> [!note]
> - A limit in single-variable functions exists when both left and right limits yield the same result.
> - A limit in multi-variable functions exists when all the possible paths yield the same limit.


Since we can't actually check all the possible paths, we need to find two paths that yield different result and prove that the limit doesn't exist.

Lines are usually the easiest path to check first, we set $y=x$:

$$\Large f(x,y)=\frac{x^2}{x^2+x^2}=\frac{1}{2}$$

![[Pasted image 20251004120657.png]]


Then we check another path, we choose a crossing line for simplicity, $y=-x$:

$$\Large f(x,y)=\frac{-x^2}{x^2+x^2}=-\frac{1}{2}$$

We can see that two different paths yield a different limit, so the limit doesn't exist at $(0, 0)$.

> [!hint] What if the line we choose doesn't approach the point we want to test?
> Well then its useless lol. Think about it this way. the first variable acts like a traversal of the space and the second variable is the function that determines the path.
> 
> Like a normal 2-D function.
> 
> It needs to pass through the point we want to test.
