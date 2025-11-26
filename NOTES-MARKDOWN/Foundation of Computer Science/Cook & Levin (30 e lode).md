Given a boolean formula, find an encoding of input variables that makes the formula output true (verify that its satisfiable).
This is an NP-Complete problem.

## Cook & Levin

Proof that SAT belongs to NPC.
In this case, the certificates are sequences of $n$ bits (first bit is first variable, second bit is second variable, etc...). 
1. Prove that its NP (algorithm for polynomially verifying a certificate exists): This is quickly done, because you just have to compute the formula, given the certificate. It's in linear in the size of the formula.
2. Show that every problem $A$ in NP polynomially reduces to SAT.
	- Consider that a deterministic decider N for A exists.
	- For every input $w$, we polynomially build a formula that is satisfiable only if $N$ accepts $w$.
	- Choose a problem $A$, then choose an input, 


### $\phi_{\text{cell}}$
For every cell, there exists an S such that x i,j contains s, and not any other thing.
A single 1 for every i,j.
For the cell 1,1, everything is 0 except one character that is 1.

### $\phi_{\text{start}}$

Just the concatenation of some conditions on each cell.

### $\phi_{\text{accept}}$

There exists a cell in which $q_{\text{accept}}$ appears.

### $\phi_{\text{cell}}$

Check that every row yields the next one, according to the transition function of the turing machine.
You need to see where the head is, and check which are the possible evolutions from that point, and check if the next row adheres to these evolutions.

You must also maintain polynomiality in this (in the whole reduction).
The changes from one configuration to another, the changes are very localized (this is why 2x3 window, 2 lines and 3 characters). Because like you can move the variables by just one position.

The head is where the q is, it reads the next character (to the right), then the next head will move Left or Right in the next row. The read character will be replaced exactly below its cell, with the output.

So basically we have legal windows and illegal windows. The condition of $\phi$ is that the configuration is legal in every windows.
All windows are centered on their middle-up cell.


## ??

We want to codify one path of the computation of the machine as a formula, such that the formula is accepting if and only if the formula is satisfiable.
