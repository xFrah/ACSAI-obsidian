- Initialization step: we take K random centroids from the space.
- Assignment step: For each point, we compute the distance to the k random centroids, the point now belongs to that centroid. The assignments can move but the centroids are fixed.
- Update step: Now the assignments are fixed but the centroids can move. We loop over the centroids. Given $\large \mu_k$ we update it as 
$$$$

among all the points that we have, just consider k = one of the clusters, we are just selecting the set of points that belongs to that cluster.
We are summing all that and dividing by the cardinality.
So we are calculating a new mean for the cluster/centroid.

repeat?