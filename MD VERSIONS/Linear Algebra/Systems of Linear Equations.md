A system of linear equations is a collection of linear equations involving the same variables.

$$\large\begin{align*} x + 2y - 3z &= 4 \\ 3x - y + 2z &= -1 \\ 4x + y - z &= 2 \end{align*}$$

---

## Augmented and Coefficient [Matrix](Matrix%20(ML).md)

Consider a system of linear equations as follows: 

$$\large \begin{align*} 2x + 3y - 4z &= 1 \\ 5x - 6y + 7z &= -8 \\ -9x + 10y - 11z &= 12 \end{align*}$$

The **coefficient matrix** of this system is a matrix consisting only of the coefficients of the variables: 

$$\large A = \begin{bmatrix} 2 & 3 & -4 \\ 5 & -6 & 7 \\ -9 & 10 & -11 \end{bmatrix}$$

The **augmented matrix** of the system includes the constants on the right-hand side of the equations. It represents the entire system of equations: 

$$\large [A|B] = \begin{bmatrix} 2 & 3 & -4 & 1 \\ 5 & -6 & 7 & -8 \\ -9 & 10 & -11 & 12 \end{bmatrix}$$

---

## Elementary row operations

1. **Interchange 2 rows**
2. **Multiply a row** by a non-zero constant
3. **Add** a multiple(potentially negative) of a row to another row

---

## How to solve

- Parametric solution
- Substitution 
- Elimination (also known as the method of addition) 
- Matrix method (using matrices and, frequently, [Gaussian elimination](Gaussian%20Elimination.md) or its variant, [Gauss-Jordan elimination](Gaussian%20Elimination.md))


> [!note] Parametric solution
> For example, consider the following dependent system of equations:
> 
> $$\large\begin{align*} x + y + z &= 3 \\ 2x + 2y + 2z &= 6 \\ \end{align*}$$
> 
> We can choose $z$ as a parameter, say $z=t$. Then the solution set of the system can be written as:
> 
> $$\large\begin{align*} x &= 3 - t \\ y &= 3 - t \\ z &= t \\ \end{align*}$$
> 
> 
> > [!hint]
> > For every value of $t$, we get a different solution of the system.
> > The choice of parameter is arbitrary and does not change the solution set.
> 

---

## Solutions

The solution to such a system is an assignment of values to the variables such that all the equations are satisfied.

A system of linear equations is either: 
1. **Inconsistent**: No solution.
2. **Consistent**: At least 1 solution.


> [!hint]
> During the process of elimination, if one row is full of zeros except for the last element, you can safely say that the system has no solutions.
> 
> ![](../z_images/Pasted%20image%2020230806132327.png)
