Turing Machine encoding is the same as turning TM -> strings ($M \rightarrow w$), helps us solving complicated problems. So which part of the Turing Machine tuple should be encoded?
$$ (K, \Sigma, \Gamma, \delta, s, H) $$ 
Everything -  but mainly $K$, $\Gamma$, $\delta$.

### Encoding $K$ 
---
If we have all states:
$$ K = \{p_0, p_1, y, n\} $$ 
Then we enumerate through $K$ and encode each state with a ==🔵unique binary number== as well as a ==🔵prefix==:
In this case, the binaries will be $\{00, 01, 10, 11\}$:
- $p_0 = q_{00}$ 
- $p_1 = q_{01}$
- $y = y_{10}$ 
- $n = n_{11}$ 

### Encoding $\Gamma$
---
If we have all tape alphabet:
$$ \Gamma = \{a,b,c,d,\square\}$$ 
The binaries will be $\{000, 001, 010, 011, 100\}$, and prefix be universally $a$ (so $a_{000}, a_{001}, \text{etc.}$) 

### Encoding $\delta$
---
Note that all a $\delta$ is is just: 

$$ \delta = (\text{state}, \text{symbol}, \text{state}, \text{symbol}, \text{move})$$ 
And we literally represent each part with the newly encoded symbol used previously. 