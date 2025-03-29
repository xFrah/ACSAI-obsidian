## EX1) True or False

![](../z_images/Pasted%20image%2020230809111207.png)

> [!tldr] Linear combination Notion
> Mathematically, if you have two vectors $\mathbf{v}$ and $\mathbf{w}$, a linear combination of these vectors can be expressed as:
> 
> $$\large a\mathbf{v}+b\mathbf{w}$$
> 
> where $a$ and $b$ are scalar values.

### 1) Linear combinations

In order to check whether a [linear combination](../Linear%20Algebra/Linear%20Combination.md) can result in a specific vector, we put the vectors as the column of a matrix and we solve the [systems of linear equations](../Linear%20Algebra/Systems%20of%20Linear%20Equations.md) that we have generated.

![](../z_images/Pasted%20image%2020230909102536.png)


### 2) Linearity of transformation

In order for a transformation to be linear, it must satisfy 2 conditions.

$$\large T(x+y) \quad \text{and} \quad T(cu)=cT(u)$$
![](../z_images/Pasted%20image%2020230909105318.png)


### 3) Linear dependency check

> [!note] Definition of $P_2(\mathbb{R})$
> $P_2(\mathbb{R})$ represents the [vector space](../Linear%20Algebra/Vector%20spaces.md) of all polynomials of degree 2 or less with real coefficients. The elements of $P_2(\mathbb{R})$ are polynomials of the form:
> 
> $$\large ax^2+bx+c$$
> 
> where $a$, $b$ and $c$ are real numbers.


 In order to check we can either look at the thing and see that they are not multiples of each other:

![](../z_images/Pasted%20image%2020230909135006.png)


or we gotta solve the following equation for $c_1$ and $c_2$:

$$\large c_1​(1+x)+c_2​(−x^2+2)=0$$

> [!note] How to go from this to system of linear equations
> You expand the thing:
> 
> $$\large c_1 + c_1x + c_2(-x^2) + 2c_2=0$$
> 
> Then you group by their power of $x$.
> 
> $$\large \begin{cases}
\underbracket{c_1 + 2c_2}_{\text{constants}} = 0 \\
c_1 = 0 \\
c_2 = 0
\end{cases}$$


If the only solution is $c1_​=0$ and $c2​=0$, then the set $S$ is [linearly independent](../Linear%20Algebra/Linear%20dependence.md). If there are other(non-zero) solutions for $c_1$​ and/or $c_2​$, then the set $S$ is linearly dependent.


### 4) Checking for subspaces

#### WIP

---


## EX2) Eigenvalues and Eigenvectors, Basis

![](../z_images/Pasted%20image%2020230911143808.png)

### 1) Eigenvalues

Solve the equation given by:

$$\large \text{det}(\lambda I-A)=0$$

> [!warning]
> We may need to re-learn decompositions here.


### 1) Eigenvectors

Solve the system of linear equations given by:

$$\large (\lambda I- A)X =0$$

where $\lambda$ is one of the eigenvalues that we discovered previously and $X$ is the corresponding eigenvector(which we are trying to find).


### 1) Basis for Eigenspaces

An [eigenspace](../Linear%20Algebra/Eigenvectors%20and%20Eigenvalues.md) is the space related to one eigenvalue.
We have two cases:
- We found multiple eigenvectors for a $\lambda$.
- We found a single eigenvector for a $\lambda$.

In the case of one eigenvector, the [basis](../Linear%20Algebra/Basis.md) is simply that eigenvector.
In the case of multiple eigenvectors(they should be [linearly independent](../Linear%20Algebra/Linear%20dependence.md)), the basis is $\{v_0,\cdots, v_n\}$.


### 2) Diagonalization and Invertible matrices

> [!note]
> A matrix is called a diagonal matrix if all of its off-diagonal entries are zero. For example:
> 
> ![](../z_images/Pasted%20image%2020230911122338.png)
> 
> where $a,b,c$ are real numbers.

> [!hint]
> **Every [symmetric matrix](../Linear%20Algebra/Symmetric%20matrix.md) is diagonalizable.**
> 
> A matrix $A$ is said to be symmetric if $A=A^T$, where $A^T$ denotes the transpose of $A$.


This entire process is called diagonalization, its goal is to find an invertible matrix $P$ and a diagonal matrix $D$ such that:

$$\large P^{−1}AP=D$$

where:
- $P$: Matrix constructed by placing the eigenvectors of $A$ as its columns. If $A$ has $n$ linearly independent eigenvectors, then $P$ is invertible, and $A$ can be diagonalized.
- $D$: This is a diagonal matrix where the diagonal entries are the eigenvalues of $A$. The order of the eigenvalues in D should match the order of the corresponding eigenvectors in P.

![](../z_images/Pasted%20image%2020230911131024.png)

---


## EX3) Basis for Row space and Column space, Rank, Nullity, Null space

![](../z_images/Pasted%20image%2020230911143739.png)

### 1) Basis for Row space

Turn the matrix in [R.E.F](../Linear%20Algebra/Gaussian%20Elimination.md). then get the non-zero rows. Those will be the vectors of our basis.

![](../z_images/Pasted%20image%2020230911143332.png)
![](../z_images/Pasted%20image%2020230911143341.png)

### 1) Basis for Column space

You either re-use the matrix that we used in the row space, and get the columns that have the pivots(they are surely [linearly independent](../Linear%20Algebra/Linear%20dependence.md)).

Or you can use the same process of the row space on $A^T$.

![](../z_images/Pasted%20image%2020230911145703.png)


### 1) Rank

The rank is just the dimensionality of the column space(the number of vectors in its basis). In this case $\text{Rank}(A)=3$.


### 1) Nullity

The nullity of matrix $A$ The dimension of the null space.
We can compute it through the following relation:

$$\large \text{Nullity}(A) + \text{Rank}(A) = \text{number of columns}$$

![](../z_images/Pasted%20image%2020230911150339.png)


### 2) Null space

The [null space](../Linear%20Algebra/Null%20space.md) of a matrix is the set of vectors that go to 0 after the transformation:

$$\large Ax=0$$

We just need to solve the [system of linear equations](../Linear%20Algebra/Systems%20of%20Linear%20Equations.md) given by the formula above.

![](../z_images/Pasted%20image%2020230911152406.png)


The free variables are $x_4$ and $x_5$, so we set $x_4 = S$ and $x_5 = t$.

![](../z_images/Pasted%20image%2020230911152930.png)


We then group by the parameters and generate these two vectors:

![](../z_images/Pasted%20image%2020230911153040.png)

---


## EX4) Determinant properties, Invertibility, basis

### Determinant properties

- $\text{det}(A^{-1})=\large\frac{1}{\text{det}(A)}$ (if $A$ is invertible, so $|A|\neq 0$).
- $\text{det}(A^T)=\text{det}(A)$ (if $A$ is square).
- $\text{det}(cA)=c \cdot \text{det}(A)$ (if $A$ is square).
- $\text{det}(AB)=\text{det}(A)\text{det}(B)$ (if $A$ and $B$ are square).


### Solutions for invertibility

We just pose $|A|=0$ and solve the equation.

![](../z_images/Pasted%20image%2020230912100214.png)

