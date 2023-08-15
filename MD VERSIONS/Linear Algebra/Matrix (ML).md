---
alias: Matrices, Matrix
---

We shouldn't think of it as a list of scalars.

$$\huge\begin{bmatrix} m_{11} & ... & m_{13} \\ ... & m_{22} & ... \\ m_{31} & ... & m_{33} \end{bmatrix}$$

## Interpretation:
- n column [[Vectors|vectors]] in a real-valued M-dimensional space.
- m row vectors in a real-valued N-dimensional space.
- Transformations, each column are new basis vectors.

---

## Identity/Diagonal Matrix:

$$\huge\begin{bmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{bmatrix}
$$

---

## Symmetrical matrix:

A matrix is simmetrical if:

$$\Large A = A^T$$

1.  $(A^T)^T = A$: The transpose of a transpose matrix is the original matrix.
    
2.  $(A+B)^T = A^T + B^T$: The transpose of the sum of two matrices is equal to the sum of their transposes.
    
3.  $(AB)^T = B^T A^T$: The transpose of a product of two matrices is equal to the product of their transposes in reverse order.

---

## Reduction operations (sum across rows)
Rows will disappear.

```
print(A, end='\n\n') # Possible to do reduction on the matrix (sum along rows) 
A_c = A.sum(axis=0, keepdims=False) # 3 (rows are canceled out) 
A_c.shape print(A_c)
```
Output:

```
[[0 1 2]
[3 4 5]
[6 7 8]]

[ 9 12 15]
```

You flatten the axes, so you get something that is 1x3. You flatten the rows.
The axis where you do the operation is said to be flattened.

```ad-warning
title: Exam question
How do we translate a point cloud to the origin?

We compute the mean of the point cloud and then we subtract it from all the point.
The new mean of the point cloud is 0.

```

```ad-tip
title: Hamaard multiplication
We do multiplications element wise. In python, it is done by the operator "*", between matrices.
```

---

## Matrices as linear map between spaces/Linear transformations

They actually map a space into another space. Or an input vector to an output vector.

We are gonna take the basis vectors, and we are gonna change them. Then the operation can be done for every other point/vector.

It's basically just a change of basis vectors.

We are given the vector: $$\Large\begin{bmatrix}5\\7\end{bmatrix}$$
we can also represent it as a [linear combination](Linear%20Combination.md) of scaled basis vectors:

$$\Large5\hat{i}+7\hat{j}$$

Now, the whole point of a linear transformation is to change the basis vectors, so we do:

$$\Large\hat{i} = \begin{bmatrix}3\\-2\end{bmatrix},\quad \hat{i}=\begin{bmatrix}2\\1\end{bmatrix}$$

The result is:
$$\Large5\begin{bmatrix}3\\-2\end{bmatrix}+7\begin{bmatrix}2\\1\end{bmatrix}=\begin{bmatrix}15\\-10\end{bmatrix}+\begin{bmatrix}14\\7\end{bmatrix}$$

The linear combination of our scaled new basis vectors is then our transformed vector:

$$\Large\begin{bmatrix}15\\-10\end{bmatrix}+\begin{bmatrix}14\\7\end{bmatrix}=\begin{bmatrix}15 + 14\\-10 + 7\end{bmatrix}=\begin{bmatrix}29\\-3\end{bmatrix}$$

This transformation can be represented as a matrix:
$$\Large A=\begin{bmatrix}3 & 2 \\ -2 & 1 \end{bmatrix}$$
Each column of the matrix is a new basis vector.


```ad-tip
title: Alternative writing
Often, other people collapse the last part into a single vector whose elements are yet to be calculated.
![](../z_images/Pasted%20image%2020230304142913.png)
```


### Visual examples:

![](../z_images/Pasted%20image%2020230304142327.png)

![](../z_images/Pasted%20image%2020230304142416.png)

Sometimes they can induce severe distortion when the two vectors lie in the same direction.

---

## Matrix multiplication

Now that we have established matrices as transformations, we can merge two matrices/transformations into just 1 matrix, that is called a composition of matrices.

![](../z_images/Pasted%20image%2020230304154959.png)


Basically, it goes from right to left, so in this case we first apply rotation and then shear.
When we apply rotation, we have that:
$$\Large\hat{j} = \begin{bmatrix}0\\1\end{bmatrix}, \quad \hat{i} =\begin{bmatrix}-1\\0\end{bmatrix}$$
Now assume j and i are vectors on a basic cartesian plane, with normal basis vectors.
We now transform the basis vectors of the new j and i, to see where they land, and that will be our final combination.
$$\Large\begin{bmatrix}1 & 1 \\ 0 & 1 \end{bmatrix}\begin{bmatrix}0\\1\end{bmatrix}, \quad \begin{bmatrix}1 & 1 \\ 0 & 1 \end{bmatrix}\begin{bmatrix}-1\\0\end{bmatrix}$$

Basically, we must substitute the basis vectors of the new j and i with the columns of the shear:

$\Large\begin{bmatrix}1 & 1 \\ 0 & 1 \end{bmatrix}\begin{bmatrix}0\\1\end{bmatrix}=0\begin{bmatrix}1\\0\end{bmatrix}+1\begin{bmatrix}1\\1\end{bmatrix}=\begin{bmatrix}1\\1\end{bmatrix}=\hat{j}$


$\Large\begin{bmatrix}1 & 1 \\ 0 & 1 \end{bmatrix}\begin{bmatrix}-1\\0\end{bmatrix}=-1\begin{bmatrix}1\\0\end{bmatrix}+0\begin{bmatrix}1\\1\end{bmatrix}=\begin{bmatrix}-1\\0\end{bmatrix}=\hat{i}$

The result is the matrix:
$$\Large\begin{bmatrix}1 & -1 \\ 1 & 0 \end{bmatrix}$$
Which is exactly the same as the composition in the image above.

---

## [Determinant](Determinant.md)

The [determinant](Determinant.md) of a matrix/transformation is the factor by which any area is scaled by the transformation.

![](../z_images/Pasted%20image%2020230305161956.png)

The determinant also allows for negative values.
Negative values happen when the space is "flipped", for example when the unit vectors cross each other.

A determinant of 0 is means that dimensions have collapsed into a single one, so for example a volume has been squished into a plane or an area has been squished into a single line.

This is what happens when the vectors/column of the matrix are not linearly indipendent.

---

## Rectangular matrices

With rectangular matrices we can actually erase dimensions.

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


### Dimension eraser

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