
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

Because the domain $D_{uni}$ generates combinations of text, structural blocks ($\text{⯀}$), and empty spaces ($\text{⬚}$), a single variable resolution possesses great geometric flexibility. 

Instead of strictly mapping one word to a predefined boundary, the algorithm evaluates contiguous segments and executes assignments over time. Geometrically, when placing a word $w$ (of length $k$) within a slot of length $L$, the generated vector $v$ is divided into distinct spatial regions:

$$\large v = (\underbrace{\text{⬚}, \dots, \text{⬚}}_{\text{Deferred Left}}, \underbrace{\text{⯀}}_{\text{Left Boundary}}, \underbrace{w_1, \dots, w_k}_{\text{Placed Word}}, \underbrace{\text{⯀}}_{\text{Right Boundary}}, \underbrace{\text{⬚}, \dots, \text{⬚}}_{\text{Deferred Right}})$$
Trivially, there will be no deferred space if the boundary coincides with the edge of the slot.

This structure executes assignments through the following mechanics:
- **Lazy combinatorial generation**: The generator systematically yields all possible spatial combinations of any word that can fit into the slot (even words shorter than the slot’s length). These resolutions ensure that the configuration yields an assignment in which the selected word is either bounded by new blocks or existing edges of the slot. 
- **Deferred Generation**: The algorithm intentionally leaves the remainder of the vector unassigned (the operators). By leaving these spaces blank (e.g., generating ), the initial assignment dynamically fractures the original space into new, independent contiguous sub-slots to be processed later. 

The remaining empty spaces simply become new variables in the CSP. As the search progresses, these newly defined sub-slots are resolved independently—either by intersecting perpendicular domains or by subsequent parallel iterations—allowing multiple words to naturally populate the original row or column. 

In this continuous formulation, the assignment of a single domain organically shapes the matrix topology, places words from the vocabulary, and defines the exact boundaries for future variables all at once.

### 3.3 Lazy Evaluation of Infinite Combinations

Since a single domain encapsulates all valid permutations of vocabulary, structural blocks ($\text{⯀}$), and empty spaces ($\text{⬚}$), the resulting search space is exponentially larger than a traditional static domain. Generating and storing all possible vectors in memory is computationally unfeasible. 

This limitation is bypassed through lazy evaluation, which transforms the domain from a static array into an on-demand generator. Crucially, this generator is not a blind iterator; its combinatorial yield is actively directed by heuristics. 

Because both topology shaping (block placements) and word assignment (vocabulary) coexist within the exact same continuous search space, the heuristics achieve maximum flexibility. They can evaluate the physical shape of the grid and the linguistic constraints of the dictionary simultaneously.

---

## Chapter 4 - Hierarchical Constraint Caching

### 4.1 The Constraint Cache Tree

To support the rapid combinatorial expansion of the lazy generator, the algorithm relies on a custom hierarchical caching tree. Because the generator constantly demands valid dictionary words to fulfill newly formed segments, filtering the entire dataset for every iteration is computationally prohibitive.

The architecture of this tree is organized by the following hierarchy:

- **Root nodes:** The root nodes (multiple ones) of the tree consists of nodes representing completely unconstrained slots of various lengths. For example, a root node for a length of five contains all five-letter words in the vocabulary, represented purely by wildcards.

- **Child-nodes:** Every node in the tree represents a specific constraint pattern, and contains all the words in the vocabulary after filtering according to the constraint. A child node always enforces a stricter constraint than its parent node. Consequently, the list of valid words within any child node is a strict, smaller subset of the words contained in its parent.


When the solver requests the list of words that fit a specific constraint, the data structure is navigated and updated through the following operations:

When the solver requests the list of words that fit a specific constraint, the tree does the following:
- **Downward Traversal:** The tree gets traversed from the root to locate the most specific existing parent that fully encompasses the new constraint pattern. The new node is then populated by filtering only the heavily reduced wordset of that exact parent, bypassing a full dictionary scan.
- **New Constraint Caching:** Once the new constraint is added as a child to the located parent, it triggers a self-organizing mechanism. The new node evaluates its siblings (the other existing children of its parent). If any sibling represents a constraint that is actually a stricter subset of the _new_ node, the new node "kidnaps" it: the sibling is removed from the original parent and reassigned as a child of the newly created node.

This insertion logic ensures that the tree remains perfectly layered and optimized as new constraints are discovered on the fly.