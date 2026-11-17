==**Grammars**== are rules that convert variables $A \rightarrow B$; any occurrence of $A$ are replaced with $B$.

==🔴**Context-Free Grammars**== are all rules of the form:
- $A \rightarrow X$, where $A$ is a single variable and $X$ can be any strings
Examples:
- $S \rightarrow aSb$ is context free
- $A \rightarrow BCD$ is context free
- $aA \rightarrow ab$ is NOT context free

==🔴**Derivation**== is the process to produce a valid string $X \in \sum^*$ from starting string $S$ in a language through **CFG**:
- $S \Rightarrow ... \Rightarrow X \in \sum^*$ 

# Build CFG for CFL
---
Instead of following a list of steps to obtain a result, $CFG$ is built using intuition. 

Every $CFG$ is just a combination of the following 4 patterns:

| Goal                            | Pattern                              | Notes                    |
| ------------------------------- | ------------------------------------ | ------------------------ |
| Repeat everything ($\sum^*$)    | $X \rightarrow aX \| bX \| \epsilon$ | `while()`                |
| Symmetry ($a^nb^n$)             | $X \rightarrow aXb \| \epsilon$      | sandwhich                |
| Consecutive Letters (a, then b) | $X \rightarrow AB$                   | calling helper functions |
| Giving a choice (a, or b)       | $X \rightarrow A \| B$               | `if-else`                |
|                                 |                                      |                          |

# Leftmost Derivations & Ambiguity
---
If, in a **derivation**, the leftmost nonterminal in the sentential form is rewritten, we denote this step as $\Rightarrow_m$, or "leftmost derivation". 

For example, with CFG $G = (S \rightarrow SS \: | \: \epsilon)$, we can derive terminal string $\epsilon$ in 2 different ways:
1. $S \Rightarrow_m \epsilon$
2. $S\Rightarrow_m SS \Rightarrow_m S \Rightarrow_m \epsilon$ 

This makes $G$ ==🔴ambiguous==, since we have multiple nontrivial ways to get the same word. 

# Examples of Ambiguous Grammars
---
$$ S \Rightarrow aSb | \epsilon$$ *Unambiguous* -> you can only get one derivation.

$$ S \Rightarrow aSb  |ab | \epsilon $$
*Ambiguous*. We can get $S \Rightarrow abb \Rightarrow ... \Rightarrow aabb$ in different derivations.

$$ S \Rightarrow SaS | b$$ *Ambiguous* because symmetry implies ambiguity (draw parse tree). 

$$ S \Rightarrow aSb | aSbb | \epsilon $$

*Ambiguous* because we can derive in different orders but still get $\epsilon$ (S->1st -> 2nd = S->2nd->1st)
- *Unambiguous equivalent*: separate the grammar to eliminate the order:
	- $S \Rightarrow aSb |T$ 
	- $T \Rightarrow aTbb | \epsilon$ 