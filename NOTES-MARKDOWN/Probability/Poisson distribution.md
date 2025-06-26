Used for when we have an event that occurs $\lambda$ times in a fixed time or space.
The poisson distribution models how probable it is that the event occurs $k$ times (instead of $\lambda$).

- $\lambda$ is the average number of [events](Events.md) occurring in the interval.
- $k$ is the number of events that we want the probability of, instead of $\lambda$.

$$\large P(k) = \frac{λ^k \cdot e^{-λ}}{!k}$$

- $\lambda^k$ is the probability that the event
- $e^{-λ}$ is a normalizing factor that ensures the probabilities sum to 1
- $!k$ is a normalizing factor too, it accounts for the events that are indistinguishable from each other because of the different orderings.

> [!hint] Poisson distribution with $e^{-\lambda}$ vs without
> ![](../z_images/Pasted%20image%2020240923110037.png)
> 
