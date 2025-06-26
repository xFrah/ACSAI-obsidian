The entropy describes the degree of confusion in the set.
Another way you can think of it, is that entropy describes how surprised we are when we pick a value from the set. (You wouldn't be very surprised if a dice had only 6s in it)

$$\large H(X) \doteq -\sum_{x \in X} p(x)\log_2 p(x)$$

> [!hint] Formula explanation
> Suppose we have a function $h(x)$ we call surprise, that measures our surprise if the label $x$ is picked.
> 
> - $p(x) = 1$ we want $h(x)=0 \rightarrow$ **[Boring] NO surprise, a very common event happens**
> - $p(x) \rightarrow 0$ then $h(x)=\infty\rightarrow$ **[Excitment] Lots of surprise, a rare event happens**
> 
> This can be achieved if we set $\large h(x)$ to $\large\log_2 p(x)$:
> 
> ![](../z_images/Pasted%20image%2020230504151116.png)
> 
> Since we are dealing with probabilities, $\large p(x)$ will always be in [0, 1], so every value we feed to the log will come out negative.
> 
> We can see that the lower the probability for a label is, the more negative the log result will be:
> 
> ![](../z_images/Figure_1oidjgkerjg.png)
> 
> Now we may have the surprise for each label, but we want to compute the average surprise for every trial.
> 
> We can do just that by computing the [[Expected value|Expectation]] for the $h(x)$ distribution:
> 
> $$\large E[h(x)] = \sum_{x \in X} p(x)h(x) = \underbracket{\sum_{x \in X} p(x)\underbracket{\log_2 p(x)}_{\text{h(x) or surprise}}}_{\text{Expected value of h(x)}}$$
> 
> This average surprise measure, or the expectation of $h(x)$ is exactly what entropy is.

> [!hint] Why the [logarithm](../Calculus/5.%20Logarithms.md)?
> We can also use something else, but log is cute because it gives high values to lower probability events.

> [!hint] Another way to think about it
> Basically the log is just remodeling the [probability distribution](../Probability/Probability%20distributions.md) by giving low probabilities high values, and then we sum everything.
> 
> ![](../z_images/Figure_1oidjgkerjg.png)
> 
> So the entropy score represents how many rare events there are and how rare thy are. The rarer they are, the more they matter.

> [!example]
> 
> ![](../z_images/Pasted%20image%2020230504142832.png)
> 
> Here the entropy of A is lower than the entropy of B.
> 
> A) ![](../z_images/Pasted%20image%2020230504143542.png)
> 
> B) ![](../z_images/Pasted%20image%2020230504143601.png)
> 
> 

---


```ad-seealso
title: Useful links for a better understanding
https://randompearls.medium.com/information-theory-rationale-behind-using-logarithm-for-entropy-335d8e942e53
```
