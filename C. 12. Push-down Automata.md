**PDA**'s are **FSM**'s with memory. 

#### An Exmple
---
Notice how it's impossible to construct a FSM for $(L = A^nB^n)$ since FSM's can't memorize $n$? We can overcome this by constructing a ==🟢**stack**==, and populate/pop it with each input letter read. The NFA looks a bit different:
![[Pasted image 20261020170755.png | NFA for $A^nB^n$ | 300]]
Where each step are now 3 bits in the form of $x / y /z$, where:
- $x \in \textstyle\sum^*$ is the input letter
- $y \in T^*$ is the letter to be popped from the stack
- $z \in T^*$ is the letter to be pushed to the stack

Where $T = \{@\}$ is the alphabet for the stack.  

# Building PDA for CFL
----
$$ \text{Use PDA to prove that CFL are closed under prefix}$$
Outline:
1. Start with machine $M$ that recognizes $L$, and build a new machine $M'$ on top of $M$.
2. Prove $M'$ recognizes exactly Pref(L). So:
	- every $x \in$ Pref(L) is accepted by $M'$
	- every $x$ accepted by $M'$ is in Pref(L)

So upon reading input $x$, $M'$ needs to know if there exists any continuation $y$ such that $xy \in M$.
1. **reading $x$**: $M'$ behaves exactly like $M$ 
2. **imagining $y$**: at some point determine $x$ is finished, and pretend to read input without actually consuming anything
3. **accept**: if this imaged run reaches a final state in $M$.

### Construction

We make 2 copies of each state in $M$:
- the original states $Q$ (used in phase 1 above) and a copy $\hat{Q} = \{\hat{q} | q \in Q\}$ (used in phase 2)

Note the Sipser convention we use to denote each transition in $\delta$:
$$ \delta(q,a,A) \rightarrow (p, B) $$
- *In state $q$, read input $a$ and pop $A$, then go to state $p$ and push $B$*

