## Sequential circuits ([HOW-TO](14.%20Finite%20State%20Machines.md#^817621))
![](../z_images/Pasted%20image%2020250113133107.png)

![](../z_images/Pasted%20image%2020250113132727.png)

![](../z_images/Pasted%20image%2020250210172213.png)

![](../z_images/Pasted%20image%2020250210174312.png)

![](../z_images/Pasted%20image%2020250407123932.png)

This exercise is actually asking you to:
- Make an [FSM](14.%20Finite%20State%20Machines.md) for the problem
- Turn it into transition table
- Make the sequential circuit for the FSM, specifically the next state circuit and the output circuit with [PLA](8.%20PLA.md), or [Decoder](11.%20Decoder.md).

> [!hint] Making an FSM
> - We usually use **Mealy FSM**s, which use current **inputs** and **current states** to **decide the next state**.
> - When the FSM is meant to detect a sequence, usually we have to put the whole steps of the sequence in states, not just a single character. If you use single characters, it's impossible to remember where you are in the sequence.
> - Arrows have a label {input}/{output}

> [!hint] Simple Decoder explanation
> A decoder is a circuit in which the inputs choose the active lane, and the active lane corresponds to a binary sequence:
> 
> ![](../z_images/Pasted%20image%2020250120121131.png)
> 
> Or to a midterm:
> ![](../z_images/Pasted%20image%2020250120121359.png)

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

![](../z_images/Pasted%20image%2020250113133225.png)
![](../z_images/Pasted%20image%2020250210174725.png)
![](../z_images/Pasted%20image%2020250527143237.png)![](../z_images/Pasted%20image%2020250527143249.png)![](../z_images/Pasted%20image%2020250527143302.png)
![](../z_images/Pasted%20image%2020250602205044.png)

This exercise is asking you to:
1. Compute the formulas for each output given the FSM (Skip if you have a decoder already)
2. Turn the formulas into a state transition table
3. Draw the FSM


In an FSM, you have 3 different parts, the registers, the output logic and the next state logic.
The **output logic** is the part to the **right of the registers**, while **next state logic** is the part to the **left of the registers**.
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

### Operations

> [!abstract] Multiplication
> ### Rules
> - 0 × 0 = 0
> - 0 × 1 = 0
> - 1 × 0 = 0
> - 1 × 1 = 1
>   
> 1. Multiply the first digit of the lower number (from the left) by each digit of the upper number
> 2. Do the same for second digit, then sum the results.
> 3. Then multiply the third digit with each digit of the upper number, and sum the result with the result from the previous sum
> 4. Go on
> 
> ### Remember
> - Multiply as if they were unsigned numbers.
> - Put the smallest number below.
> - Number of digits after the point = digits after the decimal point in n1 + digits after decimal point in n2.
> - Exponents must be summed and bias must be subtracted (or else you have bias x2).
> 
> > [!example]
> > ![](../z_images/Pasted%20image%2020250402144327.png)

> [!abstract] Addition & Subtraction
> ### Rules 
> - 0 + 0 = 0 
> - 1 + 0 = 1 
> - 0 + 1 = 1
> - 1 + 1 = 0 (with carry)
>   
> 1. Convert numbers to Two's Complement if they are negative.
> 2. Do normal addition
>   
> ### Remember
> - Exponent must be the same, shift smaller mantissa.
> - You need to align the dots, just move the mantissa around.
> - If you need to extend numbers:
> 	- prepend 1 if the number is negative
> 	- prepend 0 if it is positive
> 	- append 0 always


## Boolean algebra
![](../z_images/Pasted%20image%2020250113133443.png)
![](../z_images/Pasted%20image%2020250113132838.png)
![](../z_images/Pasted%20image%2020250406115654.png)

### Converting XOR

> [!abstract] Converting that expression to SOP or POS
> ![](../z_images/Pasted%20image%2020241215132848.png)


### Minimal SOP & POS

1. Make the Truth Table of the expression
	1. Write down the usual initial variables
	2. Add columns for each sub-expression, until you get a column for the whole expression.
	3. Compute the result column

| a | b | c | ab | bc | ab ⊕ bc | ac | f |
|---|---|---|----|----|---------|----|----|
| 0 | 0 | 0 | 0  | 0  | 0       | 0  | 0  |
| 0 | 0 | 1 | 0  | 0  | 0       | 0  | 0  |
| 0 | 1 | 0 | 0  | 0  | 0       | 0  | 0  |
| 0 | 1 | 1 | 0  | 1  | 1       | 0  | 1  |
| 1 | 0 | 0 | 0  | 0  | 0       | 0  | 0  |
| 1 | 0 | 1 | 0  | 0  | 0       | 1  | 1  |
| 1 | 1 | 0 | 1  | 0  | 1       | 0  | 1  |
| 1 | 1 | 1 | 1  | 1  | 0       | 1  | 1  |

2. Produce a karnaugh map:

| c \ ab | 00 | 01 | 11 | 10 |
|--------|----|----|----|----|
|   0    |  0 |  0 |  1 |  0 |
|   1    |  0 |  1 |  1 |  1 |
These would be the circles:
![](../z_images/Pasted%20image%2020250403182600.png)
3. Compute the expression

$$\Large f'=ab + bc+ ac$$

> [!danger] How to place the circles
> ![](../z_images/Pasted%20image%2020250115165959.png)
> 
> ### POS
> - Circle 0's instead.
> - The literals that you select must be negated.
> - The literals you need to select are still the ones that do not change within the circle.
>   
>   ![](../z_images/Pasted%20image%2020250408122418.png)

> [!hint] How to find the equation
> Look at the circles, for each one, **look at what variable changes between the cells**, you must **not include it** in the minterm generated by the circle.
> 
>> [!example]
>  In this case, for the vertical circle, it shows that **no matter the value of C**, if A = 0 and B = 1, then Y = 1, so the minterm is $\bar{A}B$.
> 
> Remember that we are writing down the cases that make the equation TRUE.

### Canonical forms

> [!summary] Characteristics of Canonical SOP Form
> 1. All product terms must contain all variables involved in the function.
> 2. Each product term represents exactly one specific input combination where the function equals 1.
> 3. It can be directly derived from a truth table.

> [!summary] Characteristics of Canonical POS Form
> 1. All sum terms must include every variable in the function.
> 2. Each sum term corresponds to one specific input combination where the function equals 0.
> 3. It can be directly derived from a truth table by focusing on output zeros.
