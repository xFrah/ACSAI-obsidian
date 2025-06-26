When we have our outcome space partitioned by some disjoint [events](Events.md)...

![](../z_images/Pasted%20image%2020240711181120.png)

... this gives us a way to get the probability of events that are scattered through these partitions.

In the case of the image above, we want the total probability of getting a red ball after randomly picking from $A$, $B$ or $C$.

$$\large \mathbb{P}(\text{Red})=\mathbb{P}(\text{Red}\cap A)+\mathbb{P}(\text{Red}\cap B)+\mathbb{P}(\text{Red}\cap C)$$

And since we know that $\mathbb{P}(\text{Red}\cap A)=\mathbb{P}(\text{Red}|A)\mathbb{P}(A)$, the probability of getting a red ball is given by:

$$\large \mathbb{P}(\text{Red})=\mathbb{P}(\text{Red}|A)\mathbb{P}(A)+\mathbb{P}(\text{Red}|B)\mathbb{P}(B)+\mathbb{P}(\text{Red}|A)\mathbb{P}(C)$$
## General formula

$$\large \mathbb{P}(A) = \sum_i{\mathbb{P}(A\cap B_i)}$$

> [!example] Another example
> In a class of 40% males and 60% females, 60% of the males are taller than 6 feet and 10% of the females are taller than 6 feet.
> What percent of the class is shorter than 6 feet?
> 
> $$\large \mathbb{P}(<6_{ft})=\mathbb{P}(<6_{ft}\cap \text{male})+\mathbb{P}(<6_{ft}\cap \text{female})$$
> $$\large \mathbb{P}(<6_{ft})=\mathbb{P}(<6_{ft}|\text{male})\mathbb{P}(\text{male})+\mathbb{P}(<6_{ft}|\text{female})\mathbb{P}(\text{female})$$
> $$\large\mathbb{P}(<6_{ft})=0.4\cdot0.4+0.9\cdot0.6$$

---

> [!info] Sources
> https://www.youtube.com/watch?v=U3_783xznQI
