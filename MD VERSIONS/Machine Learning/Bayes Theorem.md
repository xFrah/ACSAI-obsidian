![](../z_images/Pasted%20image%2020230410202840.png)

We have two boxes:
- The red box, which contains 6 oranges and 2 apples.
- The blue box, which contains 1 orange and 3 apples

Probabilities for the boxes, assume that:
- We pick the red box 40% of the time
- We pick the blue box 60% of the time

Input: The type of fruit
Output: The box from which it has been picked


### How do we solve this?

In order to find the probability of the event red box given the event orange, we just use conditional probability as usual.


```ad-example
![](../z_images/Pasted%20image%2020230413142348.png)

<br>

As you already know, the probability of A given B is given by their intersection divided by the new sample space which is B.

<br>

$$\large P(A\vert B)=\frac{P(A \cap B)}{P(B)}$$
```


Consider that we already know the probability of getting the red box, the probability of getting an orange and the probability of the intersection between the two events. {vergonya}

$$P(Red \; box \,|\, Orange ) = \frac{P(Orange\,|\,Red\; box) \cdot P(Red \; box)}{P(Orange)} = \frac{P(Orange\, \bigcap \, Red \; box)}{P(Orange)}$$

In this case:
- $P(Red \; box) = 0.4$
- $P(Blue \; box) = 0.6$
- $P(Orange) = \frac{6}{8} * 0.4 + \frac{1}{4} * 0.6$ 
	- Because 6 out of 8 fruits in the red box are oranges, and the red box has probability 0.4.

So:


```ad-seealso
title: Useful links for a better understanding
https://stats.stackexchange.com/a/239042
```
