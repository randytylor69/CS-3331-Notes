[Lecture Slides (empty)](https://www.csd.uwo.ca/~ilie/courses/CS3331_secure/Ch01-04Intro.pdf) 
#### Kleene Star/Closure
---
The **Kleene Star** ( * ) operator on an [alphabet](https://en.wikipedia.org/wiki/Alphabet_(formal_languages)) $V$ generates the set of $V^*$ of all finite-length strings over $V$. 
$$
V = \{a, b, c\}
$$
$$
V^* = \{\epsilon, a, b, c, ab, bc, abc...\}
$$

#### Prefixes
---
$s$ is a prefix of $t$, *iff* for all possible strings $x$ in alphabet $\textstyle\sum$ , $t\space=\space sx$. Or: 
$$\exists x \in \textstyle \sum^* (t \space = sx)$$For example, the **prefixes** of $abba$ are: $\{\epsilon, a, ab, abb, abba\}$. 

Question: what are the following languages $L$ ?

1. $$ L = \{W \in \{a, b\}^*: \text{no prefix of w contains b}\} $$
2. $$ L = \{W \in \{a, b\}^*: \text{no prefix of w starts with a}\} $$ 
3. $$ L = \{W \in \{a, b\}^*: \text{every prefix of w starts with a}\} $$ 
#### Diagonalization
---
**Diagonalization** is a method used to proof that:
- Integers are *countable* (i.e. 1, 2, 3, ...)
- Rational numbers are *countable* (i.e. $\frac{1}{2}$ )
- Irrational numbers are *uncountable* (i.e. $\pi$ )

The synopsis is to obtain one matrix of each of the above sets, the find interesting patterns on the diagonal of each matrix to prove that the countability of the set (lecture slide contains actual notes). 

`foobar` 

#### Chapter 3: The Big Picture
---
We can encode everything into strings. For any question, a language can be formed as the answer. 

Grammar generates Language, Language accepts Machine. 

- For example; a book about C++ includes everything about C++, which is its grammar. The GCC compiler is the Machine that deals with the C++ and check if the code is grammatically correct. 

