## Perceptron

![](../z_images/Pasted%20image%2020240204194848.png)

The $\hat{y}$ symbol represents the prediction.
$10x_1 - 30x_2 + 20 = 0$ is the function that defines the line of the perceptron classifier.

> [!example]
> ![](../z_images/Pasted%20image%2020240204203826.png)


The formula for a 2 word classifier is $ax_1 + bx_2 + c = 0$, where:
- $a$ is the weight of word 1. (10 in this case)
- $b$ is the weight of word 2. (30 in this case)
- c is the bias. (20 in this case)

> [!summary] Activation Function "step"
> ![](../z_images/Pasted%20image%2020240204195138.png)


In this instance, a positive result would be turned to 1 by the activation function, and a negative one to 0.


### The perceptron trick

We are talking about a method to train the perceptron.
There are 2 cases:
- If a point is correctly classified: do nothing.
- If a point is incorrectly classified, move the line towards that point by changing the weights and bias.

![](../z_images/Pasted%20image%2020240204215952.png)

> [!example]
> ![](../z_images/Pasted%20image%2020240204220617.png)
> ![](../z_images/Pasted%20image%2020240204220729.png)

---

## Word2Vec

We represent each word in the dictionary with a vector(of variable dimensions).

![](../z_images/Pasted%20image%2020240204232528.png)

> [!summary] Notation
> - The expression $V(x) - V(y)$ computes the vector difference between $V(x)$ and $V(y)$, resulting in a new vector that points from $V(y)$ to $V(x)$.
> - $||...||$ denote the "norm" of a vector, AKA the vector's length.


### Cosine Similarity

Another way to measure how similar two vectors are, but this time it's based on the angle and not the vectors length.

![](../z_images/Pasted%20image%2020240204235349.png)

> [!example]
> ![](../z_images/Pasted%20image%2020240204235410.png)


### How to find the embeddings

We build a neural network to solve the following problem:

![](../z_images/Pasted%20image%2020240205000428.png)

#### The architecture

![](../z_images/Pasted%20image%2020240205001647.png)


The following is the architecture for skipgram, which has all the possible words in the first and last layer, each word has its own neuron:

![](../z_images/Pasted%20image%2020240205001701.png)

#### On what data do we train?

We just make a sliding window on a text and we label as 1 the words that appear and 0 the words that don't appear.

![](../z_images/Pasted%20image%2020240205001522.png)

> [!important] Lil problem
> ![](../z_images/Pasted%20image%2020240205002454.png)

