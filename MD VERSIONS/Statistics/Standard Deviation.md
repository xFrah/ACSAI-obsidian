Measures <span style="background:rgba(183, 152, 255, 0.3)">how much dispersed the data is in relation to the mean</span>.

$$ \Huge\sigma = \sqrt{\frac{\sum(x_i - \mu_x)^2}{N}}$$

Where:
- **Xi** – a point X.
- **μX** – the mean of X.

---

## Computing Standard Deviation

Standard deviation is calculated as follows:

1.  Calculate the [[Mean]] of all data points.
2.  Calculate the [[Variance]] for each data point.
3.  Square the variance of each data point <font color="#7f7f7f">(from Step 2)</font>.
4.  Sum of squared variance values <font color="#7f7f7f">(from Step 3)</font>.
5.  Divide the sum of squared variance values <font color="#7f7f7f">(from Step 4)</font> by the number of data points in the data set less 1.
6.  Take the square root of the quotient <font color="#7f7f7f">(from Step 5)</font>.


```ad-hint
Why?

We are taking the <span style="background:rgba(183, 152, 255, 0.3)">average of the distances from the mean for each point</span>.
But, we square the distances so that they are always positive, then we sqrt everything to get the correct unit of measurament.

I'm positive that this is correct, tho I'm not 100% sure.
```
