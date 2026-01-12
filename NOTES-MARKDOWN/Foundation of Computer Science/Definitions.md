## Finite Automata

### Deterministic Finite Automaton (DFA)
A DFA is a 5-tuple $(Q, \Sigma, \delta, q_0, F)$ where:
1. $Q$: Finite set of states
2. $\Sigma$: Finite input alphabet
3. $\delta$: Transition function $\delta: Q \times \Sigma \to Q$
4. $q_0$: Start state, $q_0 \in Q$
5. $F$: Set of accept states, $F \subseteq Q$

**Acceptance:**
Let $A$ be a DFA and $w = w_1 \dots w_n$ where each $w_i \in \Sigma$. Then $A$ accepts $w$ if there exists a sequence of states $r_0, r_1, \dots, r_n$ in $Q$ such that:
1. $r_0 = q_0$
2. $\delta(r_i, w_{i+1}) = r_{i+1}$ for $i = 0, \dots, n-1$
3. $r_n \in F$

**Language of A:**
$L(A) = \{w \mid A \text{ accepts } w\}$

### Nondeterministic Finite Automaton (NFA)
An NFA is a 5-tuple $(Q, \Sigma, \delta, q_0, F)$ where:
1. $Q$: Finite set of states
2. $\Sigma$: Finite input alphabet
3. $\delta$: Transition function $\delta: Q \times \Sigma_{\varepsilon} \to \mathcal{P}(Q)$
4. $q_0$: Start state, $q_0 \in Q$
5. $F$: Set of accept states, $F \subseteq Q$

**Acceptance:**
Let $N$ be an NFA and $w$ a string over $\Sigma$. $N$ accepts $w$ if we can write $w$ as $w = y_1 y_2 \dots y_m$ where each $y_i \in \Sigma_{\varepsilon}$ and there exists a sequence $r_0, \dots, r_m$ in $Q$ such that:
1. $r_0 = q_0$
2. $r_{i+1} \in \delta(r_i, y_{i+1})$ for $i = 0, \dots, m-1$
3. $r_m \in F$

### Generalized NFA (GNFA)
A GNFA is a 5-tuple $(Q, \Sigma, \delta, q_{start}, q_{accept})$ where:
1. $Q$: Finite set of states
2. $\Sigma$: Input alphabet
3. $\delta$: $(Q \setminus \{q_{accept}\}) \times (Q \setminus \{q_{start}\}) \to \mathcal{R}$ (where $\mathcal{R}$ is the set of regexes)
4. $q_{start}$: Start state
5. $q_{accept}$: Accept state

**Acceptance:**
A GNFA accepts a string $w \in \Sigma^*$ if $w = w_1 \dots w_k$, where each $w_i \in \Sigma^*$ and there exists a sequence of states $q_0, \dots, q_k \in Q$ such that:
1. $q_0 = q_{start}$
2. $q_k = q_{accept}$
3. For each $i$, $w_i \in L(R_i)$ where $R_i = \delta(q_{i-1}, q_i)$

### Regular Expressions (Regex)
$R$ is a regular expression if it is:
1. $a$, for some $a \in \Sigma$
2. $\varepsilon$
3. $\emptyset$
4. $(R_1 \cup R_2)$ where $R_1, R_2$ are regexes
5. $(R_1 \circ R_2)$
6. $(R_1^*)$

### Regular Operations
Let $A$ and $B$ be regular languages:
*   **Union:** $A \cup B = \{x \mid x \in A \text{ or } x \in B\}$
*   **Concatenation:** $A \circ B = \{xy \mid x \in A \text{ and } y \in B\}$
*   **Star:** $A^* = \{x_1 x_2 \dots x_k \mid k \geq 0 \text{ and each } x_i \in A\}$

---

## Pushdown Automata & Grammars

### Pushdown Automaton (PDA)
A PDA is a 6-tuple $(Q, \Sigma, \Gamma, \delta, q_0, F)$ where:
1. $Q$: Finite set of states
2. $\Sigma$: Input alphabet
3. $\Gamma$: Stack alphabet
4. $\delta$: Transition function $\delta: Q \times \Sigma_{\varepsilon} \times \Gamma_{\varepsilon} \to \mathcal{P}(Q \times \Gamma_{\varepsilon})$
5. $q_0$: Start state, $q_0 \in Q$
6. $F$: Set of accept states, $F \subseteq Q$

