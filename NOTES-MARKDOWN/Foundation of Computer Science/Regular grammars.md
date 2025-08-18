---
aliases:
  - regular grammar
---
When we want to describe a syntax, we can use generative grammars, which make use of their recursive structure and substitutions to "generate" valid entities.

> [!note]
> Regular grammars are specifically designed to generate strings that belong to [[regular languages]]. They have a specific structure in their production rules that limits the types of strings they can produce to those that can be recognized by a finite [[Finite Automata]].

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

> [!note] Previous example but formally
> ![](../z_images/Pasted%20image%2020241118110359.png)
> ![](../z_images/Pasted%20image%2020241118110415.png)

---

## Right-Linear vs Left-Linear grammars

There are two different ways of recursively generating a language or entity:

- By recursively appending on the right (**right-linear**)
- By recursively appending on the left (**left-linear**)

> [!example]
> The regular language $0(10)^*$ can be generated in two ways:
> - We **start from the left** with $0$ and then check recursively for $10$'s
>   
> 	![](../z_images/Pasted%20image%2020241119113011.png)
> 
> - We **start from the right** by checking recursively for either $10$ or $0$.
>   
>   ![](../z_images/Pasted%20image%2020241119113150.png)
>   
> With the right-linear grammar:
> - Start from **S**
> - Check for **0**
> - Start recursion for finding a sequence of **10**'s, if we find a **10** continue the recursion.
>   
> With the left-linear grammar:
> - We start from **S**
> - We check for either **10** or **0** recursively.
> - If we find a a **10**, continue the recursion.

---


## Regularity theorems

### WIP Slide 4 p. 9