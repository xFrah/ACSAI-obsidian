When we want to describe a syntax, we can use generative grammars, which make use of their recursive structure and substitutions to "generate" valid entities.

> [!hint]
> Used by compilers to parse code with the correct syntax.

> [!example] Grammar for natural numbers
> These are the rules, components on the right will replace components on the left:
> ![](../z_images/Pasted%20image%2020241117160130.png)
> 
> $$\large a ::= b \quad \text{means b can replace a}$$
> $$\large \text{| means OR}$$
> $$\large \text{a space between two entities means concatenation}$$
> 
> We can write the number **1903**:
> - First as **NUMB** (any number).
> - Then recursively as **NONZERODIGIT DIGITSEQ**.
> > [!hint]
> > **NUMB** = **DIGIT** | **NONZERODIGIT DIGITSEQ** (0,1, ..., 9 OR a digit sequence that doesn't start with 0).
> > But since 1903 is not a single **DIGIT**, we substitute with **NONZERODIGIT DIGITSEQ**.
> - Then we can substitute with a real value: **1 DIGITSEQ**, we recursively substitute the rest.
> - **1 **(**DIGIT DIGITSEQ**)
> > [!hint]
> > **DIGITSEQ** = **DIGIT** | **DIGIT DIGITSEQ**.
> > We just substituted **DIGITSEQ** with **DIGIT DIGITSEQ**.
> - **1 9 DIGITSEQ**
> - **1 9 **(**DIGIT DIGITSEQ**)
> - **1 9 0 DIGITSEQ**
> - **1 9 0 **(**DIGIT**)
> - **1 9 0 3**

