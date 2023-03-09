The probability is the relative frequency in the long run. 

- Each outcome in a sample space has a probability between 0 and 1.
- The sum of all the individual probabilities equals 1.


## Classical rule

If all the outcomes are equally likely to occur, we say that they all have the same probability:

$$\Large \frac{1}{n}$$

## Probability of an [event](Event.md)

It is obtained by adding up all the individual probabilities of each outcome in the event.
If the events are equally likely to occur, the formula is:

$$\large P(A) = \frac{|A|}{|\omega|}$$

Where:
- $\large |A|$ is the number of outcomes in A.
- $\large |\omega|$ is the number of total possible outcomes.


## Conditional probability

Assume we have events A and B. The probability of A occurring given that B has occurred is:

$$\large P(A\,|\,B) = \frac{P(A \cap B)}{P(B)}$$


```ad-hint
title: Why?
A = carte pari
B = figure

Immaginiamo di pescare una carta, vediamo che è una figura ma non vediamo il numero.
Il nostro outcome space diventa le figure, quindi se ci sono 12 figure.

Se la formula è 
$$\large P(A) = \frac{|A|}{|\omega|}$$

allora in questo caso il nostro omega sono le figure, la formula diventa:
$$\;$$
$$\large P(A) = \frac{|figure| \cap |pari|}{|figure|}$$
```


## Multiplication rule

Assume we have events A and B. The probability that they both occur is given by:

$$\large P(A\; and \; B) = P(A\,|\,B)\; × \; P(B) \quad or \quad P(B\,|\,A)\; × \; P(A)$$


## Indipendent events

Events A and B are indipenden if at least one of these conditions is true:
- $\large P(A\cap B) = P(A) × P(B)$
- $\large P(A\,|\,B) = P(A)$
- $\large P(B\,|\,A) = P(B)$


