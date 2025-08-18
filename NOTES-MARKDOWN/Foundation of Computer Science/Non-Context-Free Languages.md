![[Pasted image 20250817155702.png]]


The fundamental distinction between these language classes lies in their **production rule formats**:

- **[[Context-Free Grammars|CFGs]]**: have the simplest structure, with productions of the form **A → α**, where A is a single nonterminal symbol and α is any string of terminals and/or nonterminals. 

> [!hint]
> The replacement of A with α is completely **independent of surrounding context**, regardless of which symbols surround it, A can always be replaced by α.


- **Context-Sensitive Grammars (CSG)** introduce context dependency through productions of the form **αAβ → αγβ**, where the nonterminal A can only be replaced by γ when it appears in the specific context of α and β. 

> [!hint]
> This context preservation means that α and β remain unchanged on both sides of the production rule.

> [!warning]
> A C.S. language cannot contain the symbol $ε$.


- **Unrestricted Grammars (Type-0)** have the most general form **α → β**, where α and β are arbitrary strings of terminals and nonterminals with no restrictions except that α cannot be empty.

> [!tldr]
> ![[Pasted image 20250817170727.png]]
