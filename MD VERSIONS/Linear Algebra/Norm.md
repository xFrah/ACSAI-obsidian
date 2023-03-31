The norm of a [[Vectors|vector]] tells us how big it is.
It's the magnitude of a vector.
Different norms encode different notions of size.

A norm is a function that maps a vector to a scalar and satisfies the following three properties:

- Given any vector x, if we scale all the elements of the vector by a scalar, its norm scales accordingly:
$$\Large|cx| = |c|\cdot |x|$$


- Non-negativity: 
					$\Large|x| \geq 0$ with equality if and only if $\Large x=0$.

- For any vectors x and y, norms satisfy the triangle inequality: 
$$\Large|x+y| \leq |x| + |y|$$


## Euclidean norm

There are many functions that compute valid norms.
Specifically, [numpy](../AI-LAB/Numpy.md)'s norm calculates the euclidean norm.

$$\Large|x|_2 = \sqrt{x_1^2 + x_2^2 + \cdots + x_n^2}$$

In other words, the Euclidean norm of a vector is the square root of the sum of the squares of its elements.

## Manhattan distance

The Manhattan distance is defined as:

$$\Large|x|_1 = |x_1| + |x_2| + \cdots + |x_n|$$

It is the sum of the absolute values of its elements.