  

---

  

## Chapter 3 - The Unified/Lazy combinatorial generator Domain Formulation

  

### 3.1 Redefining the Search Space

  

In classic crossword generation using Constraint Satisfaction Problem (CSP) algorithms, the search for word that fits a specific slot is constrained by the static geometry of the grid, or at least by the length of the slot.

  

Formally, given a slot $S$ of length $L$, the traditional domain $D_{trad}$ is defined exclusively as a subset of the dictionary containing valid words of the corresponding length:

  

$$\large D_{trad}=\{w \in \Sigma^L \mid w \in Vocabulary\}$$

  

In this model, the grid's topology (the position of the black blocks) is either already chosen, or decided in a separate generation process.

  

The present algorithm solves the dynamic generation problem by collapsing the grid's topology generation and word assignments into a single step. To achieve this, the base alphabet is expanded to include structural elements as native variables. We define the new extended alphabet $\Sigma'$:

$$\large \Sigma' = \Sigma ∪\{⬚,■\}$$

  

where the "⬚" operator represents an empty cell and the "⯀" operator represents a structural black block.

  

Consequently, the unified domain $D_{uni}$ for a slot $S$ of length $L$ is no longer a static array of pre-existing strings, but a set of dynamically generated vectors that combine text segments, blocks, and unassigned spaces:

  

