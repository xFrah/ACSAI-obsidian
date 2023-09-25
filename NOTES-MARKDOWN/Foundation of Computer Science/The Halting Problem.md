Given a program $P(x)$ we must prove that it always terminates.

We set $P$ to:

$$\large \text{If K(x) terminates then loop-forever else True}$$

We set $x$ to $P(y)$, and use $P(P(y))$:

- If $P(y)$ terminates, then $P(P(y))$ doesn't terminate.
- If $P(y)$ doesn't terminate, $P(P(y))$ can't terminate either because we are stuck in the loop of $P(y)$.



> [!hint]
> You can't even enter the outside function if the first one doesn't terminate. You just can't continue.

> [!tldr]
> There are problems that can't be formally be proven true, a machine can't solve them.
