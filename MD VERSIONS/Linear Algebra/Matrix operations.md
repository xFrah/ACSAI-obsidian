## Addition

Given two 2x2 [matrices](Matrix%20(ML).md) $A$ and $B$: 

$$\large A = \begin{bmatrix} a & b \\ c & d \end{bmatrix} ,\quad B = \begin{bmatrix}e & f \\g & h \end{bmatrix} $$

Their sum $A + B$ would be: 

$$\large A + B = \begin{bmatrix} a + e & b + f \\ c + g & d + h \end{bmatrix}$$

> [!note] Title
> Note that matrix addition is commutative, meaning $A + B = B + A$, and associative, meaning $(A + B) + C = A + (B + C)$.

---

## Scalar Multiplication

Given a scalar $k$ and a matrix ì$A$: 

$$\large A = \begin{bmatrix} a & b \\ c & d \end{bmatrix} $$

The scalar multiplication $kA$ would be: 
$$\large kA = \begin{bmatrix} ka & kb \\ kc & kd \end{bmatrix}$$

> [!note] Title
> Note that scalar multiplication is associative, meaning $k(lA) = (kl)A$, and it is distributive over matrix addition, meaning $k(A + B) = kA + kB$.

---

## Matrix Multiplication

There are a few methods for matrix multiplication:

### Basis [vectors](Vectors.md) method

I'll skip this, because we don't really need it in this shit exam.

### Dot product method
You compute the [dot product](Dot%20product.md) between the rows of the first matrix and the columns of the second matrix.


![](../z_images/Pasted%20image%2020230701131314.png)
![](../z_images/Pasted%20image%2020230701131332.png)


Here are some important properties of matrix multiplication:

1. **Associativity:** $(AB)C = A(BC)$.

2. **Distributivity over Addition:**  $A(B + C) = AB + AC$ and $(A + B)C = AC + BC$.

3. **Not Commutative:** $AB$ does not necessarily equal $BA$.

4. **Scalar Multiplication:** $r(AB) = (rA)B = A(rB)$.

5. **Transpose of a Product:** The transpose of a product is the product of their transposes in reverse order. That is, $(AB)^T = B^T A^T$.


> [!NOTE] Title
> Note that matrix multiplication is not commutative, meaning $AB$ is not necessarily equal to $BA$. 
> It is, however, associative, meaning $(AB)C=A(BC)$, and it is distributive over matrix addition, meaning $A(B+C)=AB+AC$.

> [!hint]
>   
You cannot multiply two matrices if the number of columns in the first matrix is not equal to the number of rows in the second matrix.

---


## Transpose of a Matrix

The transpose of a matrix is obtained by flipping the matrix over its diagonal.

$$\large A = \begin{bmatrix} a & b & c \\ d & e & f \\ g & h & i \end{bmatrix}, \quad A^T = \begin{bmatrix} a & d & g \\ b & e & h \\ c & f & i \end{bmatrix}$$

Here are a few properties of the transpose operation: 
1. $(A^T)^T = A$
2. $(A + B)^T = A^T + B^T$
3. $(kA)^T = k(A^T)$ where $k$ is a scalar 
4. $(AB)^T = B^TA^T$


> [!note] Symmetric Matrices
> A matrix is symmetric if it is equal to its transpose.
> 
> $$\large A = A^T$$
> 
> For instance, the following matrix is symmetric:
> 
> $$\large A = \begin{bmatrix} 1 & 2 & 3 \\ 2 & 4 & 5 \\ 3 & 5 & 6 \end{bmatrix}$$
> 
> The entries of the matrix are mirrored along the main diagonal.

> [!NOTE] Skew-Matrices (Antisymmetric)
> A square matrix whose transpose is equal to its negative.
> 
> $$\large AT=−A$$
> 
> For example, the following matrix is antisymmetric:
> 
> $$\large A = \begin{bmatrix} 0 & 2 & -3 \\ -2 & 0 & 4 \\ 3 & -4 & 0 \end{bmatrix}$$
> 
> One important property of skew-symmetric matrices is that their diagonal elements are all zero.

---


## Trace of a Matrix

The trace of a square matrix is the sum of the elements on its diagonal. 
For example, if we have a matrix \( A \): 
$$\large A = \begin{bmatrix} a & b \\ c & d \end{bmatrix}$$
The trace of $A$ is:

$$\large\text{tr}(A) = a + d$$

Some properties of the trace operation include: 
1. $\text{tr}(A + B) = \text{tr}(A) + \text{tr}(B)$
2. $\text{tr}(kA) = k \cdot \text{tr}(A)$ where $k$ is a scalar 
3. $\text{tr}(AB) = \text{tr}(BA)$
4. $\text{tr}(A^T) = \text{tr}(A)$