$$\large D_{uni} = \{v ∈ (\Sigma')^L \;|\;\text{vocabulary and structural constraints satisfied}\}$$

  

In this formulation, the grid topology is not an input to the CSP, but emerges simultaneously with the node resolution.

  

### 3.2 Contiguous Segments (possible words) vs Blocks vs Empty spaces

  

Since the domain $D_{uni}$ generates combinations of text, structural blocks ($\text{⯀}$), and empty spaces ($\text{⬚}$), a single variable resolution possesses great geometric flexibility.

  

Instead of strictly mapping one word to a predefined boundary, the algorithm evaluates contiguous segments and executes assignments over time. Geometrically, when placing a word $w$ (of length $k$) within a slot of length $L$, the generated vector $v$ is constructed from distinct spatial regions:

  

$$\large v = \left( \underbrace{\square, \dots, \square}_{\text{Deferred Left}}, \underbrace{\blacksquare}_{\text{Left Boundary}}, \underbrace{w_1, \dots, w_k}_{\text{Placed Word}}, \underbrace{\blacksquare}_{\text{Right Boundary}}, \underbrace{\square, \dots, \square}_{\text{Deferred Right}} \right)$$

Trivially, there will be no deferred space if the boundary coincides with the edge of the slot.

  

This structure executes assignments through the following mechanics:

- **Lazy combinatorial generation**: The generator systematically yields all possible spatial combinations of any word that can fit into the slot (even words shorter than the slot's length). These resolutions ensure that the configuration yields an assignment in which the selected word is either bounded by newly inserted blocks or by existing edges of the slot.

- **Deferred Generation**: The algorithm intentionally leaves the remainder of the vector unassigned as empty cells ($\text{⬚}$). By leaving these regions blank, the initial assignment dynamically fractures the original space into new, independent contiguous sub-slots to be processed later.

  

Crucially, these newly created sub-slots are not tracked explicitly. Instead, the algorithm employs a stateless rediscovery mechanism: after each assignment, the entire matrix is rescanned to identify all maximal contiguous sequences of non-block cells. Any such sequence of length $\geq 2$ is recognized as a new variable in the CSP, regardless of how it was formed. This means the algorithm requires no bookkeeping or dependency tracking between parent and child slots—new variables emerge organically from the grid's evolving topology.

  

As the search progresses, these rediscovered sub-slots are resolved independently—either by intersecting perpendicular domains or by subsequent parallel iterations—allowing multiple words to naturally populate the original row or column.

  

In this unified formulation, the assignment of a single domain organically shapes the matrix topology, places words from the vocabulary, and defines the exact boundaries for future variables all at once.

  

### 3.3 Lazy Evaluation of Infinite Combinations

  

Since a single domain encapsulates all valid permutations of vocabulary, structural blocks ($\text{⯀}$), and empty spaces ($\text{⬚}$), the resulting search space is exponentially larger than a traditional static domain. Generating and storing all possible vectors in memory is computationally unfeasible.

  

This limitation is bypassed through lazy evaluation, which transforms the domain from a static array into an on-demand generator. The generator yields one valid vector at a time, constructing each combination only when requested by the solver. This means the exponential space is never fully materialized—the solver can abandon an unpromising domain after consuming only a handful of its elements.

  

While the generator does not perform pruning—it will eventually yield every valid combination if fully consumed—it is not a blind iterator either. The order in which combinations are yielded is governed by heuristics. Given a slot containing multiple contiguous segments (regions of non-block cells separated by existing blocks), the generator prioritizes which segments to resolve first and in what order words are yielded within each segment. The specific heuristics employed are detailed in Chapter 5.

  

Because both topology shaping (block placements) and word assignment (vocabulary) coexist within the same unified search space, the generator's prioritization interacts naturally with the solver's own search heuristics. The solver controls *which* domains to expand and *when* to abandon them, while the generator controls *the order* in which candidates are presented within each domain.

  

---

  

## Chapter 4 - Hierarchical Constraint Caching

  

### 4.1 The Constraint Cache Tree

  

To support the rapid combinatorial expansion of the lazy generator, the algorithm relies on a custom hierarchical caching tree. Because the generator constantly demands valid dictionary words to fulfill newly formed segments, filtering the entire dataset for every iteration is computationally prohibitive.

  

The architecture of this tree is organized by the following hierarchy:

  

- **Root nodes:** The root nodes (multiple ones) of the tree consists of nodes representing completely unconstrained slots of various lengths. For example, a root node for a length of five contains all five-letter words in the vocabulary, represented purely by wildcards.

- **Child-nodes:** Every node in the tree represents a specific constraint pattern, and contains all the words in the vocabulary after filtering according to the constraint. A child node always enforces a stricter constraint than its parent node. Consequently, the list of valid words within any child node is a strict, smaller subset of the words contained in its parent.

  
  

When the solver requests the list of words that fit a specific constraint, the data structure is navigated and updated through the following operations:

- **Downward Traversal:** The tree gets traversed from the root to locate the most specific existing parent that fully encompasses the new constraint pattern. The new node is then populated by filtering only the heavily reduced wordset of that exact parent, bypassing a full dictionary scan.

- **New Constraint Caching:** Once the new constraint is added as a child to the located parent, it triggers a self-organizing mechanism. The new node evaluates its siblings (the other existing children of its parent). If any sibling represents a constraint that is actually a stricter subset of the _new_ node, the new node "kidnaps" it: the sibling is removed from the original parent and reassigned as a child of the newly created node.

  

This insertion logic ensures that the tree remains perfectly layered and optimized as new constraints are discovered on the fly.

  

### 4.2 Variable Resolution and Search Space Narrowing

  

The lazy generator invokes the cache tree strictly on-demand. When evaluating a slot, the generator isolates contiguous segments bounded by blocks and queries the cache using the segment's precise constraint pattern (e.g., `a..b..`).

  

The tree gets traversed to find the most specific encompassing parent node, returning a heavily reduced wordset. The generator then transforms this static wordlist into a lazy sequence of spatial combinations. Instead of computing all possible grid states simultaneously, it wraps the wordlist in an iterator and constructs full vectors on-demand.

  

For each valid word, the generator builds a complete spatial combination for the entire slot: it maps the word to the target segment's exact coordinates, inserts the required boundary blocks ($\text{⯀}$), and leaves the remaining outer indices as deferred empty spaces ($\text{⬚}$).

  

As described in §3.3, the order in which the generator yields these combinations is governed by heuristics (detailed in Chapter 5), ensuring that the solver receives the most promising candidates early and can make informed branching decisions without exhausting the entire domain.

  

---

  

## Chapter 5 - Search Architecture and Heuristics

  

### 5.1 Best-First Search and State Representation

  

#### 5.1.1 Choosing Best-First Search over Backtracking

  

Traditional CSP crossword generators typically commit to a single path (depth-first search), and upon reaching a dead end, undo assignments until a viable alternative is found.

This type of backtracking, while memory-efficient, suffers from a fundamental limitation in the context of dynamic grid generation: the quality of a solution is highly sensitive to early decisions, and comparing partial solutions across different branches of the search tree requires either advanced pruning strategies or some kind of parallelism, on top of the backtracking algorithm.

  

The present work adopts a best-first search strategy instead. Rather than committing to a single path, the solver maintains a priority queue of partial solutions (states), always expanding the most promising one. This comes at a significant memory cost, since each state must store an independent copy of the grid, but it offers the critical advantage of easing the comparison to other partial solutions, without requiring sophisticated pruning strategies. This allows the algorithm to naturally gravitate toward configurations that satisfy both structural and linguistic quality criteria. Pruning is basically all done through the priority queue, by using heuristics.

  

For example, if an early word placement leads to a structurally poor grid region, the solver does not need to exhaust that subtree before trying alternatives. It can simply deprioritize the resulting state and explore more promising branches first.

  

#### 5.1.2 State Representation

  

A key consequence of the best-first approach is that each state in the priority queue must carry enough information to fully resume the search from that point, without relying on any external context. At minimum, this requires a complete snapshot of the grid matrix $M$.

However, the state representation is not limited to the grid itself. Each state $\mathcal{S}$ can carry arbitrary auxiliary metadata alongside the matrix:

  

$$\large \mathcal{S} = (M, \; \alpha_1, \; \alpha_2, \; \dots, \; \alpha_n)$$

  

where $\alpha_1, \dots, \alpha_n$ represent any additional information that would be useful for heuristic evaluation, pruning decisions, or search management. This metadata travels with the state through the queue and is available at expansion time, enabling the solver to make informed decisions without recomputing information from the grid alone.

  

In the present implementation, the auxiliary fields carried are the search depth $d$ (the number of word placements since the initial empty grid) and the set of placed words $W$, the latter being a precomputed convenience that could in principle be derived from $M$ alone.

  
  

#### 5.1.3 The Search Loop

  

The solver explores the search space using the priority queue, where states are ranked by a composite key of heuristic scores (detailed in §5.2). At each iteration, the solver extracts the highest-priority state $\mathcal{S} = (M, d, W)$ from the queue:

  

- If a grid $M$ is complete—meaning every slot contains a fully assigned word with no remaining empty cells—the state is evaluated as a candidate solution and the search continues until the priority queue is empty.

- If a grid $M$ is not complete, the solver selects a single unfilled slot for expansion (the slot selection mechanism is described in §5.3). The unified domain generator (Chapter 3) is then invoked on this slot, producing a lazy stream of candidate vectors. Each candidate is placed on a copy of the grid, validated for forward consistency and structural constraints (§5.2), and if viable, inserted into the priority queue as a new state $\mathcal{S}' = (M', d+1, W \cup \{w\})$.

  

### 5.2 Heuristic Scores, Pruning, and Queue Management

  

This section documents the concrete heuristic scores, pruning strategies, and queue management policies adopted in the current implementation of the algorithm.

  

#### 5.2.1 Priority Queue Key

  

Each state is inserted into the min-heap with the following key:

  

$$\large \text{key}(\mathcal{S}) = \left(-d,\; \rho(\mathcal{S}),\; \sigma(\mathcal{S})\right)$$

  

where:

- $-d$ is the negated search depth, making it the primary criterion: deeper states—those closer to a complete solution—are always expanded before shallower ones.

- $\rho(\mathcal{S}) = |r(\mathcal{S}) - r_{target}|$ is the block ratio penalty, where $r(\mathcal{S})$ is the current ratio of black blocks to total filled cells (blocks + letters) and $r_{target}$ is a configurable target density. This penalty acts as both a floor and a ceiling: states with too few blocks are penalized because they are likely too difficult to complete; states with too many blocks are penalized because excessive fragmentation produces smaller, lower-quality words and wastes grid space. In the current implementation, $r_{target}$ is set to $0.35$.

- $\sigma(\mathcal{S})$ is the count of short words (length 2) in the current grid. Fewer short words indicate higher crossword quality.

  

With this configuration, the solver aggressively pursues the deepest partial solutions, using structural quality as a tiebreaker.

  

#### 5.2.2 Pruning at Expansion

  

After forward consistency validation (§5.1.3), candidates must pass additional structural checks before entering the queue. The grid must not contain three or more consecutive black blocks along any row or column, as this would fragment the grid into disconnected areas. Additionally, the number of short words (length 2) must not exceed that of the best solution found so far—the search never regresses in quality.

  

#### 5.2.3 Diversity Pruning

  

Since the algorithm does not terminate after its first solution, the priority queue can accumulate states that converge toward the same grid configuration. To counteract this, a diversity pruning mechanism is applied at extraction time: when a state is popped from the queue, its placed word set $W$ is compared against a reference set $W_{ref}$. If the overlap $|W \cap W_{ref}|$ exceeds a threshold fraction of $|W_{ref}|$, the state is discarded without expansion.

  

The reference set $W_{ref}$ is updated whenever a new best solution is found, and periodically refreshed to the current state's word set to prevent the reference from going stale. The effect is that the solver continuously explores structurally distinct crosswords rather than repeatedly refining minor variations of the same grid.

  

#### 5.2.4 RAM-Bounded Queue Management

  

Since each state carries a full copy of the grid matrix, the priority queue can grow to consume significant memory. To prevent out-of-memory failures, the solver periodically checks process memory usage. When it exceeds a configurable RAM limit, the queue is sorted by its composite key and the bottom half—the least promising states—is discarded. This is a lossy operation that sacrifices completeness in exchange for bounded memory, allowing the solver to run on fixed hardware without risk of crashes.