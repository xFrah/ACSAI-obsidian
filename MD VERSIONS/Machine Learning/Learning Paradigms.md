1. Supervised Learning (We have labels)
2. Unsupervised Learning (We do NOT have labels)


## Supervised Learning
Assume we have a generator that follows an unknown probability distribution D over inputs (x, y).

x corresponds to the image.
y corresponds to the label.

So you get_prob_under_D(x, y) returns the probability of the pair.


#### Bayes optimal classifier:

- For any test input x' it returns the y' that maximizes get_prob_under_D(x, y)

$$\Large h(\mathbf{x}') = \underset{y\in\mathcal{Y}}{\operatorname{argmax}}\ p(Y=y\mid\mathbf{X}=\mathbf{x}')$$

##### Goal:
Given a training set with labels, we learn a function over a set of possible funtions.
The output of the learning is h() that can be used to do predictions.

Given a training dataset of paired (x, y), we learn to predict the label when given as input unseen data.
- Classification the output is a discrete value(category)
- Regression: The output is a continuous value.

![](../z_images/Pasted%20image%2020230228143731.png)


## Unsupervised Learning:

We drop the label. We don't have any labels paired with the data.
It works by creating an internal representation of the input, capturing regularities/structures in the data.

Examples: 
- Form clusters
- Extract features

## Clustering

When you have point clouds with different shapes.
The goal here is to group the data based on similarities.

![](../z_images/Pasted%20image%2020230228143343.png)

