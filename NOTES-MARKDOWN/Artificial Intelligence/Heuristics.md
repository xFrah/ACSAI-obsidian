---
alias: Heuristic
---
A heuristic function returns the apparent distance from a node to the destination, or the apparent cost.

It is nothing but a kind of **smart guess**. We really don’t know the actual distance until we find the path.

We actually could calculate the exact value of h, but that would be time consuming.
For this reason we turn to approximations, an example is the manhattan distance:

```
 h = abs (current_cell.x – goal.x) + abs (current_cell.y – goal.y)
```

![](../z_images/Pasted%20image%2020230317154434.png)
