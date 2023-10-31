The goal is to represent each word of the english language by a vector in $\mathbb{R}^d$ with d being an hyperparameter(set by us.)

> [!example]
>$$\large \text{Bob} \rightarrow \begin{bmatrix}
0.2 \\ 0.5 \\ -10 \\ -1 \\40
\end{bmatrix}$$ 
> These dimension can convey information about the word.


## Why is it cool

1) If word x and word y have similar meanings, then $||V(x) - V(y)||$ is small.
2) If x and y have opposite meanings, then $||V(x)+V(y)||$ is small.
3) Some relations between words are preserved.