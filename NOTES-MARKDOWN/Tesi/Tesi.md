## Chapter 3

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

## 3.3 Lazy Evaluation of Infinite Combinations

Since a single domain encapsulates all valid permutations of vocabulary, structural blocks ($\text{⯀}$), and empty spaces ($\text{⬚}$), the resulting search space is exponentially larger than a traditional static domain. Generating and storing all possible vectors in memory is computationally unfeasible. 

This limitation is bypassed through lazy evaluation, which transforms the domain from a static array into an on-demand generator. Crucially, this generator is not a blind iterator; its combinatorial yield is actively directed by heuristics. 

Because both topology shaping (block placements) and word assignment (vocabulary) coexist within the exact same continuous search space, the heuristics achieve maximum flexibility. They can evaluate the physical shape of the grid and the linguistic constraints of the dictionary simultaneously