---
alias: Gini, Gini impurity, Missclassification
---

Measures impurity given a set of labels. They tell you how pure a set is.


We will cover a few impurity functions:
- Missclassification
- Gini Index
- [Entropy](Entropy.md)

---

## Missclassification

A few definitions:

- $K \leftarrow$ number of classes 
- $k\leftarrow$ a specific class
- $S \leftarrow$ set of data points
- $S_k \leftarrow$ points with label k
- $p_k=\large \frac{\left | S_k \right |}{\left | S \right |}\leftarrow$ the probability of picking a point with label $k$


The formula for Missclassification is:
$$\large H(S) = 1 - \max_k(p_{k})$$
The lower the missclassification is, the better.

```ad-hint
title: Formula explanation
It gives you the complement of the probability of picking the most probable label.

Or the probability of not picking the most probable class.

<br>

Some examples:

- impurity = 0: the set is pure, every point belongs to the same label.
- impurity = 1: the most probable label has 100% probability of not being picked, which means that every point has a different label. **I'M REALLY NOT SURE ABOUT THIS ONE**
```

```ad-example

Consider that $\large p_{red}=\frac{3}{4}$ and $\large p_{blue}=\frac{1}{4}$.

<br>

![](../z_images/Pasted%20image%2020230502145426.png)

<br>

Then Missclassification:
$$\large H(S) = 1 - \max(p_{k}) = 1-\max\{\frac{3}{4},\frac{1}{4}\} = \frac{1}{4} = 25\%$$

<br>

Let's do another example with 3 classes,

Consider that $\large p_{red}=\frac{2}{4}$ and $\large p_{blue}=\frac{1}{4}$ and $\large p_{green}=\frac{1}{4}$.

<br>

![](../z_images/Pasted%20image%2020230502150217.png)

<br>

Now the missclassification is:

$$\large H(S) = 1 - \max(p_{k}) = 1-\max\{\frac{2}{4},\frac{1}{4},\frac{1}{4}\}=50\%$$
```

---

## Gini impurity

The definitions are the same as before:

- $K \leftarrow$ number of classes 
- $k\leftarrow$ a specific class
- $S \leftarrow$ set of data points
- $S_k \leftarrow$ points with label k
- $p_k=\large \frac{\left | S_k \right |}{\left | S \right |}\leftarrow$ the probability of picking a point with label $k$

The formula for Gini Impurity is:
$$\large G(S)=\sum_{k=1}^{K}p_k(1-p_k)$$

```ad-hint
title: Formula explanation
For each class $k$, we multiply the probability of picking k($p_k$) and its complement(the probability of not picking k). Then we are summing the results.
```

---

## [Entropy](Entropy.md)

It describes the degree of confusion in the set.

$$\large H(X) \doteq -\sum_{x \in X} p(x)\log_2 p(x)$$
---
