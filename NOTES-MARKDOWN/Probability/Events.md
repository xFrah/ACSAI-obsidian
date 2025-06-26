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

---

## Probability measure

A function that maps a probability to events.

$$\large P : \mathcal{F} → [0, 1]$$
> [!note]
> $\mathcal{F}$ contains all the subsets of $\Omega$(so all events). It is the set of all observable events.

Probability measures must respect these conditions:
- $P(Ω) = 1$
- For any sequence of disjoint events(*cannot occur simultaneously*):

$$\large \mathbb{P}\left(\bigcup_{i=1}^n A_i\right)=\sum^n_{i=1}\mathbb{P} (A_i)$$

> [!hint]
> The probability of united events must be equal to the sum of the probabilities of the individual events.

---

## Event independence

Events A and B are indipendent if at least one of these conditions is true:

- $\large P(A\cap B) = P(A) × P(B)$
- $\large P(A\,|\,B) = P(A)$
- $\large P(B\,|\,A) = P(B)$

> [!hint]
> A = carta fiori, $\mathbb{P}(A) = \frac{13}{52}$
> B = carta nera, $\mathbb{P}(B) = \frac{26}{52}$
> 
> $$\large \mathbb{P}(\text{pescato e rimosso carta fiori e nuovamente pescato carta nera)} = \frac{13}{52} * \frac{25}{52}$$
> $$\large\frac{13}{52} * \frac{25}{52}\neq \frac{13}{52} * \frac{26}{52}$$

---

## Equally likely outcomes

When all the outcomes are equally likely, the probability of an event depends on the number of outcomes in the event.

$$\large \mathbb{P}(A)=\frac{|A|}{|\Omega|}$$

> [!hint]
> $$\large \mathbb{P}(A\cup B)=\mathbb{P}(A)+\mathbb{P}(B)- \mathbb{P}(A∩B)$$
> 
> The probability of their intersection would be counted twice if we didn't remove it once.
