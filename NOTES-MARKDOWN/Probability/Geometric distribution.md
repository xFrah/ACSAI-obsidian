Models the probability of obtaining the first success in a series of bernoulli trials.

The geometric distribution models the probability of getting the first success on the kth trial in a sequence of independent Bernoulli trials.

P(k) gives the probability that the first success occurs on the kth trial.

$$\large P(k) = (1-p)^{(k-1)} * p$$

Where:

- $p$ is the probability of success on each trial
- $k$ is the number of trials until the first success occurs

> [!example] 
> We look at this case:
> 
> - 1st cast: Fail
> - 2nd cast: Fail
> - 3rd cast: Success
>   
> What's the probability of this?
>
> - $(1-p)^{(k-1)}$ represents the probability of failing all trials before the kth trial.
> $$\large P(F)\cdot P(F)$$
> - $p^k$ is the remaining part, which is the probability of getting a success with the last trial.
>   $$\large P(S)$$
>   
>   And all together:
>   $$\large P(F)\cdot P(F) \cdot P(S)$$

![](../z_images/Pasted%20image%2020240921211638.png)