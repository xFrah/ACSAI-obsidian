---
alias: Vector
---

$v$ is a high dimentional point in a vector space.

$$\huge v=\begin{bmatrix}x\\ y\end{bmatrix}$$

Vectors are written column wise. We can make it row wise by transposing it.

$$\huge v^T=[x_0,\;x_1,\;...,\;x_D]$$

A vector isn't just a list of numbers. We need to have an origin and an orientation of the axes.

Imagine a plane with a looot of dimensions, then a vector is just a point inside of it.
Each component i of the vector is a scalar that stands for the coordinate of the dimension i.

---

## Geometric Interpretation:

### Point in space:
Given a vector, the first interpretation that we should give it is as a point in space

"In two or three dimensions, we can visualize these points by using the components of the vectors to define the location of the points in space compared to a fixed reference called the origin.

![](../z_images/Pasted%20image%2020230228151326.png)

### Direction in space:
The bright side of this one is that the vector addition actually makes sense.
It would just be to follow the directions of the first vector, than we follow the directions from the second vector, getting to the point.

![](../z_images/Pasted%20image%2020230228151310.png)


```ad-important
A fundamental concept of vectors, is the idea that a vector is the sum of the scaled [basis](Basis.md) vectors.

Let me clarify. We know that the base vectors are the vectors of length 1 that lie on the two axis.

> ![](../z_images/Pasted%20image%2020230304125916.png)

We can represent the vector `[3, -2]` as the scalars that multiply the basis vectors.

So we would have:
`3*[1, 0] and -2*[0, 1]`, so `[3, 0] and [0, -2].`

> ![](../z_images/Pasted%20image%2020230304130123.png)

If we sum these two vectors, we can see that the resulting point in space is exactly our vector `[3, -2]`.

So we can represent our vector v as `3*Ĵ + -2*î`.

> ![](../z_images/Pasted%20image%2020230304130045.png)
```

---

## Span:

The span of a vector is the set of all their [linear combinations](Linear%20Combination.md)(sum of vectors).
The span of most 2D vectors is a 2D space.

![](../z_images/Pasted%20image%2020230304133130.png)

---

## Linear indipendence/Dimensions collapsing

If two basis vectors line up in the same directions, the span lies on a single line.
Another definition, is that if a basis vector sits on the span of another vector, it is redundant and doesn't add anything to the span of the system.

Two vectors are [linearly dependent](Linear%20dependence.md) if one is the scaled version of the other.

![](../z_images/Pasted%20image%2020230304133216.png)


```ad-info
title: Norm
What is the [norm](Norm.md) of a vector?

**The length of the vector** is referred to as the vector norm or the vector's magnitude.
```
