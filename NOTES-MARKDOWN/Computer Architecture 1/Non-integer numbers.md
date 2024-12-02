There are usually two common notations:
- **Fixed-point**: Integer part and fractional part have fixed number of bits.
- **Floating-point**: Integer part is always 1, uses powers to represent the integer part as fractional part.

![](../z_images/Pasted%20image%2020241202192212.png)

---

## Fixed-point numbers

An example would be the number 0110.1100 (4 integer and 4 fractional bits).
It can be converted as follows:

$$\large \underbracket{0}\underbracket{1}_{2^3}\underbracket{1}_{2^2}\underbracket{0}.\underbracket{1}_{2^{-1}}\underbracket{1}_{2^{-2}}\underbracket{0}\underbracket{0}$$$$\large2^2+2^1+2^{-1}+2^{-2}=6.75$$

### Conversion to binary

For the integer part you should use **???**
For the fractional part:
1. Multiply by 2.
2. If result is greater than 1, write 1, otherwise 0.
3. Take result, put integer part to 0 and repeat step 1.

> [!example]
> Let's convert 0.625 to binary:
> 
> - 0.625 × 2 = 1.25 → write 1, keep 0.25
> - 0.25 × 2 = 0.5 → write 0, keep 0.5
> - 0.5 × 2 = 1.0 → write 1, keep 0
> - Since p is now 0, we're done
> 
> So 0.625₁₀ = 0.101₂


### Signed fixed-point numbers

We have two options:
- The sign bit (leftmost bit)
- Two's Complement:
	- First we write the positive number in binary.
	- We invert all the bits.
	- Add 1.

> [!danger]
> We need to apply the Two's Complement process to the whole number, not just the integer part.


## Floating-point numbers

> [!example]
> - The binary number 1101.01 would be normalized to 1.10101 × 2³
> - The binary number 0.00101 would be normalized to 1.01 × 2⁻³


---

