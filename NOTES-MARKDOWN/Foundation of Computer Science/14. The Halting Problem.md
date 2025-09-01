Assume we have two programs $q$ and $P$:
- $q$ is a generic program;
- $P$ takes a program and an input for that program, and returns whether the program terminates or not with that specific input.

> [!hint]
> For intuition, think about $P$ as a code parser, it analyzes the second program and checks if it can finish.


Consider another outer program $K$, which takes as input a generic program $y$.
This program $K$ is defined as:

```C
if P(y, y) {  // if y finishes
	while 1;  // don't make this program finish
}
return true;  // if y can't finish, return True
```

> [!warning]
> Remember that P(y, y) doesn't necessarily execute y, so **we can definitely arrive at the line** `return True` **even when y can't terminate**, if that's what you were thinking.


Now what happens if we input the program $K$ into $K$?
**Two cases** can happen:
- $P(K, K)$ outputs True, meaning that $K$ will terminate with input $K$. But this is a contradiction

```C
if P(K, K) {  // We enter this if
	while 1;  // K doesn't finish
}
```

- $P(K, K)$ outputs False, meaning that K cannot terminate, but this will make $K$ terminate so this is also a contradiction.

```C
return True;
```


So the existence of this program $P$ is not possible, which makes this is a problem we can't solve.