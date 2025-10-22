## Double Integrals

![[Pasted image 20251017121700.png]]


We do the innermost integral first, and then the outer one, while treating every variable except one as constants.

$$\Large\int_c^d \int_a^b f(x, y) \, dx \, dy$$
1. We integrate $\int_a^b f(x, y) \, dx$ while treating $y$ as a constant.
2. Then we integrate the result with respect to y.

> [!danger] **IMPORTANT**
> Order of integration does NOT matter.

---

## Integrals between boundaries of a region 
### Region bounded by functions 

For non-rectangular regions, we use **functions** as integration limits instead of constants. 
**Type I region** (vertical slices): 
$$\Large D = \{(x,y) \in \mathbb{R}^2 : a \leq x \leq b, \, \alpha(x) \leq y \leq \beta(x)\}$$ The integral becomes: $$\Large\iint_D f(x,y) \, dA = \int_a^b \int_{\alpha(x)}^{\beta(x)} f(x,y) \, dy \, dx$$ Where: 
- $a$ and $b$ are **constant** bounds for $x$ 
- $\alpha(x)$ is the **lower boundary** (function of $x$) 
- $\beta(x)$ is the **upper boundary** (function of $x$) 

**How to read this:** 
1. For each fixed value of $x$ between $a$ and $b$ 
2. Integrate $f(x,y)$ with respect to $y$ from the bottom curve $\alpha(x)$ to the top curve $\beta(x)$ 
3. Then integrate that result over all $x$ from $a$ to $b$

--- 
## Polar Coordinates 

For **circular or annular regions**, polar coordinates simplify the integral dramatically. 
**Conversion formulas:** 
- $x = r\cos\theta$ 
- $y = r\sin\theta$ 
- $x^2 + y^2 = r^2$ 

> [!danger] **CRITICAL** 
> When converting to polar coordinates: $dx \, dy = r \, dr \, d\theta$ 
> Don't forget the extra $r$ factor! 
> **General form:** $$\Large\iint_D f(x,y) \, dx\,dy = \int_{\theta_1}^{\theta_2} \int_{r_1}^{r_2} f(r\cos\theta, r\sin\theta) \cdot r \, dr\,d\theta$$ 
> 

> [!example] Quarter annulus problem
> 
> $$\Large\iint_{\Omega} xy \, dx\,dy\quad\Omega = \{(x,y) : 1 \leq x^2 + y^2 \leq 4, x \geq 0, y \geq 0\}$$
> **Step 1:** Identify the region 
> - Annulus (ring) between circles of radius 1 and 2 
> - First quadrant only 
>   
> **Step 2:** Set up bounds in polar coordinates 
> - $1 \leq r \leq 2$ (from $1 \leq r^2 \leq 4$) 
> - $0 \leq \theta \leq \frac{\pi}{2}$ (first quadrant) 
>   
> **Step 3:** Convert the integrand $$xy = (r\cos\theta)(r\sin\theta) = r^2\cos\theta\sin\theta$$ **Step 4:** Set up the integral (don't forget the $r$ from $dA$!) $$\iint_{\Omega} xy \, dx\,dy = \int_0^{\pi/2} \int_1^2 r^2\cos\theta\sin\theta \cdot r \, dr\,d\theta = \int_0^{\pi/2} \int_1^2 r^3\cos\theta\sin\theta \, dr\,d\theta$$ 
> 
> **Step 5:** Separate variables and integrate $$= \left(\int_1^2 r^3 \, dr\right) \left(\int_0^{\pi/2} \cos\theta\sin\theta \, d\theta\right)$$ $$= \left[\frac{r^4}{4}\right]_1^2 \cdot \left[\frac{\sin^2\theta}{2}\right]_0^{\pi/2} = \frac{15}{4} \cdot \frac{1}{2} = \frac{15}{8}$$