**Acceptance:**
A PDA accepts string $w$ if $w = w_1 \dots w_m$, where each $w_i \in \Sigma_{\varepsilon}$, and sequences $r_0, \dots, r_m \in Q$ and $s_0, \dots, s_m \in \Gamma^*$ exist such that:
1. $r_0 = q_0$ and $s_0 = \varepsilon$
2. $r_m \in F$
3. For $i = 0, \dots, m-1$: if $s_i = at$ for some $a \in \Gamma_{\varepsilon}, t \in \Gamma^*$, then $(r_{i+1}, b) \in \delta(r_i, w_{i+1}, a)$ and $s_{i+1} = bt$ for some $b \in \Gamma_{\varepsilon}$.

### Deterministic PDA (DPDA)
A DPDA is a 6-tuple $(Q, \Sigma, \Gamma, \delta, q_0, F)$ subject to the condition:
For every $q \in Q, a \in \Sigma, x \in \Gamma$, exactly one of $\delta(q,a,x), \delta(q,a,\varepsilon), \delta(q,\varepsilon,x), \delta(q,\varepsilon,\varepsilon)$ is not $\emptyset$.

### Context-Free Grammar (CFG)
A CFG is a 4-tuple $(V, \Sigma, R, S)$ where:
1. $V$: Finite set of variables
2. $\Sigma$: Finite set of terminals
3. $R$: Finite set of rules $R \subseteq V \times (V \cup \Sigma)^*$
4. $S$: Start variable, $S \in V$

### Chomsky Normal Form (CNF)
A CFG is in CNF if every rule is of the form:
*   $A \to BC$
*   $A \to a$
*   $S \to \varepsilon$ (permitted)
where $a \in \Sigma$ and $B, C \in V \setminus \{S\}$.

**Derivations:** Deriving a string of length $n$ ($n>0$) in a CNF grammar requires exactly $2n-1$ steps.

**Conversion to CNF:**
1. Add new start variable $S_0 \to S$.
2. Remove $\varepsilon$-rules ($A \to \varepsilon$).
3. Remove unit rules ($A \to B$).
4. Convert remaining rules to have exactly 2 variables on RHS.

---

## Turing Machines

### Standard Turing Machine
A TM is a 7-tuple $(Q, \Sigma, \Gamma, \delta, q_0, q_{accept}, q_{reject})$ where:
1. $Q$: Set of states
2. $\Sigma$: Input alphabet (does not contain blank $\sqcup$)
3. $\Gamma$: Tape alphabet ($\Sigma \subseteq \Gamma$ and $\sqcup \in \Gamma$)
4. $\delta$: Transition function $\delta: (Q \setminus \{q_{acc}, q_{rej}\}) \times \Gamma \to Q \times \Gamma \times \{L, R\}$
5. $q_0$: Start state
6. $q_{accept}$: Accept state
7. $q_{reject}$: Reject state

**Configuration:**
$u q v$ means current state is $q$, current tape content is $uv$, and head is on the first symbol of $v$.
A TM accepts input $w$ if there exists a sequence of configs $C_0, \dots, C_k$ where:
1. $C_0$ is the start config on input $w$.
2. Each $C_i$ yields $C_{i+1}$.
3. $C_k$ is an accepting config.

*   **Recognizable (R.E.):** A TM may fail to accept by rejecting or looping.
*   **Decider:** A TM that always halts.

### Nondeterministic TM (NTM)
Defined by having multiple possibilities at a step.
$\delta: (Q \setminus \{q_{acc}, q_{rej}\}) \times \Gamma \to \mathcal{P}(Q \times \Gamma \times \{L, R\})$
The computation is a tree. If some branch leads to accept, the machine accepts.

### Enumerator
A 2-tape TM $(Q, \Sigma, \Gamma, \delta, q_0, q_{print}, q_{reject})$ that uses a printer as an output device.
*   $L(E) = \{w \in \Sigma^* \mid w \text{ appears on the print tape after } q_{print} \text{ is entered}\}$.

### Multitape TM
Ordinary TM with $k > 1$ tapes.
$\delta: (Q \setminus \{q_{acc}, q_{rej}\}) \times \Gamma^k \to Q \times \Gamma^k \times \{L, R, S\}^k$

### Linear Bounded Automaton (LBA)
An LBA is an NTM with restricted tape:
1. $\Gamma$ includes special endmarkers (e.g., $\vdash, \dashv$).
2. Head cannot move past endmarkers (tape size bounded linearly by input length).
$L(LBA) = \{w \in \Sigma^* \mid q_0 w \vdash^* \text{accepting config}\}$

---

## Complexity Theory

### Time Complexity
*   **Deterministic:** Let $M$ be a DTM that halts on all inputs. The running time is $f: \mathbb{N} \to \mathbb{N}$, where $f(n)$ is the max number of steps $M$ uses on any input of length $n$.
*   **Nondeterministic:** Let $N$ be an NTM decider. The running time $f(n)$ is the max nu
