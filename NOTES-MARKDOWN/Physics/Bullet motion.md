![](../z_images/Immagine%20WhatsApp%202024-03-04%20ore%2009.16.46_cac8eb0e.jpg)

First we break down the initial velocity into its horizontal and vertical components:
$$\large v_{x0} = v_0 \cdot \cos(\alpha)$$

$$\large v_{y0} = v_0 \cdot \sin(\alpha)$$

We know that the acceleration in the horizontal component is 0, it is a constant velocity. Meanwhile in the vertical component we have an acceleration of $-g$:
$$\large a_x = 0,\quad y = -g$$

### Kinematic equations for projectile motion

#### Horizontal motion
The rate of change of horizontal position is constant (it changes $\large v_{x0}$ $\;x$ every $t$):
$$\large\frac{dx}{dt} = v_{x0}$$

The velocity of horizontal position doesn't change, which means it's constant.
AKA the rate of change of the rate of change of the horizontal position doesn't change and it's 0:
$$\large\frac{dv_x}{dt} = 0$$

The actual formula for x axis:
$$\large x(t) = x_0 + v_{x0} t$$

#### Vertical motion
The vertical position changes $v_{y0}$ space units every $t$ plus the gravitational pull.
The rate of change of vertical position is not constant because the gravitational pull gets bigger over time:
$$\large\frac{dy}{dt} = v_{y0} - g t$$

The rate of change of vertical position also changes because of acceleartion, it changes $-g$ every $t$:
$$\large\frac{dv_y}{dt} = -g$$

The actual formula for $y$ axis:
$$\large y(t) = y_0 + v_{y0} t - \frac{1}{2} g t^2$$

## Trajectory equation

![](../z_images/Immagine%20WhatsApp%202024-03-04%20ore%2009.24.35_58d72c74.jpg)

The following equation tells us at $y$ the object is at position $x$ (time is no more).
$$\large y - y_0 = x \tan(\theta) - \frac{g}{2v_0^2 \cos^2(\theta)} (x - x_0)^2$$

> [!info] How does one derive this?
> Horizontal motion equation
$$\large x(t) = x_0 + v_{x0}t$$
>
> Vertical motion equation
$$\large y(t) = y_0 + v_{y0}t - \frac{1}{2}gt^2$$
>
> Solving the horizontal motion equation for time $t$
$$\large t = \frac{x - x_0}{v_{x0}}$$
>
>Substituting $t$ into the vertical motion equation
$$\large y = y_0 + v_{y0} \left( \frac{x - x_0}{v_{x0}} \right) - \frac{1}{2}g\left( \frac{x - x_0}{v_{x0}} \right)^2$$
>
> Expanding and simplifying the equation
$$\large y = y_0 + \frac{v_{y0}}{v_{x0}}(x - x_0) - \frac{1}{2}g\frac{(x - x_0)^2}{v_{x0}^2}$$
>
> Substituting $v_{y0}$ and $v_{x0}$ with $v_0 sin(\alpha)$ and $v_0 cos(\alpha)$
$$\large y = y_0 + \tan(\alpha)(x - x_0) - \frac{1}{2}g\frac{(x - x_0)^2}{(v_0 \cos(\alpha))^2}$$


## Horizontal reach

![](../z_images/Immagine%20WhatsApp%202024-03-04%20ore%2009.30.33_4b89e48d.jpg)

## Maximum height

![](../z_images/Immagine%20WhatsApp%202024-03-04%20ore%2009.35.22_f4726dd5.jpg)


> [!example] Exercise
> ![](../z_images/Immagine%20WhatsApp%202024-03-04%20ore%2010.05.58_7492ee1c.jpg)
> ![](../z_images/Immagine%20WhatsApp%202024-03-04%20ore%2010.19.34_e137f933.jpg)

> [!example] Exercise
> ![](../z_images/Immagine%20WhatsApp%202024-03-04%20ore%2010.24.31_ace8d80e.jpg)
