We shouldn't think of it as a list of scalars.

![](../z_images/Pasted%20image%2020230228151744.png)

## Interpretation:
- n column [[Vectors recap|vectors]] in a real-valued M-dimensional space.
- m row vectors in a real-valued N-dimensional space.

## Identity/Diagonal Matrix:

![](../z_images/Pasted%20image%2020230228151814.png)

We plot a diagonal matrix with [numpy](../Computer%20Vision/Numpy.md):

```
#help(np.diag) 
A = np.diag(np.ones(3)) # firstly create a vector [1,1,1] and then makes it a diagonal matrix 
print(A)
```
Output:

```
[[1. 0. 0.]
[0. 1. 0.]
[0. 0. 1.]]
```


## Symmetrical matrix:

A matrix is simmetrical if??? ARE YOU SURE???

$$\Large A = A^T$$

1.  $(A^T)^T = A$: The transpose of a transpose matrix is the original matrix.
    
2.  $(A+B)^T = A^T + B^T$: The transpose of the sum of two matrices is equal to the sum of their transposes.
    
3.  $(AB)^T = B^T A^T$: The transpose of a product of two matrices is equal to the product of their transposes in reverse order.


## Trace of a matrix

The trace is the sum of the diagonal elements.

$$\Large\text{trace}(A) = \sum_{i} a_{ii}$$

## Reduction operations (sum across rows)
Rows will disappear.

```
print(A, end='\n\n') # Possible to do reduction on the matrix (sum along rows) 
A_c = A.sum(axis=0, keepdims=False) # 3 (rows are canceled out) 
A_c.shape print(A_c)
```
Output:

```
[[0 1 2]
[3 4 5]
[6 7 8]]

[ 9 12 15]
```

You flatten the axes, so you get something that is 1x3. You flatten the rows.
The axis where you do the operation is said to be flattened.

```ad-warning
Question of the exam about this!!

What is the geometric meaning of a point cloud and we want to translate it to the origin.

How do we translate this point cloud to the origin? We can compute the mean of the point cloud, in which dimensional space is this WHAT THE FUCK IS HE SAYING

We compute the mean of the point cloud and then we subtract it from all the point.
The new mean of the point cloud is 0.

For each point x and y, we subtract the meanX and meanY. (x, y) - (meanX, meanY)

```

```ad-tip
Hamaard multiplication: We do multiplications element wise. In python, it is done by the operator "*", between matrices.
```

## Inner product (Dot product)
