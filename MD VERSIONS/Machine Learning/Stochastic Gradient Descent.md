While classic [Gradient Descent](Gradient%20Descent.md) has to iterate through all the datapoints just to update the parameters once, Stochastic [Gradient](Gradient.md) Descent(SGD) will process only a small subset of the dataset and then update the parameters.

> [!hint] Difference between GD and SGD
> ### GD
> $$\large\theta \leftarrow  \theta -\gamma \sum_{i=1}^n \big(\underbracket{\theta^Tx_i- y_i\big)}_{\text{scalar}}\underbracket{x_i}_{\mathbb{R}^d}$$
> ![](../z_images/Pasted%20image%2020230525171924.png)
> ### SGD 
> $$\large\theta \leftarrow  \theta -\gamma  \big(\underbracket{\theta^Tx_i- y_i\big)}_{\text{scalar}}\underbrace{x_i}_{\mathbb{R}^d} \qquad \text{where}~ i\sim \mathcal{U}(0,n)|$$
> ![](../z_images/Pasted%20image%2020230525172014.png)


So the idea is to **update the parameters for each single training sample selected randomly:**

$$\theta \leftarrow  \theta -\gamma  \big(\underbracket{\theta^Tx_i- y_i\big)}_{\text{scalar}}\underbracket{x_i}_{\mathbb{R}^d} \qquad \text{where} \qquad  i\sim \mathcal{U}(0,n)$$

![](../z_images/Pasted%20image%2020230525165800.png)


> [!seealso] Useful links
> https://stats.stackexchange.com/questions/232056/how-could-stochastic-gradient-descent-save-time-compared-to-standard-gradient-de/232058#232058
