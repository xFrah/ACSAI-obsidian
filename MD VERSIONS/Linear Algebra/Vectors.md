$v$ is a high dimentional point in a vector space.

$$\huge v=\begin{bmatrix}x\\ y\end{bmatrix}$$

Vectors are written column wise. We can make it row wise by transposing it.

$$\huge v^T=[x_0,\;x_1,\;...,\;x_D]$$

A vector isn't just a list of numbers. We need to have an origin and an orientation of the axes.

Imagine a plane with a looot of dimensions, then a vector is just a point inside of it.
Each component i of the vector is a scalar that stands for the coordinate of the dimension i.


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
A fundamental concept of vectors, is the idea that a vector is the sum of the scaled basis vectors.

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


## Span:

The span of a vector is the set of all their linear combinations(sum of vectors).
The span of most 2D vectors is a 2D space.

![](../z_images/Pasted%20image%2020230304133130.png)


## Linear indipendence/Dimensions collapsing

If two basis vectors line up in the same directions, the span lies on a single line.
Another definition, is that if a basis vector sits on the span of another vector, it is redundant and doesn't add anything to the span of the system.

Two vectors are linearly dependent if one is the scaled version of the other.

![](../z_images/Pasted%20image%2020230304133216.png)


## Inner product (Dot product)

Let $\large x$ and $\large y$ be two 2D vectors with their magnitudes $\large |x|$ and $\large |y|$.

Now, we take $\large y$ and compute the length of its [projection](Projection.md) onto $\large x$, which we call $\large y_p$:

$$\Large y_p=|y|\cos{\theta}$$

Once we have the length of the projection, the dot product is:

$$\Large x \cdot y = |x|\, |y| \cos \theta $$

![](../z_images/Pasted%20image%2020230305172741.png)

#### Or:
There is another way:
$$\Large \begin{bmatrix}x_1\\x_2\\x_3\end{bmatrix} \cdot \begin{bmatrix}y_1\\y_2\\y_3\end{bmatrix}=x_1y_1 + x_2y_2 +x_3y_4$$

## Why are those two ways the same thing?

BECAUSE, imagine if we use a tasformation with only one dimension for 2D vectors.

$$\Large t = \begin{bmatrix}\;2 & 1\;\end{bmatrix}$$

Now, with this transformation, the span of the system becomes a line, because both unit vectors are on the same dimension.

![](../z_images/Pasted%20image%2020230305175829.png)

So if we put any vector through this transformation, it will go along this line.

Since the components of our vector are adding value to the same dimension, for us to obtain our output vector, we just need to sum its components:

![](../z_images/Pasted%20image%2020230305180047.png)

So the new vector/scalar is -2. 
And we can see that applying the transformation to the vector is the same operation that we described before.
In the first way, we are taking the [norm](Norm.md)/magnitudes of each vector and comparing them in one dimension. 
In the second way we are collapsing everything in one single dimension(the one of the first vector), then the other vector will automatically project onto the dimension.

	TO BE REVISED!

```ad-important
title: How is this useful?

BECAUSE, the dot product lets you see if two vectors are similar.
In fact, if two vectors are generally going in the same direction, the dot product will be positive and  big.
> ![](../z_images/Pasted%20image%2020230305173452.png)

On the contrary, if the vectors are dissimilar, the dot product will be smaller.
If the two vectors are perpendicular, the $\large\cos\theta$ will return 0, and the dot product will be 0:

> ![](../z_images/Pasted%20image%2020230305172918.png)

If the two vectors are going in opposite directions, the dot product will be negative.
> ![](../z_images/Pasted%20image%2020230305173626.png)
```

```ad-info
Order doesn't matter, we can take the projection of either one of the two vectors and the dot product will stay the same.
```

```ad-info
Works only if you want to compare vectors that are in the same vector (dimensional) space.
```

```ad-warning
We must know this very well!
```

```ad-tldr
title: GPT Explanation
So, the inner product is essentially a way of measuring the similarity or correlation between two vectors. If the vectors are similar, meaning their corresponding components are aligned in a similar direction, the inner product will be a large positive value. If the vectors are dissimilar, meaning their corresponding components are pointing in different directions or canceling each other out, the inner product will be smaller, possibly negative.
```

```ad-info
title: Norm
What is the [norm](Norm.md) of a vector?

**The length of the vector** is referred to as the vector norm or the vector's magnitude.
```



## Outer product:
