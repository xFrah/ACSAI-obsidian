The binomial distribution models the probability of getting $k$ successes in $n$ independent trials of a [bernoulli distribution](Bernoulli%20distribution.md) setting.

$\large \mathbb{P}(k)$ gives the probability of getting exactly $k$ successes in the trials.

$$\large\mathbb{P}(k)=\begin{pmatrix} 
n\\k\end{pmatrix}p^k(1-p)^{N-k}$$
Where:
- $\begin{pmatrix}n\\k\end{pmatrix}$ are the subsets without ordering, so the number of ways that we can make a subset of $k$ elements from $n$ trials.
- 