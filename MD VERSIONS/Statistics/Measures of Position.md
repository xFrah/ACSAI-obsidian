## Percentile

Percentile The $p^{th}$ percentile is a value such that $p$ % of the observations fall below or at that value.

![](../z_images/Pasted%20image%2020230301155850.png)

## Quartiles

The Quartiles split the distribution into <span style="background:rgba(183, 152, 255, 0.3)">four parts that have the same number of observations</span>:
- 25% is below the first quartile (Q1), 
- 25% is between the first quartile and the second quartile (the [median](Median.md), Q2), 
- 25% is between the second quartile and the third quartile (Q3), and 
- 25% is above the third quartile.

![](../z_images/Pasted%20image%2020230301160048.png)

The procedure to find them is:
- Arrange the data in order. 
- Consider the median. This is the second quartile, Q2. 
- Consider the lower half of the observations (excluding the median itself if n is odd). The median of these observations is the first quartile, Q1. 
- Consider the upper half of the observations (excluding the median itself if n is odd). Their median is the third quartile, Q3.

```ad-important
It is not the range that we are dividing, but the observations

In fact, not all quartiles are equal in x range.
```


## Interquartile Range (IQR)

It is the distance between the third quartile and first quartile.

$$\Large Q3 - Q3$$


```ad-info
Useful for detecting outliers. 

In fact, an observation is a potential outlier if it falls more than 1.5×IQR below the first quartile or more than 1.5×IQR above the third quartile.‎
  ‎‎
 
  ‎‎
![](../z_images/Pasted%20image%2020230301162351.png)

```
