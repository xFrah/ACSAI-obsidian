---
alias: Minor, Cofactor, minors, cofactors, determinants
---
Every square [matrix](Matrix%20(ML).md) can be associated with a real number called its determinant.


> [!abstract] Notation
> You can refer to the determinant of matrix $A$ as either det($A$) or |$A$|.

---

## Determinant of a 2x2 Matrix

$$\large A=\begin{bmatrix}
a & b \\ c & d
\end{bmatrix}$$

The determinant of the matix above is given by

$$\large \text{det}(A)=ad-bc$$

> [!example] Exercise
> ![](../z_images/Pasted%20image%2020230810122936.png)

---

## Determinant of a Triangular Matrix

The determinant of a triangular matrix is given by the product of the elements on its main diagonal.

> [!summary] Triangular matrix Summary
> A triangular matrix can be:
> - **Upper triangular**: All 0's below the main diagonal.
>   
> 	![](../z_images/Pasted%20image%2020230810123719.png)
> - **Lower triangular**: All 0's above the main diagonal.
> 
> 	![](../z_images/Pasted%20image%2020230810123736.png)
> - **Diagonal matrix**: All 0's except for the main diagonal.
> 
> 	![](../z_images/Pasted%20image%2020230810123749.png)

---

## Minors and Cofactors of a matrix

The minor $M_{ij}$ of a square matrix $A$ is the determinant of the matrix with row $i$ and column $j$ killed.

![](../z_images/Pasted%20image%2020230811174914.png)

The cofactor is given by:

$$\large C_{ij} = (-1)^{i+j} \cdot Mij$$


> [!hint]
> That means that the cofactors and the minors differ by just a sign(at most). The sign depends on the position of the entry.
> 
> ![](../z_images/Pasted%20image%2020230811174851.png)

> [!example]
> ![](../z_images/Pasted%20image%2020230811195826.png)

---

## Determinant of general square Matrices

The determinant of a square matrix is the sum of the entries in the 1st row multiplied by their cofactors.

$$\large |A|=a_{11}c_{11}+a_{12}c_{12}+\dots + a_{1n}c_{1n}$$


> [!note]
> I think we can do this with any row or column of the matrix.
> Usually we take the row/column with the most 0's.

> [!example]
> ![](../z_images/Pasted%20image%2020230811200346.png)

---

## The zero determinant

If $A$ is a square matrix, then $det(A)=0$ if one of the following conditions hold:

1) An entire row/column are equal.
2) Two rows/columns are equal.
3) One row/column is a multiple of another row/column


> [!example]
> ![](../z_images/Pasted%20image%2020230813114849.png)

---

## How the determinant changes when using Elementary Row operations

> [!hint] An alternative to the cofactors method
> If you don't feel like doing the thing with cofactors, you can try to turn the matrix into a triangular one, taking into consideration how the determinant changes when we apply elementary row operations.
> 
> ![](../z_images/Pasted%20image%2020230813122547.png)


1) If we interchange two rows of A, the determinant chang sign.

> [!example]
> ![](../z_images/Pasted%20image%2020230813115615.png)

2) If we add a multiple of a row of A to another row of A, the determinant stays the same.

> [!example]
> ![](../z_images/Pasted%20image%2020230813115635.png)

3) If we multiply a row of A by a non-zero scalar, the determinant is equal to itself multiplied by a scalar.

> [!example]
> ![](../z_images/Pasted%20image%2020230813120401.png)
> ![](../z_images/Pasted%20image%2020230813120413.png)

> [!hint]
> You can also use these opeations to create more zeros in a row or column, as to make the cofactor process easier.
> 
> ![](../z_images/Pasted%20image%2020230813122827.png)
