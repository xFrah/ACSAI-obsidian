Informally, an algorithm is a collection of simple instructions for solving some task.

## Church-Turing Thesis

The Church-Turing Thesis states that **any function that can be computed by an effective method can be computed by a Turing machine**.

More formally, it asserts that the set of functions computable by a Turing machine is exactly the same as the set of functions that can be computed by any effective or mechanical procedure.

> [!hint]
> The thesis provides a precise definition of what it means for something to be computable and defines the limits of what can be algorithmically computed.


The thesis can be expressed in several equivalent formulations:
- Every effective computation can be carried out by a Turing machine.
- A function on natural numbers is effectively calculable if and only if it is computable by a Turing machine.
- Any real-world computation can be translated into an equivalent computation involving a Turing machine.

### Effective methods definition

1. **Finite instructions (IMPORTANT)**: The method consists of a finite number of exact, precise instructions.
2. **Finite execution (IMPORTANT)**: When applied correctly, it produces results in a finite number of steps.
3. **Human executable**: It can, in principle, be carried out by a human with only paper and pencil.
4. **Mechanical process**: It requires no insight, intuition, or ingenuity - only following instructions systematically.

> [!example]
> A classic example of an effective method is the **truth table test** for determining if a logical formula is a tautology.
