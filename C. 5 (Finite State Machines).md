
# How a FSM works
---
A **finite state machine** is just a collection of states with attached rules on how you move between states. 

- Start in the initial state, begin reading the input string, every state must have exactly one way to progress for every possible input.
- When you run out of inputs, or reaches a state that will always return **accepted/rejected** no matter future inputs, you stop and evaluate the result. 

#### Example

A **FSM** with pattern *All strings where `2` and `3` subsequentially appear, OR strings that start with `1` and has `1`, `2` and `3` as inputs*. An **acceptable** state is an input string that satisfies the above pattern, while all other inputs are **unacceptable**.

![[newscreenshot_090 1.jpg | 500]]

- Note for every state ($q_0, q_1,$ etc.) we have one valid path for each future inputs
- The **acceptable state** is doubly circled; that's our goal. 

#### Definition

Formally, a DFA is a 5-member tuple of $M = (Q, \sum, \delta, q_0, q_f)$, where:

- $Q$ is a finite set of states (i.e. $q_0, q_1, q_2, ..., q_n$)

- $\sum$ is a finite alphabet (i.e. $\{1, 2, 3\}$)

- $\delta$ is a transition function where $\delta(q, w) = q'$ 

- $q_0$ is the starting state

- $q_f$ is the **accepting state** (or, final state)


# How a NDFA works
---
Non-deterministic finite automata works the same way as a DFA with an important distinction: there are *more* than one possible progress from the current input. 

