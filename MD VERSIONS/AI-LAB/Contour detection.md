There are some well known kernels that allow to extract only the edges from the image.
The most famous are the Sobel and Laplacian kernels.

The sobel operator is a [kernel](Kernel.md) that computes the first derivative of pixels intensity.

![](../z_images/Pasted%20image%2020230321171341.png)


Basically, there are some points/edges in the image, where the pixel intensities change quickly.
That is basically how we detect edges. 

In an edge, the pixel value changes noticeably. and the derivative is the best way tp measure the change in a function.

An edge is simply a jump in pixel intensity:

![](../z_images/Pasted%20image%2020230321171530.png)

If we take the first derivative we can identify the flex:

![](../z_images/Pasted%20image%2020230321171605.png)

---

## Sobel

We can use the Sobel operator to compute that peak, it works as follows($I$ = image portion around pixel):

1. We compute the horizontal changes(by disabling vertical direction):

$$\large G_x=\begin{bmatrix}
-1 & 0 & +1 \\
-2 & 0 & +2 \\
-1 & 0 & +1
\end{bmatrix}*I$$

2. We compute vertical changes(by disabling horizontal direction):

$$\large G_y=\begin{bmatrix}
-1 & -2 & -1 \\
0 & 0 & 0 \\
+1 & +2 & +1
\end{bmatrix}*I$$

3. We compute an approximation of the [gradient](../Machine%20Learning/Gradient.md) in that point by combining both results above is computed:
$$\large G=\sqrt{G^{2}_x + G^{2}_y}$$
or just
$$\large G = |G_x|+|G_y|$$


```ad-tldr
When using the sobel operator, we take the product of the kernel elements and the corresponding pixels, and we add them all together. This is just normal convolution.

<br>

So if the result is very positive or very negative we have detected an edge, because the sides of the convolution are too different.

<br>

If the two sides have mostly the same values, the result is close to zero.

<br>

We can also interpret this as a discrete derivative.
```


```ad-tip
The operator * stands for "cross product", whichi is not really a cross product, we are just multiplying the elements in the same position and we are summing them. In this way we get a scalar.
```

