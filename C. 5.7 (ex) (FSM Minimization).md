# Indistinguishable Strings & Equivalance Classes
---

$x \approx_L y$ means the two strings are indistinguishable (or *equivalent*) if no matter what's appeneded to them, either they'll be in L or neither will:
$$ \forall x, y \in \textstyle \sum^*: \space \space x \approx_L y \space \space \iff \space \space \forall z \in \textstyle\sum^*\space(xz\in L \iff yz \in L)nnn  $$ 
For example, consider the following alphabet and language:

- $\textstyle\sum = \{a, b\}$ 
- $L = \{w \in \textstyle\sum^*: w \space \text{has at least 2 a's}\}$ 

Then we can construct some equivalance classes for $\approx_L$ (or, *the equivalance relations with respect to L*):

- $\{\epsilon, b, bb, bbb, ...\}$ 
- $\{a, ab, ba, bab, abb, ...\}$ 
- $\{aa, aab, bbaab, ...\}$ 

Why? Because if we tack on any string $w \in \textstyle\sum^*$ by the end of any 2 elements of the same class, the result will be the same (accepted/unaccepted).

Each equivalence class correspondes to one state on the FSM, we can construct a minimal FSM with the above information. 
# Exercises
---
### Question (slide 14):

-  $\textstyle\sum = \{a, b\}$ 
-  $L = aab^*a$ 

Find the equivalence classes of $\approx_L$.

### Solution

First, note that the accepting pattern is `a + a + (0 or more b) + a`. From this pattern we can construct a graph:

![[Pasted image 20260920140822.png | 400]]
Since the number of equivalence classes is equal to the number of states, we can just base each class off each state. The content of the class is simply the string input up until that class:

- $[\epsilon ] \not\in L$   (state `1` takes no input)
- $[a] \not\in L$  (state `2` takes input `a`)
- $[aab^*] \not\in L$ (state `3` takes input from the previous state **as well as itself!** )
- $[aab^*a] \in L$  (state `4` is the accepting state)
- $[b\textstyle\sum^*, aab^*a\textstyle\sum^*] \not\in L$  (state `5`. Note that if a state takes all possible inputs from itself, then we append $\textstyle\sum^*$ to its class member)