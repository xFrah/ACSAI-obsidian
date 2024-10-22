This will contain only important stuff

## Systems of linear equations

Use gaussian elimination/gauss-jordan.

### Solutions
There are three cases:
- **fewer equations than variables**: free variable, which means **infinite solutions**.
- **contradiction**, the system has **no solution**, 
- otherwise it's consistent.

### Homogeneous
An homogeneous system is a sistem with constant terms all to 0, and it has at least one solution.
It can also have infinite solutions and one of them is that all variables are 0.

## Matrix multiplication

**Row of first** matrix x **column of second** matrix. Each one of these operations outputs a single cell.


## Equations with matrices

For addition and subtraction they have the same properties as normal algebra.

> [!hint]
> You can think of it as applying these operations for only the first element of the matrix, it's the same thing, since these operations apply to each one of the cells individually.



## Vector spaces

There will be exercises like this:

![](../z_images/Pasted%20image%2020241022123848.png)


For something to be considered a vector space $V$, it must respect the axioms of vector addition and scalar multiplication:

**Addition**:
- Closure under addition:$\large \quad u + v \in V$
- Cummutativity: $\large \quad u + v = v + u$
- Associativity: $\large \quad u + (v+w)=(u+v)+w$
- Additive identity: There exists a 0 vector that added to other vectors, doesn't change them.
- Additive inverse: For every vector, there exists an inverse one that when added produces 0.

**Scalar multiplication**:
- Closure under scalar multiplication: $\large \quad c\vec{u} \in V$
- Distributivity: $\large \quad c(\vec{u}+\vec{v})=c\vec{u}+c\vec{v}\quad$ e $\large\quad(c+d)\vec{u} = c\vec{u}+d\vec{u}$
- Associativity: $\large \quad c(d\vec{u})=(cd)\vec{u}$
- Scalar identity: $\large \quad 1(\vec{u})=\vec{u}$

