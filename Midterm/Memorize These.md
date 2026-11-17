### NFA -> DFA -> Min DFA
---
- How to draw (for Thompson Construction): $(a + b), (a+b)^*$? 
- subset: for computing actual symbol transitions, go to new closures if the content of that closure is not already in current closure
### CF or not?
---
- Using ==🔵**Closure Properties**==: usually we're using 2 tricks: 
	1. Intersecting $L$ with a regex (greatly simplifies $L$)
	2. Negate and compliment 

Examples (prove context-free or not):
$$ a^ib^jc^k: \: j = k \iff i = 1 $$ 
- Intersect with $ab^*c^*$ to force $i=1$ 

$$ a^ib^j: \: i \not = j $$
- Take its negation -> $A \cup \neg B$. Simplify by eliminating the RHS of the union (union with $B$)
### Pattern Searching / Matching
---
- Searching makes $\Sigma^* p$, while matching makes $\Sigma^*p \Sigma$ 

### Decision Procedures 
---
1. If $A \subset B$, then $A \cap \neg B = \emptyset$ (so you can use emptiness proof)
2. $A - B = A \cap \neg B$ (converting difference into something we know)
3. $\neg A \cap \neg B = \neg (A \cup B)$
4. If you have $A \cup B$, remove $B$ with: $(A \cup B) \cap \neg B$ 

### Ambiguity
---
Patterns for ambiguous $G$ (produces multiple parse tree):
- $S \rightarrow SS$ 
- $S \rightarrow S + S$ 
To make $G$ unambiguous, simply separate the grammar to eliminate the order:
- $S \rightarrow aSb \mid aSbb \mid \epsilon$     <- ambiguous because you can do $S$ in any order
- $S \rightarrow aSb \mid T, T \rightarrow aTbb \mid \epsilon$     <- unambiguous because we forced $aSb$ then $aSbb$.
Know how to construct unambiguous grammar for $L_{\text{set expressions}}$ (2023.3c) and $L_{arithmetic}$ (2022.5c)

**Associativity** denotes the direction of evaluation:
- $\cup$ and $\cap$ are both left and right associative: there's no order for which one to be evaluated first
	- but if they're specified as ==🔴left-associative==, then we do $(A \cup B) \cup C$ 
- $\neg$ is right-associative, observe $(\neg \neg A)$ where it has to be read as $(\neg(\neg A))$

# PDA
---
$$ \Delta = \{(q_{start}, input, pop), (q_{next}, push)\}$$  