
#### Definition

Say any word in $L$ is made of $sz$, where $s$ = prefix, $z$= suffix. 
Now, if you can find an **infinite list** of prefixes $S = \{s_1, s_2, s_3, ... \}$ where any 2 prefixes can be ==🔵distinguished== by some suffix $z$, then the language is not regular - because a DFA would need **infinite number of states** to keep them all separate. 
- $z$ ==🔵distinguish== $s_1$ and $s_2$ if $s_1z \in L$ and $s_2z \not \in L$. 

#### 4-Step Process

1. Pick infinite list of prefixes $S$: a pattern of strings that force the machine to count something unbounded (i.e. $\{a^i \: |\: i \geq 1\}$)
2. Pick 2 arbitrary strings $s_1, s_2 \in S$ 
3. Pick suffix that will make $s_1z \in L$ and $s_2z \not \in L$
4. Conclude that since there $z$ will distinguish any 2 pairs in the infinitely long list $S$, there would exist infinitely many equivalence classes, which makes the language not regular. 

