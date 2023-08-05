## Definition of Row Echelon form


> [!summary] Pivot definition
> A pivot is the first non-zero element of a row.


A matrix is in row echelon form if it satisfies the following conditions:

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

The matrix is used in many areas of linear algebra, including solving systems of linear equations, calculating the rank of a matrix, and finding the determinant of a matrix. It can be obtained from any matrix using elementary row operations (which include swapping two rows, multiplying a row by a nonzero scalar, and adding a multiple of one row to another row).

---


## Augmented and Coefficient Matrix

Consider a system of linear equations as follows: 

$$\large \begin{align*} 2x + 3y - 4z &= 1 \\ 5x - 6y + 7z &= -8 \\ -9x + 10y - 11z &= 12 \end{align*}$$

The **coefficient matrix** of this system is a matrix consisting only of the coefficients of the variables: 

$$\large A = \begin{bmatrix} 2 & 3 & -4 \\ 5 & -6 & 7 \\ -9 & 10 & -11 \end{bmatrix}$$

The **augmented matrix** of the system includes the constants on the right-hand side of the equations. It represents the entire system of equations: 

$$\large [A|B] = \begin{bmatrix} 2 & 3 & -4 & 1 \\ 5 & -6 & 7 & -8 \\ -9 & 10 & -11 & 12 \end{bmatrix}$$

---


## Elementary row operations