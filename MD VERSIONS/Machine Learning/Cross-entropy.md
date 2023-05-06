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
###### What is the exact difference with entropy?

### Coming soon

```
