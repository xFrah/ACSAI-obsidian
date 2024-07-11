The set of possible **outcomes** is the **sample space**:

$$\large\Omega =\{w_1, w_2, w_3, \dots\}$$

A **subset of $\Omega$** is called an **event**.

$$\large A \subseteq \Omega$$

> [!example]  Toss a dice Example
> $\Omega = \{1, 2, 3, 4, 5, 6\}$
> Some events:
> - $\{5\}$ The outcome is 5
> - $\{2, 4, 6\}$ The outcome is even
> - $\{3, 6\}$ The outcome is divisible by 3

> [!note] Exclusion from the outcomes
> When describing an event that includes every outcome **except for one**, for example one number out of the set of real numbers $N$:
> 
> $$\{\text{the number is not 7}\} = N\; \backslash \;\{7\}$$

> [!note] Length of an event
> The length of an event is denoted by:
> $$\large |A|$$

> [!note] Interval events
> When describing an event from a continuous set, for example $[0, 1]$:
> $$\large \{x:\underbracket{x<\frac{1}{3}}_{\text{all x before }\frac{1}{3}}\} = \underbracket{[0, \frac{1}{3})}_{\text{x from 0 to }\frac{1}{3} \text{ (inclusive)}}$$
> 

> [!abstract] Countable vs Uncountable sets
> A set is countable if the number of outcomes in it is finite.
> And viceversa.


## Probability measure

A function that maps a probability to events.

$$\large P : \mathcal{F} → [0, 1]$$
> [!note]
> $\mathcal{F}$ contains all the subsets of $\Omega$(so all events). It is the set of all observable events.

[Probability measures](Probability%20measures.md) must respect these conditions:
- $P(Ω) = 1$
- For any sequence of disjoint events(*cannot occur simultaneously*):

$$\large \mathbb{P}\left(\bigcup_{i=1}^n A_i\right)=\sum^n_{i=1}\mathbb{P} (A_i)$$

> [!hint]
> The probability of united events must be equal to the sum of the probabilities of the individual events.

