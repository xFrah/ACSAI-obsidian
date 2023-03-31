In image processing functions are usually called kernels. A kernel is nothing more than a (square) array of pixels. Usually, the values in the kernel add up to one.
A Kernel tells you how to change the value of any given pixel by combining it with different amounts of the neighboring pixels.
Ex:
$$\large \begin{bmatrix}
1 & 1 & 1\\
1 & 1 & 1\\
1 & 1 & 1
\end{bmatrix}$$

This is a blurring kernel: for every pixel, it's combining equally the values of the neighboring pixels with the value of the pixel itself.


## Using the kernels

The operator * stands for "cross product", whichi is not really a cross product, we are just multiplying the elements in the same position and we are summing them. In this way we get a scalar.


## Gaussian blur

A Gaussian kernel is a square array of pixels where the pixel values correspond to the values of a Gaussian curve (in 2D).

![](../z_images/Pasted%20image%2020230321165721.png)

When each pixel of the image gets multiplied by the gaussian kernel, the image becomes blurred.
You can choose the size of the gaussian kernel to select the amount of blur(the bigger it is, the more neighboring pixels it uses).