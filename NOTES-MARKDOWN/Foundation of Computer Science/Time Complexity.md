![[Pasted image 20250829161110.png]]

> [!hint]
> The time-complexity function $f:N→N$ maps each input length $n$ to the worst-case number of computation steps taken by the deterministic Turing machine $M$ that halts on all inputs.
> 
> The inputs to f are natural numbers n=0,1,2,… representing input lengths, not the strings themselves.
> 


Suppose $M$ decides whether a binary string contains at least one ‘1’ by scanning left to right, halting as soon as it finds a ‘1’ or reaches the end.

1. **Inputs of length nn:** All binary strings of length $n$.
2. **Worst-case input:** The string of all zeros, “000…0” (since $M$ must scan every symbol to confirm no ‘1’).
3. **Steps counted:** One step per symbol read plus one final halting step → roughly £n+1$.

Thus for this $M$:
$$\large f(n)=n+1$$

We say **“$M$ runs in time $n+1$”**.

> [!hint]
> $f(n)$ of $M$ = $n+1$.
> Where $n$ is the input length.


---

## O Notation

Asymptotic analysis estimates the running time of the algorithm on large inputs.
We consider only the highest order term of the expression

> [!hint]
> Hence, we disregard both the coefficient of that term and any lower order terms.
> The highest order term dominates the other terms on large input.


![[Pasted image 20250829163904.png]]

Where: 
- $g(n)$ is a comparison function. $g(n)$ is picked to represent a target growth rate (e.g., $n$, $n\cdot \log\cdot n$, $n^2$, $2^n$) that captures the desired asymptotic upper bound class for $f(n)$.
- $O(g(n))$ denotes the set of all functions whose growth is eventually no more than a constant multiple of $g(n)$.

> [!example]
> If $f(n) = 2n^2$. We shall say that $g(n)=n^2$ and $c=2$.
> $$\large \lim_{n\rightarrow\infty}\frac{2n^2}{n^2}=2$$
> And so $f(n)=2n^2$ is $O(n^2)$.

> [!note]
> ![[Pasted image 20250829164600.png]]
> 
> $n_0$ encodes the phrase “for sufficiently large $n$” and is not unique—any larger threshold also works, as long as the inequality holds from that point onward.
