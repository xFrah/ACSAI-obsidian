We want to match strings. This is what we call **RegEx** usually.

There are 3 operations that we can do:
- **Concatenation**: $a ∘ b$ or $ab$, matches the concatenation of two characters, in two consecutive spots.
- **Union**: $a \cup b$, matches both characters at a single spot.
- **Star**: $a*$ or $\Sigma*$ (for any character), matches a sequence of any length of a character.

> [!note]
> - ε means **no character**, just like pressing enter without any character.
> - $\Sigma$ stands for the alphabet, so it's a **placeholder for any character** in the alphabet.

> [!hint]
> In the definitions above i just mention characters, but beware, we can input a sequence of characters in place of a single character for any of those operations.
> 
> $$\large (\Sigma\Sigma)^*$$
> 
> The string above matches any string that has even length.

> [!example]
> - $\large 0^*10^*$ 
> 	- matches any string that starts with all zero's, contains a 1 and ends with all zeroes (*"1", "01", "10", "001", "100", "0010"*). 
> 
> - $\large Σ^*1Σ^*$ 
> 	- matches any string with at least one 1 (*"1", "11", "101", "010", etc.*).
> 
> - $\large Σ^*001Σ^*$ 
> 	- matches any string containing "001" (*"001", "0011", "10010", etc.*).
> 
> - $(ΣΣ)^*$ 
> 	- matches strings with length 0, 2, 4, 6, etc. (*"", "00", "01", "1100", etc.*).
> 
> - $(ΣΣΣ)^*$ 
> 	- similar to above but for lengths 0, 3, 6, 9, etc. (*"", "000", "001", "111000", etc.*).
> 
> - $\large(0∪ε)(1∪ε)$ 
> 	- optionally have a 0, then optionally have a 1 (*"0", "1", or "01"*)
> 
> - $\large 0Σ^*0 ∪ 1Σ^*1 ∪ 0 ∪ 1$ 
> 	- matches strings that start and end with the same digit (*"0", "1", "00", "11", "010", "101", etc.*)
> 
> 

> [!example] Example with syntax of numbers
> The following regular expression can be used to match integers, fractional and negative numbers:
> 
> $$\large (+\cup -\cup ε)(D^+\cup D^+.D^*\cup D^*.D^+)$$
> 
> More in detail
> - $D^+$ - integers (**72**)
> - $D^+.D^*$ - integers with possible fractional part (**7.**)
> - $D^*.D^+$ - possible integer part and sure fractional part (**-.01**)
>   
>   > [!note]
> > $D^+$ is equal to $DD^*$. 
> > This is useful because $D^*$ can match empty strings, while $D^+$ can't.


## Algebraic laws

Think of the **union as a sum** and the **concatenation as a product**.

> [!danger]
> Even if it's similar to the product, concatenation is not commutative:
> $$\large R1 ∘ R2 ≠ R2 ∘ R1$$

> [!example]
> ![](../z_images/Pasted%20image%2020241108105941.png)


---

## Equivalence with NFA

### WIP Slide 3 p. 7