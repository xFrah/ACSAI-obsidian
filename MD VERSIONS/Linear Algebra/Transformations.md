---
alias: Rotation, Translation, Rotations, Translations, Scale, Flip, Affine
---

## Isometries/Orthogonal matrix: Rotations and Translations

If we want to rotate, we can add one single scalar. We can do that by using this transformation [matrix](Matrix%20(ML).md), and justby using a single number we can rotate.

$$\huge\begin{bmatrix}
\cos{\theta} & -\sin{\theta} \\
\sin{\theta} & \cos{\theta}
\end{bmatrix}
$$

<span style="background:rgba(183, 152, 255, 0.3)">This preserves angles and distances.</span>

![](../z_images/Pasted%20image%2020230307165614.png)

```ad-hint
title: Why?
Of course you remember that each column of the transform where the unit [vectors](Vectors.md) are gonna land.
Then, with $\large\begin{bmatrix} \cos{\theta}\\ \sin{\theta} \end{bmatrix}$, will make $\large \hat{j}$ land on $\large\begin{bmatrix} 1\\ 0 \end{bmatrix}$ when $\large\theta = 0$. Then it will continue rotating left with higher angles.

For $\large\hat{i}$ it's the same thing, the only difference is that it is at a different position in the unit circle.
In fact, when $\large\theta = 0$, $\large\begin{bmatrix} -\sin{\theta}\\ \cos{\theta} \end{bmatrix} = \large\begin{bmatrix} 0\\ 1 \end{bmatrix}$, which is exactly the basic $\large\hat{i}$.
```

```ad-info
If you transpose an orthogonal matrix(rotation), you get its inverse matrix, which is the exact rotation but backwards.

So with $AA^T$, nothing changes.

> ![](../z_images/Pasted%20image%2020230311130642.png)
```

---

## Similarity: Scale, Flip, Rotation and Translations

Now we add a scaling factor to the two axes.

$$\huge\begin{bmatrix}
S_x\cos{\theta} & -\sin{\theta} \\
\sin{\theta} & S_y\cos{\theta}
\end{bmatrix}
$$

Preserve angles and ratio between distances.


```ad-hint
title: Why the S coefficients?
Because as you remember, the unit vectors have two components, $\large x$ and $\large y$.
The main component of $\large \hat{i}$ is $\large x$ and the main component of $\large \hat{j}$ is $\large y$.

Here we are just scaling the main components of the two vectors.
```


![](../z_images/Pasted%20image%2020230307171444.png)

---

## Affine: 

We add $C_x$ and $C_y$ to the axes that were previously 0.

$$\huge\left[\begin{array}{cc}s_x\cos\theta ~~~ -c_x\sin\theta \\c_y\sin\theta ~~~ s_y\cos\theta\end{array} \right]$$

Preserve preserve parallelism but not angles.

```ad-hint
title: Why the C coefficients?
There are two ways to shear:
- By rotating one vector and keeping the other the same:
	![](../z_images/Pasted%20image%2020230307181604.png)
- Rotate both the vectors and extend only one of them.

Since in this case we have only 1 angle, we are using the second way. The shear can only happen if we rotate the vectors, since if the secondary component is 0 in both of the basis vectors, unless it is rotated.

So, here, the C coefficients serve the purpose of scaling the secondary component of the unit vectors, which is rotated.
```

![](../z_images/Pasted%20image%2020230307174837.png)
