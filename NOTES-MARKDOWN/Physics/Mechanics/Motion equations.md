---
aliases:
  - Kinematics
  - kinematic
---
The goal is to find a trajectory arc and predict position, velocity and acceleration at time $t$.

## Position Functions and Displacement 

We begin with position functions in 3D space. An object's position at any time can be described by three functions: 
$$\large x(t), \quad y(t), \quad z(t)$$

> [!quote] Displacement definition and calculation
> $$\large\Delta x = x(t + \Delta t) - x(t)$$$$\large \Delta y = y(t + \Delta t) - y(t)$$$$\large\Delta z = z(t + \Delta t) - z(t)$$

> [!quote] Vector notation for position
> The position vector $\vec{r}$ represents the complete position of an object in space: 
> $$\Large \vec{\text{pos}}(t) = x(t)\cdot\hat{i} + y(t)\cdot\hat{j} + z(t)\cdot\hat{k}$$

## Velocity and Acceleration 

The velocity vector $\vec{v}$ is the [derivative](../../Calculus/8.%20Differentiation.md) of a position function $x(t)$ with respect to time:

$$\Large \vec{v(t)} = \frac{d\,\vec{\text{pos}}}{dt}$$
or:
$$\Large v=\frac{\Delta s}{t}$$

> [!hint]
> The speed is the magnitude of the velocity vector. 


The acceleration $\vec{a}$ is the [derivative](../../Calculus/8.%20Differentiation.md) of velocity: 

$$\Large \vec{a(t)}=\frac{d\vec{v}}{dt}=\frac{d^2\vec{r}}{d^2t}$$
or:
$$\Large a=\frac{\overbracket{\Delta v}^{v_f-v_i}}{t}$$

> [!example] Projectile Motion Example 
> Let's consider a simple case of projectile motion. We have an initial velocity in the y-direction: 
> $$\large\vec{v}_0=v_{0y}\cdot \hat{j}\;\left(\frac{m}{s}\right)$$
> The acceleration due to gravity acts downward: 
> $$\large\vec{a_y}(t)=-g\cdot \hat{j} \;\left(\frac{m}{s^2}\right)$$
> ### Finding Velocity Using Integration 
> 
> To find the velocity at any time, we integrate the acceleration: 
> $$\large v_y=v_{0y}+\int a_y(t) \; dt$$$$\large v_y=v_{0y}-gt$$
> ### Finding Position Using Integration 
> 
> Similarly, to find the position function, we integrate the velocity: $$\large y=y_0+\int v_y \; dt$$ $$\large y=y_0+\int (v_{0y}-gt) \; dt$$ $$\large y=y_0+v_{0y}t-\frac{1}{2}gt^2$$
> This final equation gives us the vertical position as a function of time, derived by integrating the velocity function. 


For projectile motion in a plane, assuming the initial position is at the origin: $$\Large \vec{r}(t) = (v_{0x}t)\hat{i} + (v_{0y}t - \frac{1}{2}gt^2)\hat{j}$$This vector function completely describes the trajectory of the projectile over time.

Touches ground when $y=0$
- $t=0$ is the starting point
- $v_{0y}=\frac{1}{2}gt\rightarrow t= \frac{2v_0s}{g??}$
