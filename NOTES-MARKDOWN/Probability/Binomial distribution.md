The binomial distribution models the probability of getting $k$ successes in $n$ independent trials of a [bernoulli distribution](Bernoulli%20distribution.md) setting.

$\large \mathbb{P}(k)$ gives the probability of getting exactly $k$ successes in the $n$ trials.

$$\large\mathbb{P}(k)=\begin{pmatrix} 
n\\k\end{pmatrix}p^k(1-p)^{N-k}$$
Where:
- $\begin{pmatrix}n\\k\end{pmatrix}$ are the subsets without ordering.

> [!example]
> We have $n$ trials with 2 possible outcomes, we want to get the number of ways that this can go.
> If order mattered, we would do $2^n$, but order doesn't matter here because we just want to count the wins, not how the wins are distributed.
> For example for 3 trials, n would be all the possible combinations '**HHH**', '**HHT**', '**HTT**', '**TTT**', '**TTH**', '**HTH**', '**THT**', '**THH**'. Now we want to get the number of ways we can get exactly 2 **H**'s.
> - '**HHH**' - No
> - '**HHT**' - *Yes*
> - '**HTT**' - No
> - '**TTT**' - No
> - '**TTH**' - No
> - '**HTH**' - *Yes*
> - '**THT**' - No
> - '**THH**' - *Yes*
>   
>   Basically 3 combinations out of 8 give us the exact number of heads.

- $p^k$ is the probability of winning $k$ times

> [!example]
> By multiplication rule, in this case its:
> $$\large \mathbb{P}(H) \cdot \mathbb{P}(H) \cdot \mathbb{P}(H)=0.5\cdot 0.5\cdot 0.5= p^3$$

- $(1-p)^{n - k}$ is the probability of losing the remaining trials, since we did $k$ out of $n$ trials.

> [!example]
> By multiplication rule, in this case its:
> $$\large \mathbb{P}(T)\cdot\mathbb{P}(T)=0.5\cdot 0.5=(1-p)^2$$

> [!hint] wtf?
> Basically, in order:
> - First, we get the **number of ways** in which **this scenario happens**.
> - Second, we get the **probability of this happening**:
> 	- $p^k$ is the part where we get the probability of the $k$ wins;
> 	- $(1-p)^{n-k}$ is the part where we get the rest of the probability.
> 	  *Since we know that it doesn't matter the order in which we multiply them, we also know that the order here really doesn't matter at all.*

> [!faq]
> You may ask yourself: **aren't all the scenarios equally likely?**
> In my examples, yes. But what if heads has probability 0.7?
> Then the scenario in which we get all tails is far less likely.
