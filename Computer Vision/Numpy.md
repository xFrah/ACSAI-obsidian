Vectorizing: Avoiding loops.

We create a matrix:

```
import numpy as np 

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

We plot a [[Vectors recap|vector]]:


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


