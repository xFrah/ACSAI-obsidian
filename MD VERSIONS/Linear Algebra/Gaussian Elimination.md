---
alias: Gauss-Jordan Elimination
---
## Row Echelon Form


> [!summary] Pivot definition
> A pivot is the first non-zero element of a row.


A [matrix](Matrix%20(ML).md) is in row echelon form if it satisfies the following conditions:

1. **Leading Coefficients:** All nonzero rows have a pivot that is to the right of the pivot of the row above it.

2. **Zero Rows:** Any rows that contain only zeros are at the bottom of the matrix.

3. **Non-Zero Rows:** In any nonzero row, the pivot equals to 1.

For example, the following matrix is in row echelon form:


$$\large \begin{bmatrix}
1 & 2 & -1 & 4 \\
0 & 1 & 3 & 8 \\
0 & 0 & 1 & 2 \\
0 & 0 & 0 & 0
\end{bmatrix}
$$

The matrix is used in many areas of linear algebra, including solving [systems of linear equations](Systems%20of%20Linear%20Equations.md), calculating the rank of a matrix, and finding the [determinant](Determinant.md) of a matrix. It can be obtained from any matrix using elementary row operations (which include swapping two rows, multiplying a row by a nonzero scalar, and adding a multiple of one row to another row).

---

#
---

## Gaussian Elimination with back-substitution

1. **Write the Augmented Matrix:** Write down the augmented matrix.
    
2. **Perform Row Operations to Reach Row Echelon Form:** Use elementary row operations to transform the augmented matrix into row echelon form.
    
> [!tldr]
> - **Swap Rows:** You can swap two rows.
> - **Multiply a Row by a Scalar:** You can multiply a row by a nonzero constant.
> - **Add a Multiple of One Row to Another Row:** You can replace a row by adding to it a scalar multiple of another row.
	
3. **Back Substitution:** Write down the system corresponding to the matrix, then start with the last row and solve for the variable in that row. Then, move up to the previous row and use the previously found variables to solve for the new variable. Continue this process until all variables are found.


> [!example]
> 
> Suppose we have the following system of linear equations:
> 
> $$\large\begin{align*}
x + 2y - z &= 4 \\
3x + 8y + z &= 20 \\
4x + 6y + 5z &= \phantom{-}6
\end{align*}$$
>
>We can represent this system as an augmented matrix:
>
>$$\large\begin{bmatrix}
1 & 2 & -1 & 4 \\
3 & 8 & 1 & 20 \\
4 & 6 & 5 & 6
\end{bmatrix}$$
> 
> Now, we'll perform Gaussian elimination to reach row echelon form:
>
>1. **First Pivot:**
   No need to change the first row. Start with the second row and subtract three times the first row from it. Then, subtract four times the first row from the third row:
>
>$$\large\begin{bmatrix}
1 & 2 & -1 & 4 \\
3 & 8 & 1 & 20 \\
4 & 6 & 5 & 6
\end{bmatrix}\rightarrow\begin{bmatrix}
1 & 2 & -1 & \phantom{-}4 \\
0 & 2 & 4 & \phantom{-}8 \\
4 & 6 & 5 & 6
\end{bmatrix}\rightarrow
\begin{bmatrix}
1 & 2 & -1 & \phantom{-}4 \\
0 & 2 & 4 & \phantom{-}8 \\
0 & -2 & 9 & -10
\end{bmatrix}$$
>
>2. **Second Pivot:**
   Divide the second row by 2 to make the leading coefficient 1. Then, subtract the second row from the third row:
>
>$$\large\begin{bmatrix}
1 & 2 & -1 & \phantom{-}4 \\
0 & 2 & 4 & \phantom{-}8 \\
0 & -2 & 9 & -10
\end{bmatrix}\rightarrow\begin{bmatrix}
1 & 2 & -1 & \phantom{-}4 \\
0 & 1 & 2 & \phantom{-}4 \\
0 & -2 & 9 & -10
\end{bmatrix}$$
>
>3. **Third Pivot**
>   Add the second row to the third row in order to shift the leading coefficient. Then, divide by 11 to make the leading coefficient 1.
>   
> $$\large\begin{bmatrix}
1 & 2 & -1 & \phantom{-}4 \\
0 & 1 & 2 & \phantom{-}4 \\
0 & -2 & 9 & -10
\end{bmatrix}\rightarrow\begin{bmatrix}
1 & 2 & -1 & \phantom{-}4 \\
0 & 1 & 2 & \phantom{-}4 \\
0 & 0 & 11 & -6
\end{bmatrix}\rightarrow\begin{bmatrix}
1 & 2 & -1 & \phantom{-}4 \\
0 & 1 & 2 & \phantom{-}4 \\
0 & 0 & 1 & -\frac{6}{11}
\end{bmatrix}$$
>
>4. **Back Substitution:**
>   
> $$\large\begin{align*} x + 2y - z &= 4 \\ y + 2z &= 4 \\ z &= -\frac{6}{11} \end{align*}$$
>   
   Now, we can find the variables using back substitution:
>   - Solve the third equation for $z$:  $z = -\frac{6}{11}$
>  ### WIP, WRONG
>   - Use z to find $y$: $y + 2\left(-\frac{6}{11}\right) = 4 \Rightarrow y = \frac{26}{5}$
>   - Use y and z to find $x$: $x + 2\left(\frac{26}{5}\right) - \left(-\frac{14}{5}\right) = 4 \Rightarrow x = -\frac{8}{5}$
>
>
>So, the solution to the system is $x = -\frac{8}{5}$, $y = \frac{26}{5}$, and $z = -\frac{14}{5}$.

---

## Reduced Row Echelon Form

A matrix is in RREF if it satisfies this additional following condition(with respect to r.e.f): 

4. **Zero Above and Below Pivots:** Every entry above and below a pivot is 0. 


> [!example]
> Here's an example of a matrix in Reduced Row Echelon Form: 
> 
> $$\large\begin{bmatrix} 1 & 0 & 3 & 7 \\ 0 & 1 & -2 & -3 \\ 0 & 0 & 0 & 0 \end{bmatrix}$$
> 
> This matrix satisfies all the conditions for RREF: 
> - The leading coefficient in each non-zero row is 1. 
> - The pivots occur in successive columns. 
> - There is a row with all zero entries at the bottom of the matrix. - There are zeros above and below each pivot.

---

## Gauss-Jordan Elimination

Same steps as the Gauss-Jordan Elimination, but now we continue the reduction process until we have a Reduced Row Echelon Form.


> [!example]
> ![](../z_images/Pasted%20image%2020230806102622.png)
