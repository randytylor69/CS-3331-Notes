
$$ (K, \Sigma, \Gamma, \delta, s, H) $$ 
- $K$ is a finite set of ==🔴states==
- $\Sigma$ is the ==🔴input alphabet==, $\square \subset \Sigma$ 
- $\Gamma$ is the ==🔴tape alphabet==, $\Sigma, \square \subset \Gamma$ 
- $s$ is the starting state
- $H$ is the halting state(s)
- $\delta$ is the transition function of:
$$ (q_0, \: \Gamma_0) \: \Rightarrow \: (q_1, \Gamma_1, \leftarrow \text{or} \rightarrow) $$ Which reads: *starting from state $q_0$ on tape char $\Gamma_0$, goes to state $q_1$ and rewrites $\Gamma_0$ to $\Gamma_1$, move tape head left or right*. 

# Useful Notations
---
	
| Machine                      | Meaning                                                                                                                                                                         |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| $R_{a, b}$                   | 1. Go right until first occurrence of $a$ or $b$                                                                                                                                |
| $L_{x \leftarrow a,b}$       | 1. Go left until first occurrence of $a$ or $b$<br>2. Set $x$ to that value                                                                                                     |
| $L_{x\leftarrow a,b} \: R x$ | 1. Go left until first occurence of $a$ or $b$  %% this is the same as above%%<br>2. Set $x$ to that value %%still the same%%<br>3. Write $x$ value to the square on the right. |
| $\# R_{\square}$             | 1. Write hash<br>2. Go right until seeing $\square$                                                                                                                             |
|                              |                                                                                                                                                                                 |
| $R_{x \leftarrow \neg \#}$   | 1. Go right until first occurence of non-hash symbol<br>2. Set $x$ to that symbol                                                                                               |

# Computing a Function
---
Much like solving a sophisticated programming problem, we construct subroutines and combine them to compute a sophisticated function $f$ with a Turing Machine $M$. 

#### Example
Construct Turing Machine $M$ that computes the function below:
$$ f(w) = ww $$
1. Understand that $M$ must perform: $\underline{\square} w \square \: \rightarrow \: \underline{\square}ww\square$  

%% directly building M would be silly; how do we know when does w ends for its identical copy to start? %% 

2. We will construct 2 subroutines (submachines) $C$ and $S$:
	- $C$ is the *copy machine* that performs: $\underline{\square}w\square \: \rightarrow \: \underline{\square} w \square w$  
	- $S$ is the *shifting machine* that performs: $\square u \underline{\square} w \square \: \rightarrow \: \square u w \underline{\square}$ 

%% directly combining C &  S wold be silly; the tapehead would end up on the wrong side of w'%% 
	
3. Then we simply combine the subroutines to construct $M$: $>CSL_{\square}$   



