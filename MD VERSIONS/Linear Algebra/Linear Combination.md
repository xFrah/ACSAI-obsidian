---
alias: Linear Combinations
---

A [vector](Vectors.md) $v$ in a V.S. $V$ is called a Linear Combination of the vectors $u_1, u_2, \dots u_k$ in $V$ can be written in the form:

$$\large v=c_1u_1 + c_2u_2+\dots + c_ku_k$$

where $c_1 \dots c_k$ are scalars.

> [!example]
> ![](../z_images/Pasted%20image%2020230814182921.png)

---

## How to find a Linear Combination

Assume we have to vectors $v$ and $u$, and we want to find the linear combination between them that gives the vector $\begin{bmatrix}x\\ y\end{bmatrix}$.

We would have to solve the following:

$$\large\begin{bmatrix}x\\ y\end{bmatrix}=c_1v+c_2u=c_1\begin{bmatrix}
v_1 \\ v_2
\end{bmatrix}+c_2\begin{bmatrix}
u_1 \\ u_2
\end{bmatrix}=\begin{bmatrix}
c_1v_1 \\ c_1v_2
\end{bmatrix} + \begin{bmatrix}
c_2u_1 \\ c_2u_2
\end{bmatrix}$$

Which is a [system of linear equations](Systems%20of%20Linear%20Equations.md):

$$\large \begin{bmatrix}
c_1v_1+c_2u_1 \\
c_1v_2+c_2u_2
\end{bmatrix} = \begin{bmatrix}x\\ y\end{bmatrix}$$

We use [Gaussian Elimination](Gaussian%20Elimination.md) to solve this.