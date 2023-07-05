## TPR and FPR

Assume we are in a [logistic regression](Logistic%20Regression.md) setting.
We put a 0.5 threshold for the positive class...

![](../z_images/Pasted%20image%2020230704185229.png)


Of course, if we have a dataset, we can compute the True Positive Rate and the False Positive Rate:

![](../z_images/Pasted%20image%2020230704185706.png)


But, for example, if we lower the threshold, the amount of True positives will increase along with the amount of False Positives.

![](../z_images/Pasted%20image%2020230704190001.png)

> [!hint]
> Lowering the thresholds and increasing the number of False positives is sometime needed, when we cannot afford to output False negatives.


So how do we summarize all this information about how TPR and FPR change with the threshold value?

---


## The ROC curve

The ROC curve associates a threshold with its resulting True Positives and False Positives.
Each point of the curve is the result of a different threshold, for example **a threshold of 0 would result in the following point**:

![](../z_images/Pasted%20image%2020230704190502.png)


The important osservation is that the closer a point is to the top left corner(100% True positives, 0% False Positives), the better the threshold works for the model.

![](../z_images/Pasted%20image%2020230704191100.png)
![](../z_images/Pasted%20image%2020230704191204.png)

---


## AUC

Basically, if our model has a lot of points close to the top left corner, it's very good.
Another metric that we can use to check if our model/ROC is good, it's its area under the curve.

The larger the AUC is, the better the model.

![](../z_images/Pasted%20image%2020230704191353.png)