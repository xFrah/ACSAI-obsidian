Let $A$ be a square [matrix](Matrices.md), if there exists a square matrix $B$ such that...

$$\large AB=BA=I$$

... then we say that $A$ is invertible and $B$ is the inverse of $A$($A^{-1} = B$).

> [!note]
> A matrix that doesn't have an inverse is called singular or non-invertible.

---

## Finding the inverse of a Matrix

The [Gauss-Jordan elimination](Gaussian%20Elimination.md) method can be used to find the inverse of a matrix. Here's a step-by-step process:

1. **Augment the Matrix with the Identity Matrix.**

2. **Apply Row Operations to Reach RREF:** Use the Gauss-Jordan elimination method to transform the given matrix into the reduced row echelon form (RREF). **The goal is to transform the left side of the augmented matrix into the identity matrix.**

> [!hint]
>    Use elementary row operations, including swapping rows, multiplying a row by a nonzero scalar, and adding/subtracting a multiple of one row from another row.


3. **Extract the Inverse:** Once the left side of the augmented matrix is the identity matrix, the right side will be the inverse of the original matrix.


> [!warning]
> Note that this method only works for square matrices that are invertible. 
> If the given matrix is not invertible (i.e., it has no inverse), the process will reveal this fact by leading to a row of zeros or inconsistencies in the augmented matrix.
> 
> ![](../z_images/Pasted%20image%2020230809124506.png)

> [!example]
> Suppose we want to find the inverse of the following matrix:
> 
> $$\large A = \begin{bmatrix} 2 & 1 \\ 1 & 1 \end{bmatrix}$$
> 
> 1. **Augment with the Identity Matrix:**
> 
>    $$\large \begin{bmatrix} 2 & 1 & | & 1 & 0 \\ 1 & 1 & | & 0 & 1 \end{bmatrix}$$
> 
> 2. **Row Operations:**
>    - Multiply the first row by $\large\frac{1}{2}$:
>      $$\large\begin{bmatrix} 1 & \frac{1}{2} & | & \frac{1}{2} & 0 \\ 1 & 1 & | & 0 & 1 \end{bmatrix}$$
>    - Subtract the first row from the second row:
>      $$\large \begin{bmatrix} 1 & \frac{1}{2} & | & \frac{1}{2} & 0 \\ 0 & \frac{1}{2} & | & -\frac{1}{2} & 1 \end{bmatrix}$$
>    - Multiply the second row by 2:
>      $$\large \begin{bmatrix} 1 & \frac{1}{2} & | & \frac{1}{2} & 0 \\ 0 & 1 & | & -1 & 2 \end{bmatrix}$$
>    - Subtract $\large\frac{1}{2}$ times the second row from the first row:
>      $$\large \begin{bmatrix} 1 & 0 & | & 1 & -1 \\ 0 & 1 & | & -1 & 2 \end{bmatrix}$$
> 
> 3. **Extract the Inverse:**
>    The inverse of $A$ is:
> 
>    $$\large A^{-1} = \begin{bmatrix} 1 & -1 \\ -1 & 2 \end{bmatrix}$$

---

## Properties of Inverse Matrices

![](../z_images/Pasted%20image%2020230810113050.png)

**Existence of the Inverse:**
The inverse of a matrix $A$ exists if and only if $A$ is square and has a non-zero [determinant](Determinant.md).

> [!hint]
> A non-zero determinant indicates that the matrix represents a transformation that doesn't "collapse" space; hence, it can be reversed.


**Transposition of an Inverse:**
If $A$ is invertible, then $(A^T)^{-1} = (A^{-1})^T$.

> [!hint]
> Transposing a matrix and finding its inverse are reversible operations, so the order in which you perform them doesn't matter.


**Inverse of a Scalar Multiple:**
If $A$ is invertible and $k$ is a nonzero scalar, then $(kA)^{-1} = \frac{1}{k}A^{-1}$.

> [!hint]
> Scaling a matrix by a factor  $k$ scales its inverse by  $\frac{1}{k}$, as the scaling must be "undone" in the inverse transformation.



> [!example] Exercise
> ![](../z_images/Pasted%20image%2020230810113210.png)
> 
> ![](../z_images/Pasted%20image%2020230810113229.png)
> 
> ![](../z_images/Pasted%20image%2020230810113241.png)

---

## Inverse of a product

Let A and B be invertible matrices, then AB is also invertible and

$$\large (AB)^{-1}=B^{-1}A^{-1}$$


> [!example] Exercise
> ![](../z_images/Pasted%20image%2020230810113548.png)
> 
> ![](../z_images/Pasted%20image%2020230810113614.png)

---

## System of Equations with Unique solution

Intuitively, you can solve the an equation of the form $ax=b$ with $x=a^{-1}b$.

You can use the same method for solving system of linear equations of the form...

$$\large Ax=b \rightarrow x=A^{-1}b$$

Where A is an invertible matrix.

> [!hint]
> ![](../z_images/Pasted%20image%2020230810121009.png)

> [!example] Exercise (using Gauss-Jordan elimination)
> ![](../z_images/Pasted%20image%2020230810121339.png)
