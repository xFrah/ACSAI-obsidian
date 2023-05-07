Cross-entropy is commonly used to quantify the difference between two probability distributions.
It is used in machine learning to estimate the loss/error for categorical multi-class classification.

The formula for cross-[[impurity functions|entropy]] is:
$$\large H(x) = -\sum_{x \in X} p(x)\log q(x)$$
Where:
- $\large q(x)$ - predicted probability of label
- $\large p(x)$ - true probability of label
- $\large \log q(x)$ - surprise of the predicted label

```python
import numpy as np

# assume we are predicting a label for an instance

p = np.array([0, 1, 0])             # True probability (one-hot)
q = np.array([0.228, 0.619, 0.153]) # Predicted probability

cross_entropy_loss = -np.sum(p * np.log(q))
print(cross_entropy_loss)
# 0.47965000629754095
```

```ad-hint
title: Formula explanation
Imagine that we have a distribution P(x) and a distribution Q(x).

- $h(x)=\log p(x)$ is the number of bits required to represent the event x in distribution P.
- $h(x)=\log q(x)$ is the number of bits required to represent the event x in distribution Q.

<br>

When we compute entropy of P(x), we are getting the average number of bits that are used to represent any event x in P:
- The weights/frequencies of events is given by P(x)
- The actual number of bits for any of these events is given by $\log p(x)$.

<br>

Here we have the P(x) distribution in red and its $\log p(x)$ in blue:

<br>

![](../z_images/Figure_1dfdfgdfg.png)

<br>

You can see that the less probable an event x is, the more information(surprise, given by $\log p(x)$) is needed to represent it.

<br>

Now imagine that we have the number of bits for any event x determined by the same distribution, but the distribution/frequency of events changes. That basically changes the average cost per event x.

<br>

![](../z_images/Figure_asdasdasd1.png)
```
