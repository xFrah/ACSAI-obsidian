With rectangular [matrix](Matrix.md) we can actually erase dimensions.

Example:

$$\Large\begin{bmatrix}
3 & -2 & 1 \\
2 & 1 & -1
\end{bmatrix}\begin{bmatrix}
1 \\
2 \\
3
\end{bmatrix}=\begin{bmatrix}
2 \\
1
\end{bmatrix}$$

We can see that one dimension gets erased, here's the math:

$\Large1\begin{bmatrix}3\\2\end{bmatrix}+2\begin{bmatrix}-2\\1\end{bmatrix}+3\begin{bmatrix}1\\-1\end{bmatrix}=\Large\begin{bmatrix}3\\2\end{bmatrix}+\Large\begin{bmatrix}-4\\2\end{bmatrix}+\begin{bmatrix}3\\-3\end{bmatrix}$

$\Large=\begin{bmatrix}3 -4 + 3\\2+2-3\end{bmatrix}=\begin{bmatrix}2\\1\end{bmatrix}$

Mathematically, you can see that it makes perfect sense.

```ad-hint
We are basically just scaling the new unit [vectors](Vectors.md) by the scalars of the vector.
```

```ad-important
We can also see that the scalar for the third unit vector still influences the rest of the plane.

The main component of the third unit vector is not there anymore, which means that the dimension is flat but the rest of the components still influence the other dimensions.

It should be equivalent to:
$$\Large\begin{bmatrix}
3 & -2 & 1 \\
2 & 1 & -1 \\
0 & 0 & 0
\end{bmatrix}$$
```


## Dimension eraser

Here is a rectangular matrix that just kills one dimension and doesn't change or scale anything else:
$$\Large\begin{bmatrix}
1 & 0 & 0 \\
0 & 1 & 0
\end{bmatrix}$$
Here the main components of the unit vectors are all still 1, but not the third one.

It should be the equivalent of:
$$\Large\begin{bmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 0
\end{bmatrix}$$