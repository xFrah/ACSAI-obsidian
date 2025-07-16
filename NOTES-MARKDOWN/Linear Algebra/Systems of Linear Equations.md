---
alias: system of linear equations
---
A system of linear equations is a collection of linear equations involving the same variables.

$$\large\begin{align*} x + 2y - 3z &= 4 \\ 3x - y + 2z &= -1 \\ 4x + y - z &= 2 \end{align*}$$

---

## Augmented and Coefficient [Matrix](Matrix%20(ML).md)

Consider a system of linear equations as follows: 

$$\large \begin{align*} 2x + 3y - 4z &= 1 \\ 5x - 6y + 7z &= -8 \\ -9x + 10y - 11z &= 12 \end{align*}$$

![](../z_images/Pasted%20image%2020230819191825.png)

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

---

## Cramer's Rule

If a system of linear equations has a coefficient matrix with a non-zero [determinant](Determinant.md) $|A|$, then you can compute the solution with Cramer's rule.

Given a system of linear equations:

$$\large\begin{align*} a_{11}x_1 + a_{12}x_2 + \ldots + a_{1n}x_n & = b_1 \\ a_{21}x_1 + a_{22}x_2 + \ldots + a_{2n}x_n & = b_2 \\ \vdots & \, \\ a_{n1}x_1 + a_{n2}x_2 + \ldots + a_{nn}x_n & = b_n \end{align*}$$

You can write this system as $AX = B$, where:
- $A$ is the matrix of coefficients.
- $X$ is the column matrix of variables $[x_1, x_2, \ldots, x_n]^T$.
- $B$ is the column matrix of constants $[b_1, b_2, \ldots, b_n]^T$.

To solve for each variable $x_i$, you can use the following formula:

$$\large x_i = \frac{\text{det}(A_i)}{\text{det}(A)}$$

where:

- $\text{det}(A)$ is the determinant of the original coefficient matrix $A$.
- $\text{det}(Ai_​)$ is the determinant of the matrix obtained by replacing the $i$-th column of $A$ with the column matrix $B$.


> [!example]
> Consider a system of two equations:
> 
> $$\large\begin{align*} 2x + 3y & = 1 \\ 3x + 4y & = 2 \end{align*}$$
> 
> 1. **Calculate the Determinant of $A$:**
>  $$\large\text{det}(A) = \text{det}\left(\begin{bmatrix} 2 & 3 \\ 3 & 4 \end{bmatrix}\right) = 1$$
> 
> 2. **Calculate the Determinant of $A_x$:**
>   $$\large\text{det}(A_x) = \text{det}\left(\begin{bmatrix} 1 & 3 \\ 2 & 4 \end{bmatrix}\right) = -2$$
> 
> 3. **Calculate $x$:**
>   $$\large x = \frac{\text{det}(A_x)}{\text{det}(A)} = -2$$
> 
> 4. **Repeat Steps 2-3 for $y$:**
>   $$\large y = \frac{\text{det}\left(\begin{bmatrix} 2 & 1 \\ 3 & 2 \end{bmatrix}\right)}{\text{det}(A)} = 1$$
> 
> The solution to the system is $x = -2, y = 1$.
> 

---

## Solutions for non-homogeneous systems

?????

![](../z_images/Pasted%20image%2020230819195438.png)