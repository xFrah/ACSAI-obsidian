## Sequential circuits ([HOW-TO](14.%20Finite%20State%20Machines.md#^817621))
![](../z_images/Pasted%20image%2020250113133107.png)

![](../z_images/Pasted%20image%2020250113132727.png)

![](../z_images/Pasted%20image%2020250210172213.png)

![](../z_images/Pasted%20image%2020250210174312.png)

This exercise is actually asking you to:
- Make an [FSM](14.%20Finite%20State%20Machines.md) for the problem
- Turn it into transition table
- Make the sequential circuit for the FSM, specifically the next state circuit and the output circuit with [PLA](8.%20PLA.md), or [Decoder](11.%20Decoder.md).

> [!example] Third exercise
> ### Make the FSM
> ![](../z_images/Pasted%20image%2020250210172312.png)
> 
> ### Make the transition table
> ![](../z_images/Pasted%20image%2020250210172350.png)
> 
> ### Make the circuit
> In this case we use a Decoder for turning the single cases (in order) to their actual output, using a simplified diagram:
> ![](../z_images/Pasted%20image%2020250210172541.png)
> > [!hint]
> The vertical lines are meant to be seen as a giant or for a single output.

> [!example] Fourth exercise
> ### Make the FSM
> ![](../z_images/Pasted%20image%2020250210174351.png)
> ### Draw the state transition table
> ![](../z_images/Pasted%20image%2020250210174409.png)
> 
> Draw the circuit, in this case it's all in one with a Decoder:
> ![](../z_images/Pasted%20image%2020250210174434.png)
> 

## Functions, truth table and circuit drawing
![](../z_images/Pasted%20image%2020250113132739.png)
![](../z_images/Pasted%20image%2020250113132945.png)

## State transition diagram ([](14.%20Finite%20State%20Machines.md#^ed5229))
![](../z_images/Pasted%20image%2020250113133208.png)
![](../z_images/Pasted%20image%2020250113133225.png)
![](../z_images/Pasted%20image%2020250210174725.png)

This exercise is asking you to:
1. Compute the formulas for each output given the FSM (Skip if you have a decoder already)
2. Turn the formulas into a state transition table
3. Draw the FSM
## PLA
![](../z_images/Pasted%20image%2020250113133341.png)
![](../z_images/Pasted%20image%2020250113133352.png)

## IEEE 754
![](../z_images/Pasted%20image%2020250113133407.png)
![](../z_images/Pasted%20image%2020250113132827.png)
![](../z_images/Pasted%20image%2020250210172917.png)

### Decimal to Binary (EASY)

For the integer part, we have to:
1. Set to 1 the leftmost bit that would make the number still less than the number we want to convert. 
2. Repeat until you convert it all.

> [!example] Converting 18 to binary
> 1. The fifth bit from the right would make the number 16, the sixth one 32, so we set the fifth bit to 1.
>    $$\large 1 \cdot 2^4 + \text{?} \cdot 2^3 + \text{?} \cdot 2^2 + \text{?} \cdot 2^1 + \text{?} \cdot 2^0= 16+\text{?}$$
>    
>    
> 2. The fourth bit would make the number 24 (16+8), which is higher than 18 so we don't set it.
>    
>    $$\large 1 \cdot 2^4 + 0 \cdot 2^3 + \text{?} \cdot 2^2 + \text{?} \cdot 2^1 + \text{?} \cdot 2^0$$
>    
> 3. The third bit would make the number 20, which is greater than 18 so we don't set it.
>    
>    $$\large 1 \cdot 2^4 + 0 \cdot 2^3 + 0 \cdot 2^2 + \text{?} \cdot 2^1 + \text{?} \cdot 2^0$$
>    
> 4. The second bit would make the number 18, so we set it and we stop here
>    
>    $$\large 1 \cdot 2^4 + 0 \cdot 2^3 + 0 \cdot 2^2 + 1 \cdot 2^1 + 0 \cdot 2^0$$


Then for the fractional part we have to:
1. Multiply by 2.
2. If result is greater than 1, write 1, otherwise 0.
3. Take result, put integer part to 0 and repeat step 1.

> [!example] 0.625 to binary
> - 0.625 × 2 = 1.25 → write 1, keep 0.25
> - 0.25 × 2 = 0.5 → write 0, keep 0.5
> - 0.5 × 2 = 1.0 → write 1, keep 0
> - Since p is now 0, we're done
> 
> So 0.625₁₀ = 0.101₂
> 

> [!hint]
> For easier conversion, you can also think of it like this:
> $$\large2^2+2^1+2^{-1}+2^{-2}=6.75$$
> 
> The fractional part is:
> $$\large 1\cdot \frac{1}{2} + 1\cdot \frac{1}{4}= 0.75$$


### Hex to binary

> [!hint]
> Each hex digit can hold 16 values $\rightarrow$ We need 4 bits to represent 16 values.
> Basically we can convert any hex digit to a 4 bit number.


Take each digit of the hex number and convert it to 4 bits binary.

> [!example] Converting 0xC180 to binary
> $$\large \underbracket{C}_{1100}\;\underbracket{1}_{0001}\;\underbracket{8}_{1000}\;\underbracket{0}_{0000}$$

### Fixed-point to Floating-Point

Starting with a Fixed-point number:
- Multiply by 2 until you have only 1 bit (must be 1) on the decimal part.
- Put the number of times you multiplied in the exponent.
- Put the fractional part as the mantissa (floating-point assumes decimal part is 1).
- Set the sign bit.

> [!attention]
> In the exam, usually the half-precision format is used, which is:
> - **Exponent**: 5 bits
> - **Mantissa**: 10 bits
> - **Bias**: 15
>   
> In contrast with the single-precision format which is:
>   
> - **Exponent**: 8 bits
> - **Mantissa**: 23 bits
> - **Bias**: 127


## Boolean algebra
![](../z_images/Pasted%20image%2020250113133443.png)
![](../z_images/Pasted%20image%2020250113132838.png)