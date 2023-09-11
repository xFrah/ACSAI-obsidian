---
aliases:
  - Eigenvectors
  - Eigenvalue
  - Eigenvector
  - Eigenvalue
  - Eigenspace
  - Eigenspaces
---

In a transformation, eigenvectors are the [vectors](Vectors.md) that don't change direction, but get just scaled.

The factors by which they get scaled is called eigenvalue, and each eigenvactor has an associated eigenvalue.

There can also be no eigenvectors.

```ad-example
Imagine we have two vectors in the basic plane:
> ![](../z_images/Pasted%20image%2020230310215652.png)

We put the plane through the transformation: $\Large \begin{bmatrix}
3 & 1 \\
0 & 2
\end{bmatrix}$

> ![](../z_images/Pasted%20image%2020230311005745.png)

Every other vector drifts to another direction, but not these guys.
> ![](../z_images/Pasted%20image%2020230310212711.png)

These vectors just get scaled.
```

```ad-info
The [determinant](Determinant.md) of a [matrix](Matrix.md) is the product of eigenvalues.
```

```ad-info
In a 3D rotation, the axis of rotation is an eigenvector. It doesn't change direction.
```

---

## Formal definition

![](../z_images/Pasted%20image%2020230311132943.png)

The <font color="#31859b">eigen vectors</font> are such that when receiving a <font color="#b2a2c7">linear transformation</font>, they stay on the same <font color="#31859b">original direction</font>, only scaled by their <font color="#c0504d">eigenvalue</font>($\large\lambda$).

---


## Eigenspaces

![](../../Pasted%20image%2020230910180425.png)

---


## How to compute Eigenvalues

![](../../Pasted%20image%2020230910162026.png)

---


## How to compute Eigenvectors

This process must be done for each eigenvalue separately.

![](../../Pasted%20image%2020230910162337.png)


We input $\lambda$ in this equations for each eigenvalue.
We are left with a system of linear equations that we can solve using any method we want.

![](../../Pasted%20image%2020230910171538.png)

---


## Examples with 3x3 matrices

### Eigenvalues

![](../../Pasted%20image%2020230910174634.png)

![](../../Pasted%20image%2020230910174709.png)


### Eigenvectors

![](../../Pasted%20image%2020230910174826.png)

![](../../Pasted%20image%2020230910174835.png)

Now we solve the system:

![](../../Pasted%20image%2020230910174909.png)

![](../../Pasted%20image%2020230910175145.png)

Now we assign $1$ to $x_3$

![](../../Pasted%20image%2020230910175221.png)

![](../../Pasted%20image%2020230910175236.png)