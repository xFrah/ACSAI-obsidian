GMT20241003-091429_Recording.cutfile.20241003135147983_as_1400x876

### Chapter 1: Introduction

- Lecture is online due to room issues, but future in-person lectures will take place in Room 101, Building B.
    
- Importance of keeping an eye on course communications (Google Classroom, administration messages).
    

#### Binary Numbers

- **Representation of Base 10 to Base 2**:
    
    - Example: 34 in base 10 can be represented as powers of 2 (32 + 2 = 2^5 + 2^1).
        
    - To obtain binary equivalent, place 1 in positions of powers of 2 and 0 elsewhere.
        
    - Equivalent binary for 34 is: 100010.
        
- **Conversion Method**: Divide by 2, note remainders until reaching 0.
    

#### Signed Numbers

- Introduction to signed numbers: Can be positive (0 as sign) or negative (1 as sign).
    
- **Methods of Representation**:
    
    - **Sign and Magnitude**: First bit indicates sign (0 = positive, 1 = negative), remaining bits indicate magnitude.
        
        - Example: 01101 (0 = positive) is +13; 11101 (1 = negative) is -13.
            
    - **Range**: 2^(n-1) for positive range, for `n` bits.
        
    - Issues: Addition may not work effectively, multiple representations for 0 (both +0 and -0).
        
- **Two's Complement**: Solutions to sign and magnitude issues.
    
    - Better for arithmetic operations, allows addition/subtraction consistency.
        
- **Two's Complement Representation**:
    
    - First bit indicates sign (0 positive, 1 negative).
        
    - Negative numbers are converted from positive by inverting bits and adding 1.
        
        - Example: 1010 (which is -6) is represented by flipping (0101) and adding 1.
            

### Chapter 2: Largest Negative Number

- Largest positive num (4 bits): 0111 = 7.
    
- Largest negative num (4 bits): 1111 = -1.
    
- Positive and negative numbers can coexist in two's complement representation.
    

### Chapter 3: Number of Bits

- **Representation**: Varies based on number of bits chosen (e.g., 5 bits can represent -15 to +15).
    
- When shifting between n bits and m bits, sign extension is crucial for ensuring negative values remain negative when increasing bits.
    

### Chapter 4: Number of Bits (Cont.)

- Recap on the effective ranges for each type of representation (unsigned, signed magnitude, and two's complement).
    
- Glide through examples showing how to add various width bits, emphasizing the overflow behavior in different systems.
    

### Chapter 5: Multiplication and Division in Binary

- **Multiplication**: Achieved through iterative addition akin to decimal systems.
    
    - Positive and negative numbers are handled similarly but need caution with carrying bits.
        
- **Division**: Emphasis on powers of 2 (e.g. left shift multiplies by 2, right shift divides by 2).
    

### Chapter 6: Logical Shifts

- **Left Shift**: Multiplying by 2 to the power of the shift count.
    
- **Right Shift**: Dividing by 2 to the power of shift count for positive; for negatives use arithmetic shift.
    

### Chapter 7: Additional Complexity with Shifting & Overflows

- Logical right shift adds zeros to the left; arithmetic retains sign fullness.
    
- Overflow occurs when summing too large values.
    

### Conclusion

- Shifted awareness towards size capability in both directions (i.e., left shift versus arithmetic right shift for negative divisions).
    
- Concept check on arrays and segmentations as essential understandings in practical applications.