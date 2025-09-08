Motion in 2D, initial velocity $v_0$.

$$\Large \vec{v}_0=v_{0x}\hat{i}+v_{0y}\hat{j}$$
$$V_{0x}= V_0 \cos \theta$$

$$V_{0y}=V_0\sin\theta$$

$$ax=0$$
$$ay=-g$$

$$\frac{dV_x}{dt}= 0, \quad V_x=const=V_{0x}$$
$$\frac{dV_y}{dt}= -g, \quad V_y=V_{0y}-gt$$

$$\frac{dx(t)}{dt}, \quad x(t)=x_0+V_{0x}t$$
$$\frac{y(t)}{dt}, \quad y(t)=y_0 + v_{0y}-\frac{g}{2}t^2$$
$$V_y(t)=v_0\sin\theta - gt$$

> [!example] Homework
> $$v_y^2 = (v_0\sin\theta)^2-2g(y(t)-y_0)$$


$$x(t)-x = (v_0\cos\theta)\quad \rightarrow \quad t=\frac{x(t)-x_0}{v_0\cos\theta}$$
$$y(t)-y_0 = (v_0 \sin \theta)t-\frac{1}{2}gt^2$$

$$y(t)-y_0=(x(t)-x_0)\tan\theta - \frac{g}{2}\frac{(x(t)-x_0)^2}{(v_0\cos\theta)^2}$$

$$y=ax + bx^2 \quad \rightarrow\quad \text{from this we know that this is a parabola}$$


### Horizontal reach

$$x-x_0 = R = V_0 \cos\theta t_R$$
$$y-y_0 = 0 = (v_0\sin\theta)t_R - \frac{1}{2}g\cdot t^2_R$$
$$R=\frac{2v_0^2}{g}\sin\theta\cos\theta$$
$$R = \frac{v_0^2}{g}\sin(2\theta)\rightarrow \theta = 45\degree$$
45 degrees is the most efficient angle to throw farther.

> [!example]
> We have a particle that's free falling.
> Then we have another particle in coincidence, shot horizontally with $v = v_{0x}$
> Which one falls first? The answer is that they fall at the same time.
> 
> Produce some formulas to prove it I guess.


### Max height

At max height, $v_y(t_m)=0 \quad \rightarrow \quad v_0\sin\theta-gt_m=0$, and $t_m = \frac{v_0\sin\theta}{g}$.

$$y(t_m)=y_0+v_0\sin\theta t_m-\frac{1}{2}gt^2_m$$
$$h_\text{max}=\frac{(v_0\sin\theta)^2}{g} - -\frac{1}{2}\frac{v_0^2\sin^2\theta}{2g}$$

$$h_{max} = \frac{v_0^2}{g}\frac{\sin^2\theta}{2}$$
