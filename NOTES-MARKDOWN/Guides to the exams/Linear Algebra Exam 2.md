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
> We need to use minors and cofactors.
