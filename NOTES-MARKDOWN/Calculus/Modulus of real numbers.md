Definition:
$$\large |x|= \begin{cases}x, \;\text{if}\;x>=0\\-x,\;\text{if}\;x<0\end{cases}$$

Other stuff
$$\large\sqrt{x^2}=|x|\quad\forall x\in\mathbb{R}$$
$$\large(\sqrt{x})^2 =x \quad \forall x >=0$$

## Distance definition using modulus

$$\large d(x_1, x_2) := |x_2-x_1| \quad \forall x \in \mathbb{R}$$
Properties of this distance:
- Positivity: $d(x_1, x_2)>=0 \quad \forall x_1, x_2 \in \mathbb{R}$ and $d(x_1, x_2) = 0 <=> x_1=x_2$
- Symmetry: $d(x_1, x_2)=d(x_2, x_1) \quad \forall x_1, x_2 \in \mathbb{R}$
- Triangle inequality: $d(x_1, x_3) <= d(x_1, x_2) + d(x_2, x_3) \quad \forall x_1,x_2,x_3 \in \mathbb{R}$


> [!example]
> $$\large |x-1|<1$$
> $\begin{cases}x-1>=0\\ x-1<0\end{cases} \cup \begin{cases}x-1<0\\ -(x-1)<1\end{cases}$
> $\begin{cases}x>=1\\ x<2 \end{cases}\cup \ \begin{cases}x<1\\ x>0\end{cases}$
> $x\in [1, 2) \cup (0, 1)=(0,2)$
> ![](../z_images/Pasted%20image%2020241009093343.png)
> 
> > [!hint]
> > Modulus is present only at the beginning, once we apply the definition we don't have it anymore.
> 
> > [!hint]
> > The solution to this is the set of points that have distance to 1 smaller than 1, geometrically speaking.
> > 
> > $$\large\{d(x,1)<1\}$$

> [!example]
> $$\large -|x|+x-1<-3x^2$$
> $\begin{cases}x>=0\\ -x-1<-3x^2\end{cases}\cup\begin{cases}x<0\\ x+x-1<-3x^2\end{cases}$
> 
> $3x^2-1<0 \qquad \& \qquad x=\frac{-2+-\sqrt{4-4(3)(-1)}}{6}$
> 
> $\begin{cases}x>=0\\ x\in(-\frac{\sqrt{3}}{3}, \frac{\sqrt{3}}{3})\end{cases}\cup \begin{cases}x<0\\ x\in (-1, \frac{1}{3})\end{cases}$
> 
> $x\in [0, \frac{\sqrt{3}}{3}\cup(-1, 0)=(-1, \frac{\sqrt{3}}{3})$
