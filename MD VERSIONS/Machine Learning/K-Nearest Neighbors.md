Whenever you get new data point, you assign it the label of the k closest points in the dataset.
This is so simple that i'm not wasting time for these notes yet.

---

## Distances problem

KNN treats every feature with the same regard.
The dimensions all have the same weight, but some of them may be more important than others.

---

## Feature Normalization

?????

## High dimensional data may live in subspace

imagine a circle, and that the distance between two points in the circle isn't the actual euclidean distance in 2d, but its the distance along the circumference of the circle.

This is to say that often, the distance between two points is not well represented in the standard dimensional space.

This is why we need normalization.

?????

WHAT THE FUUUUCK

[PCA](PCA.md) in this environment would not work well, this is why we do something called local pca.
Local pca estimates a local tangent space on the non linear point clouds.

```ad-hint
If we applied the pca to the whole point cloud(to estimate a plane/unrwap the shape) it would not be accurate(kinda like taking the derivative with $\Delta x$ being very large).
```


This is related to knn because we use it to get where to apply the local pca to get the tangent plane.

We could also unwrap the shape into a kind of plane but we won't do that.


## Advantages and disadvantages of KNN

TODO