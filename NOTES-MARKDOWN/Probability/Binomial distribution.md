The binomial distribution models the probability of getting $k$ successes in $n$ independent trials of a [bernoulli distribution](Bernoulli%20distribution.md) setting.

$\large \mathbb{P}(k)$ gives the probability of getting exactly $k$ successes in the $n$ trials.

$$\large\mathbb{P}(k)=\begin{pmatrix} 
n\\k\end{pmatrix}p^k(1-p)^{N-k}$$
Where:
- $\begin{pmatrix}n\\k\end{pmatrix}$ are the subsets without ordering.

> [!example]
> We have $n$ trials with 2 possible outcomes, we want to get the number of ways that this can go.
> If order mattered, we would do $2^n$, but order doesn't matter here because we just want to count the wins, not how the wins are distributed.
> For example for 3 trials, n would be all the possible combinations 'HHH', 'HHT', 'HTT', 'TTT', 'TTH', 'HTH', 'THT', 'THH'. Now we want to get the number of ways we can get exactly 2 H's.
> - 'HHH' - No
> - 'HHT' - Yes
> - 'HTT' - No
> - 'TTT' - No
> - 'TTH' - No
> - 'HTH' - Yes
> - 'THT' - No
> - 'THH' - Yes
>   
>   Basically 3 combinations out of 8 give us the exact number of heads.

- #### Fuck this shit, WIP