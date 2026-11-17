*Prove that CFL are closed under Prefix*.

### Via CFG
---
1. Let $L$ be context-free language and there exists context-free grammar $G$ for $L$. 
	- $G$ is in *Chomsky Normal Form*: $A \rightarrow BC$, or $A \rightarrow a$  %% this greatly simplifies our workload, since we only need to analyze 2 cases: if the prefix falls in B (so C is completely discarded), or C (so part of C is kept) %%

2. $G$ can be represented by a 4-tuple:
$$G = (V, \Sigma, R, S)$$

- Where $V$ is a finite set of all nonterminals, $\Sigma$ is a finite set of all terminals, $R$ is the rule for $G$, and $S$ is the starting variable. 
- We can now form a new context-free grammar $G'$ for $\text{Pref}(L)$ with a modified 4-tuple:
$$G' = (V\cup V', \Sigma, R \cup R', S)$$

3. Build the new rule $R'$ 
4. QED

### Via PDA
---
1. Let $L$ be accepted by a PDA:

$$M = (Q, \Sigma, \Gamma, \delta, q_0, Z_0, F)$$

- And Pref(L) be accepted by another PDA:

$$M = (Q', \Sigma, \Gamma, \delta', q_0, Z_0, F')$$

