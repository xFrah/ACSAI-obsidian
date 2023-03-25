Many algorithms in machine learning consist in optimizing the parameters of a function to best fit a model, which will ultimately do inference on the data.

To make this optimization process possible, we exploit gradient information.


```ad-seealso
title: Function notion
A function $\large f$ is a quantity that relates two quantities to each other.

<br>

These two quantities are:
- Inputs: $\;\large x \in \mathbb{R}^D$
- Targets: $\;\large f(x)$

<br>

Where:
- $\large\mathbb{R}^D$ is the domain of $\large f$. *(set of all possible input values)*
- Function values $\large f(x)$ are the image/codomain of $\large f$. *(set of all possible output values)*

<br>

Notation:
$\large f: A \rightarrow B$

The notation indicates that the function takes an input from set $A$ and maps it to an output in set $B$.

- $\large f$ is the name of the function
- $A$ is the domain of the function
- $B$ is the co-domain of the function
```



Takes a vector and outputs a scalar. It generally computes our loss.

STUDY FUCKING PARTIAL DERIVATIVE

The scalars of the vector are telling us what is the effect of perturbation on x on their. axis. Like a derivative, but this is a partial derivative because we are making constant every other variable and shifting only one.

Think of it as a direction. It is the direction of steepest ascent. The direction to change the input so that the function values goes up oin [x, x+e] 

It outputs the direction you shouuld go to get the highest increase in value.

Given that you want to minimize a loss function, you need the direction of steepets descent, -gradient.


