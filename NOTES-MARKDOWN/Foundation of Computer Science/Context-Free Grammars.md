---
aliases:
  - context free grammar
  - context free grammars
  - context-free grammar
  - cfg
  - cfgs
  - context-free languages
  - context-free language
  - context free language
  - context free languages
---
> [!cite] Variables and Terminals
> - A **variable** is a symbol that may be substituted with another grammar rule.
> - A **terminal** is a symbol that cannot be broken down further or replaced with another rule.


A context-free grammar (CFG) is a grammar where all rules are of form:

$$\Large \underbracket{A}_{\text{single variable}}\rightarrow \underbracket{X}_{\text{any combo}}$$

This includes all grammars, regular or non-regular.

> [!hint] Difference from [[Regular Grammars]]
> Regular grammars have stricter rules, which guarantee that the [[Regular Languages|language]] associated to the grammar is regular.

> [!example]
> Assume we have a grammar with the following rules:
> 
> - $\large S\rightarrow 0A \;| \;ε$
> - $\large A\rightarrow S1$
> 
> which produces strings like:
> 
> $$\large \{ε, 01, 0011, 000111,\dots\}$$
> 
> This grammar produces the following language:
> 
> $$\large L= \{0^n1^n:n\geq0\}$$
> 
> ...which is **NON-REGULAR**.


## Context-free language

A context-free language (CFL) is a language of some CFG.

> [!hint]
> Every [[Regular Languages|regular language]] is a CFL.
