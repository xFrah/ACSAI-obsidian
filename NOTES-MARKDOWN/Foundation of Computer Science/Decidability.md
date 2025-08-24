A problem is considered **decidable** if there exists a [[Turing Machines|Turing machine]] (or equivalent algorithm) that always halts (either accepts or rejects) and provides the correct answer for every possible input.

## Problems as Languages

From now on, our goal will be to see if a problem $P$ admits an algorithm (= a decider) or not.

We shall see all the solutions of the problem as a language, because we can always encode everything:

![[Pasted image 20250819170652.png]]

where $⟨p⟩$ is the encoding of solution $p$.

> [!warning]
> Any problem can be represented by a language.

---

## Decision problems

The typical decision problems on languages are:
- **Membership**: «does $w$ belong to $L$?»
- **Emptyness**: «is $L$ empty?»
- **Equivalence**:  «is $L_1 = L_2$?»

> [!note]
> ![[Pasted image 20250821184031.png]]

> [!note]
> ![[Pasted image 20250823171111.png]]

> [!example]
> ![[Pasted image 20250819171025.png]]![[Pasted image 20250819171036.png]]

---