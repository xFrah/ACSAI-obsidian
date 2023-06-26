---
alias: Cross-entropy Loss, CE Loss
---

It is commonly used to quantify the difference between two [[Probability distribution|probability distributions]] in the [Kullback-Leibler divergence](Kullback-Leibler%20divergence.md).
It is also used in machine learning to estimate the loss/error for categorical [multi-class classification](Multi-Class%20Classification.md).

The formula for cross-[[impurity functions|entropy]] is:

$$\large H(x) = -\sum_{x \in X} p(x)\log q(x)$$

> [!note] Surprise of an event
> The **more rare an event is**, the **more information it conveys**, and **the more surprise** there is when we it happens.
> 
> We can quantify the surprise of any event x as follows:
> 
> $$h(x)=\log P(x) \rightarrow \text{number of bits required to represent the event x in distribution P}$$
> 
> A practical example:
> - If you have a set of only 0s and you pick a 0, it doesn't tell you anything.
> - If you have a set full of 1s and just one 0, if you pick that zero it tells you a lot of information(and you are surprised!).
>   
> **Go further down for a visualization of this concept.**

> [!hint] Formula explanation
> 
> When we compute [entropy](Entropy.md) of P(x), we are getting the **average number of bits that are used to represent the events** in P:
> - The weight/frequency of event x is given by P(x)
> - The actual number of bits for any of these events is given by $\log p(x)$.
> 
> Here we have the P(x) distribution in red and its $\log p(x)$(number of bits to represent an event) in blue:
> 
> ![](../z_images/Figure_1dfdfgdfg.png)
> 
> You can see that the less probable an event x is, the more information(surprise, given by $\log p(x)$) is needed to represent it.
> 
> Now imagine that the distribution/frequency of events changes, while the number of bits necessary to represent each one of those events stays the same.
> 
> That basically **changes the resulting average cost per event x** for this configuration.
> 
> 
> ![](../z_images/Figure_asdasdasd1.png)
> 
> **The occurrence of events that needed a lot of bits to represent has now increased. **
> 
> And this is a big thing, because now the high h(x) is gonna get multiplied by the high p(x), and the cross-entropy is going to the moon.
> 
> So this <font color="#245bdb">encoding</font> is shit for this <font color="#c00000">distribution</font> of events.
> 

> [!hint] Some considerations
> Given the definition above, we should understand that the cross-entropy can never be lower than the entropies of the two single distributions.
> 
> This is because the bits for each event are modeled on a specific distribution, and that is the best you can do on it. 
> 
> When you change the distribution of events, it all goes to shit.

---

## Cross-Entropy as a loss function


```python
import numpy as np

# assume we are predicting a label for an instance

p = np.array([0, 1, 0])             # True probability (one-hot)
q = np.array([0.228, 0.619, 0.153]) # Predicted probability

cross_entropy_loss = -np.sum(p * np.log(q))
print(cross_entropy_loss)
# 0.47965000629754095
```


---


```ad-seealso
https://machinelearningmastery.com/cross-entropy-for-machine-learning/
```
