1. Assume $L = CFL$ -> there exists pumping length $k$ for $L$ 
2. Pick string $w \in L, |w| \geq k$
3. Observe all decompositions of $w = uvxyz$, such that:
	- $|vy| \geq 1$     %% at least one is non-empty%%
	- $|vxy| \leq k$     %% restricts the size of vxy %%
4. Construct $w' = uv^qxy^qz$. 
5. Every possible case must fail for $L$ to NOT be context-free.
		- cases are distinguished by the placement of $xyz$ in 

# Examples
---

$$L = \{a^nb^nc^n | n \geq 0 \}$$
1. Assume $L = CFL$ -> there exists pumping length $p$ for $L$ 
2. Pick $w = a^p b^p c^p \in L, |w| \geq p$ 
3. Observe $w = uvxyz$: 

 