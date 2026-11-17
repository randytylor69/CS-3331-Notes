# Question 1
---
Prove a language is regular or not. If it is, then:

- construct the minimal DFA, or 
- construct the NFA then convert to DFA (include trap/dead states), then minimize the DFA
- convert one machine into a simple regex (can also construct regex from scratch)

### Solution (case 1: regex -> NFA -> DFA -> Equiv.classes -> Min DFA)

1. Determine the regex
2. Regex to NFA conversion:
	1. Build small NFA for individual components of the regex then slowly merge them to the original regex:
	
	2. If you need to ==Concatenate== 2 comps:
		- Epsilon the accepting state of the first comp into the starting state of the second comp (nullify the first state) 
		
	3. If you need to ==Kleene Star=== a comp:
		- Create a accepting state and epsilon it into the starting state of the current comp (because Kleene star allows empty states), then connect the accepting state of the current comp into the one that we created 
		
	4. If you need to ==Union== two comps:
		- Create a state and epsilon it into both comps
		
3. NFA to DFA conversion:
	1. Find the $\epsilon$ closure of the starting state ("where can we go via only $\epsilon$'s?") (i.e. $\{q_0, q_1\}$)
	2. Find all possible transitions (from alphabet) that our new closure state will go to. If a transition is missing, then it goes to the empty set $\{\varnothing\}$ 
	3. The state that our closure goes to should include the $\epsilon$ closure of the target state! 
	4. Finally, the accepting state(s) in our DFA should include the accepting state(s) in our NFA

4. Minimize the DFA:
	1. Divide into equivalence classes. 
	2. $\equiv_0$ has 2 sets: the accepting state(s) and unaccepting state(s)
	3. For each 2 states in the unaccepting set: if their destination states are in one set, then they're *equivalent*, vice versa
		- If they're equivalent, then they go to one set in $\equiv_1$
		- If they're not, then one would go to a new set
	4. Repeat until all sets are went through. Exit when two equivalences are identical. 

### Solution (case 2: DFA -> Equiv.classes -> Min DFA -> Regex)

### Solution (case 3: Nonregular Language: [Pumping Lemma](https://youtu.be/x2J5kaf6gjg?si=JzbY-5Y2rtbG05VI) )

We will proof by contradiction to show that language $L$ is not regular. So:

1. Assume $L$ **is regular**, so there exists integer $p$ as the "pumping length" for the Pumping Lemma. 
2. Pick an accepted string $w$ such that $|w| \geq p$  (can use $p$ as exponents of certain letters in $w$)

3. $w$ can de-composite into $xyz$, satisfying the following conditions:
	- $|xy| \leq p$ 
	- $|y| \geq 1$ 
	- $xy^i z \in L$ 

	1. Substitute $x$ and $y$ with valid letters in $L$ and exponent $\alpha, \beta, ...$ within the length contraint 
	2. Obtain $z$ (we already know $xyz$ and $yz$)
	3. Simplify the expression to obtain an contradiction



# Question 2
---
***Construct minimal DFA for multi-pattern matching and searching***
- See slides 43-45 for Regular Expression chapter. 
- For matching, build DFA for $L(\sum^* \text{pattern} \sum^*)$. For searching, $L(\sum^* \text{pattern})$ 

***Describe the equiv.classes for certain languages using regex***
- For each (final) distinct class for this language, write regex to get from the initial state to that state.

***Test the equiv.relations of 2 strings*** $u, v$
- They're equivalent if they both belong to $L$.

# Question 3
---
***Proof a problem is decidable - YOU DONT HAVE TO ACTUALLY SOLVE IT*** 

