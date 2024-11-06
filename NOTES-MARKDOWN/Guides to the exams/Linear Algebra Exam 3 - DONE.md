This will contain only important stuff

## Linearity of transformations

In order for a transformation to be linear, it must satisfy 2 conditions.

$$\large T(x+y)=T(x)+T(y) \quad \text{and} \quad T(cu)=cT(u)$$

![](../z_images/Pasted%20image%2020230909105318.png)

## Systems of linear equations

Use gaussian elimination/gauss-jordan.

### Solutions
There are three cases:
- **fewer equations than variables**: free variable, which means **infinite solutions**.
- **contradiction**, the system has **no solution**, 
- otherwise it's consistent.

### Homogeneous
An homogeneous system is a sistem with constant terms all to 0, and it has at least one solution.
It can also have infinite solutions and one of them is that all variables are 0.

## Matrix multiplication

**Row of first** matrix x **column of second** matrix. Each one of these operations outputs a single cell.


## Equations with matrices

For addition and subtraction they have the same properties as normal algebra.

> [!hint]
> You can think of it as applying these operations for only the first element of the matrix, it's the same thing, since these operations apply to each one of the cells individually.



## Vector spaces

There will be exercises like this:

![](../z_images/Pasted%20image%2020241022123848.png)


For something to be considered a vector space $V$, it must respect the axioms of vector addition and scalar multiplication:

**Addition**:
- Closure under addition:$\large \quad u + v \in V$
- Cummutativity: $\large \quad u + v = v + u$
- Associativity: $\large \quad u + (v+w)=(u+v)+w$
- Additive identity: There exists a 0 vector that added to other vectors, doesn't change them.
- Additive inverse: For every vector, there exists an inverse one that when added produces 0.

**Scalar multiplication**:
- Closure under scalar multiplication: $\large \quad c\vec{u} \in V$
- Distributivity: $\large \quad c(\vec{u}+\vec{v})=c\vec{u}+c\vec{v}\quad$ e $\large\quad(c+d)\vec{u} = c\vec{u}+d\vec{u}$
- Associativity: $\large \quad c(d\vec{u})=(cd)\vec{u}$
- Scalar identity: $\large \quad 1(\vec{u})=\vec{u}$


> [!hint]
> In this specific case, the commutativity property doesn't hold, because if you put the other vector first, the resulting vector will be $(c, 0)$.


### Subspaces

A subset $W$ of vector space $V$ is a subspace of $V$ if $W$ is a vector space under the operations of addition and multiplication defined in $V$.

We would need to check all 10 axioms, but for some reason we don't give a shit and **we only check for the closures of vector addition**, **closure of scalar multiplication**, and if it has **the 0 vector**.


## Linear independence

A set of vectors is linearly independent when you put them in an homogeneous system, solve for the variables, and the solution is not just 0.

### Polynomials

![](../z_images/Pasted%20image%2020241022193150.png)

## Basis and Dimension

A set of vectors $S$ is a base for the vector space $V$ if $S$ spans $V$ and the vectors in $S$ are linearly independent.

### Check for polynomial basis

WIP



## Eigenvectors and eigenvalues

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


### Finding eigenvectors