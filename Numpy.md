Vectorizing: Avoiding loops.

We create a matrix:

```
x = np.array([[2.5, 3.2], [0, 1], [2, -3]], dtype=np.float32)

print(x) 
print(f"Shape {x.shape}") # the shape is... 
print(f"Number of dimension: {x.ndim}") # is a matrix (2 axis) 
print(f"Number of elements: {x.size}") # with 6 elements 
```
Output:

```
[[ 2.5 3.2]
[ 0. 1. ]
[ 2. -3. ]]
Shape (3, 2)
Number of dimension: 2
Number of elements: 6
```


We plot a diagonal matrix:

```
A = np.diag(np.ones(3)) # firstly create a vector [1,1,1] and then makes it a diagonal matrix 
print(A)
```
Output:

```
[[1. 0. 0.]
[0. 1. 0.]
[0. 0. 1.]]
```


We plot a [[../Linear Algebra/Vectors|vector]]:


```
import matplotlib 
import matplotlib.pyplot as plt 
import numpy as np 

v = np.array([2.5, 3.2]) # all the X first, then all the Y 
# [X1 X2] [Y1 Y2] 
plt.plot([0, v[0]], [0, v[1]], marker='x', color='red', lw=4, markersize=6)
```
Output:

![](../z_images/Pasted%20image%2020230228151003.png)



```ad-important
Generally, operations are element wise, unless specified.
```


what's opencv-contrib-python? its fucking legacy features and patented code?

np.random.seed: its the seed that np.random uses to generate random numbers

you can do this apparently: arr[::-1, ::-1] to flip vertically and horizontally a 2D matrix.

If you select a slice out of the matrix, the new object will not be a mere copy, but a reference to the real objects. I THINK.