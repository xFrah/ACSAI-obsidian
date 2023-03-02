X is a high dimentional point in a vector space.

![](../z_images/Pasted%20image%2020230228145723.png)

Vectors are written column wise. We can make it row wise by transpising it.

![](../z_images/Pasted%20image%2020230228145737.png)

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


## Inner product (Dot product)

We must know this very well!
Works only if you want to compare vectors that are in the same vector (dimensional) space. 
It allows to compare vectors and project a vector into another?

The data is paired: just muliply elementwise and sum across axis

dot_product = x1y1 + x2y2 + x3y3 + x4y4

Geometrically, it's the length of the projection of one vector on the other.

## gpt explanation
We take the norm of the projection and we multiply with the norm of the other.

The norm of the vector v * norm of the vector w * cos(angle)


Imagine you have two vectors, let's call them $\mathbf{a}$ and $\mathbf{b}$. The inner product of these two vectors, denoted by $\mathbf{a} \cdot \mathbf{b}$, is calculated by multiplying the corresponding components of the two vectors and adding up the results. That is,

$$ \mathbf{a} \cdot \mathbf{b} = a_1 b_1 + a_2 b_2 + \cdots + a_n b_n $$

where $a_1$, $a_2$, $\cdots$, $a_n$ and $b_1$, $b_2$, $\cdots$, $b_n$ are the components of the vectors $\mathbf{a}$ and $\mathbf{b}$, respectively.

So, the inner product is essentially a way of measuring the similarity or correlation between two vectors. If the vectors are similar, meaning their corresponding components are aligned in a similar direction, the inner product will be a large positive value. If the vectors are dissimilar, meaning their corresponding components are pointing in different directions or canceling each other out, the inner product will be smaller, possibly negative.


## gpt geometric explanation

The inner product of these vectors, denoted by $\mathbf{a} \cdot \mathbf{b}$, is given by:

$$ \mathbf{a} \cdot \mathbf{b} = |\mathbf{a}| |\mathbf{b}| \cos \theta $$

where $|\mathbf{a}|$ and $|\mathbf{b}|$ are the magnitudes (lengths) of the vectors, and $\theta$ is the angle between the vectors.

Geometrically, the inner product is equal to the projection of one vector onto the other, multiplied by the magnitude of the other vector. In the diagram above, the projection of $\mathbf{a}$ onto $\mathbf{b}$ is given by the length of the blue line, which is equal to $|\mathbf{a}| \cos \theta$. Multiplying this by $|\mathbf{b}|$ gives the area of the rectangle, which is equal to $\mathbf{a} \cdot \mathbf{b}$.

Intuitively, when the angle between the vectors is small, the inner product is large, indicating that the vectors are similar in direction. Conversely, when the angle between the vectors is large, the inner product is small, indicating that the vectors are dissimilar in direction. If the angle between the vectors is 90 degrees, the inner product is zero, indicating that the vectors are orthogonal (perpendicular) to each other.

So, the inner product provides a geometric way to measure the similarity between vectors, based on the angle between them and their magnitudes.

```ad-hint
What is the norm of a vector?

**The length of the vector** is referred to as the vector norm or the vector's magnitude.
```



## Outer product:
