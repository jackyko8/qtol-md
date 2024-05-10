# QUBO

Ref:

- [Quadratic Unconstrained Binary Optimisation](https://en.wikipedia.org/wiki/Quadratic_unconstrained_binary_optimization)
- [Hamiltonian](./Hamiltonian.md)

QUBO Ising solved by QAOA

- Examples:
  - Maximum Cut: $G=(V,E)$  - graph = vertices and edges, partition $V$ into two groups to maximum number of $E$ connecting different groups. Problem size is $2^N$, exponentially scaled.
  - Ising Hamiltonian to encode Max Cut, and the solution is obtained by minimising the Hamiltonian.
  - Cost function: $\hat H_C=\sum_{i>j}J_{i,j}z_iz_j$, where $z_i$ is the $z$ measurement of qubit $i$ and $J$ is the weight (1 means connected)






---

### jko

$$
\require{cancel}
\newcommand{\Ket}[1]{\left|{#1}\right\rangle}
\newcommand{\Bra}[1]{\left\langle{#1}\right|}
\newcommand{\Braket}[1]{\left\langle{#1}\right\rangle}
\newcommand{\Rsr}[1]{\frac{1}{\sqrt{#1}}}
\newcommand{\RSR}[1]{1/\sqrt{#1}}
\newcommand{\Verti}{\rvert}
\newcommand{\HAT}[1]{\hat{\,#1~}}
\DeclareMathOperator{\Tr}{Tr}
$$

