---
alias: spanning sets, spans
---

A spanning set is a specific set of [vectors](Vectors.md) that can be combined through [linear combinations](Linear%20Combination.md) to create every possible vector in that [vector space](Vector%20spaces.md).

> [!example]
> Consider the vector space $\mathbb{R}^2$, which represents the two-dimensional plane. Let's take two non-collinear vectors, such as:
> 
> 
> $$\large\mathbf{v}_1 = \begin{bmatrix} 1 \\ 0 \end{bmatrix},\quad\mathbf{v}_2 = \begin{bmatrix} 0 \\ 1 \end{bmatrix}$$
> 
> 
> These vectors form a spanning set for $\mathbb{R}^2$, as any vector $\begin{bmatrix} x \\ y \end{bmatrix}$ in $\mathbb{R}^2$ can be expressed as a linear combination of $\mathbf{v}_1$ and $\mathbf{v}_2$:
> 
> 
> $$\large \begin{bmatrix} x \\ y \end{bmatrix} = x\begin{bmatrix} 1 \\ 0 \end{bmatrix} + y\begin{bmatrix} 0 \\ 1 \end{bmatrix}$$
> 
> 
> This means that by scaling and adding these two vectors, you can reach any point in the two-dimensional plane, so they span $\mathbb{R}^2$.
> 
> 

---

## How to check if a set spans the [vector space](Vector%20spaces.md)

We set up a general linear combination:

$$\large\begin{bmatrix} x \\ y \end{bmatrix} = r\begin{bmatrix} a \\ b \end{bmatrix} + s\begin{bmatrix} c \\ d \end{bmatrix}$$

where $r$ and $s$ are scalars, then make system of linear equations that comes out of it.

$$\large \begin{align*} ra + sc & = x \\ rb + sd & = y \end{align*}$$

Then we check for solutions: 
- If the [determinant](Determinant.md) of the coefficient matrix is non-zero, i.e., $\text{det}\left(\begin{bmatrix} a & c \\ b & d \end{bmatrix}\right) \neq 0$, then the vectors span $\mathbb{R}^2$. 
- If the determinant is zero, the vectors do not span $\mathbb{R}^2$.


> [!example]
> Consider the vectors: 
> $$\large\mathbf{v}_1 = \begin{bmatrix} 1 \\ 2 \end{bmatrix},\quad 
> \mathbf{v}_2 = \begin{bmatrix} 3 \\ 4 \end{bmatrix}$$
> 
> The determinant of the coefficient matrix is: 
> 
> $$\large\text{det}\left(\begin{bmatrix} 1 & 3 \\ 2 & 4 \end{bmatrix}\right) = -2 \neq 0$$
> 
> Since the determinant is non-zero, these vectors span $\mathbb{R}^2$.

> [!hint]
> A [system of linear equations](Systems%20of%20Linear%20Equations.md) $Ax=b$ has solution if and only if $\text{det}(A)\neq 0$
