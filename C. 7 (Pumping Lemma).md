
The [Pumping Lemma](https://en.wikipedia.org/wiki/Pumping_lemma_for_regular_languages) states that all regular languages must have a section of itself that can be repeated (or *pumped*) any number of times, and the result is still in that language. Used to proof if a language is regular.

1. Assume $L$ is regular -> there exists pumping length $k$  where all strings $|w| > k$ can be pumped.
2. Suggest string $w \in L$ such that $|w| \geq k$, use $k$ as exponent(s) %% w must contain all letters of L and is a general example%%
3. Divide $w = xyz \in L$
	- Substitute the first instance of exponent $k$ with $(m, n)$
4. Pump $y$ by $q$: $w = xy^qz \in L$ 
	- $q = \text{pumping constant}$  
	- Assign $q$ to $y$'s exponents and simplify the expression $xy^qz$ 
5. Consider different $q$ values for $w$ such that in all cases $w \not\in L$ 
6. **Conclusion**: once $w$ is pumped, it's $\not\in L$, so $w$ cannot be pumped. Since all regular languages can be pumped, $w$ is NOT REG.

# Example Template
---
1. Assume $L$ is regular -> there exists pumping length $k$ for $L$
2. Choose string $s = ..., \: |s| \geq k$ ; $s \in L$ because ...
3. Observe all decompositions of $w = xyz$ such that $|xy| \leq k$ and $|y| \geq 1$:
	- $x = ...$,
	- $y = ..., m > 0$, 
	- $z = ...$ 
4. Choose $q$ such that $xy^qz \not \in L$:
	- $w$ = ...
5. *Since the Pumping Lemam22*
