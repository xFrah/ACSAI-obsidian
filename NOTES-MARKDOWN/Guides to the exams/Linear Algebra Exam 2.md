![](../z_images/Pasted%20image%2020240326094130.png)

### Find the eigenvalues

In order to find the eigenvalues, we need to solve the following equation:

$$\large |\,A - \lambda I \,|=0$$

> [!note]
> $|\, M \,|$ means determinant of $M$.

In this case:
$$\large \begin{bmatrix}
1 & -1 & -1 \\
0 & 1 & -2 \\
0 & 1 & 4
\end{bmatrix}
-\lambda 
\begin{bmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{bmatrix}=0$$
$$\large \begin{bmatrix}
1 & -1 & -1 \\
0 & 1 & -2 \\
0 & 1 & 4
\end{bmatrix}
-
\begin{bmatrix}
\lambda & 0 & 0 \\
0 & \lambda & 0 \\
0 & 0 & \lambda
\end{bmatrix}=0$$
$$\large
\begin{bmatrix}
1 - \lambda & -1 & -1 \\
0 & 1 -\lambda & -2 \\
0 & 1 & 4 -\lambda
\end{bmatrix}=0$$

Then we set the determinant to 0 and we solve the equation:

$$\large
\det\left(\begin{bmatrix}
1 - \lambda & -1 & -1 \\
0 & 1 -\lambda & -2 \\
0 & 1 & 4 -\lambda
\end{bmatrix}\right)=0$$

> [!note] Determinant of 3x3 matrix
> We choose a row or a column. We compute the cofactors for each element of the row/column. 

In this case we choose the first column and we sum the product between the elements and their cofactors. 

![](../z_images/Pasted%20image%2020240406173418.png)

$$\large c_{00}\cdot (1-\lambda) + c_{01} \cdot (0) + c_{02}\cdot (0)$$

> [!note] How to compute a cofactor
> 1) We compute the determinant of the matrix left from erasing the column and row that contain the element.
> 2) We multiply by the element.
> 3) We multiply by the right sign.
>    
>  ![](../z_images/Pasted%20image%2020230811174851.png)


![](../z_images/Pasted%20image%2020240406175658.png)

> [!note] Determinant of 2x2 matrix
> 
> $$\large A=\begin{bmatrix}
> a & b \\ c & d
> \end{bmatrix}$$
> 
> The determinant of the matrix above is given by:
> 
> $$\large \text{det}(A)=ad-bc$$
> 


The determinant of the matrix above is:

$$\large
\det\left(\begin{bmatrix}
1 -\lambda & -2 \\
1 & 4 -\lambda
\end{bmatrix}\right) = (1-\lambda)\cdot(4-\lambda) - (-2)\cdot(1)=(4 - \lambda -4\lambda+\lambda^2) + 2=\lambda^2 -5\lambda + 6$$

We are left with:
$$\large c_{00} = (1-\lambda) \cdot (\lambda^2 -5\lambda + 6)$$

> [!note] Quadratic formula
> The quadratic formula can be used to find the roots (solutions) of any quadratic equation of the form:
> $$\large ax^2 + bx + c = 0$$
> 
> This is the quadratic formula:
> $$\large x=\frac{-b ± \sqrt{b^2 - 4ac}}{2a}$$

$$\large \lambda=\frac{5±\sqrt{25-24}}{2}=\;\;<\frac{6}{2}, \;\frac{4}{2}>$$
$$\large \lambda = 1$$

So the solutions are:

$$\large \lambda = 1, \;\lambda = 3, \;\lambda = 2$$
