Slide 13

## Reduction

## Parallel fors

We divide the iterations of a loop.
We can also have data dependency problems because OpenMP doesn't check for data dependency between iterations.

### Alternatives to data dependencies
- Loop skwing: the statements that consume that need the calculated values, will compute them in their iterations (and not get the ones calculated in the old iterations).