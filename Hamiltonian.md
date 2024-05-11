# Hamiltonian

- Hamiltonian as an operator and spectrum
  - mathematically an operator $H$
  - physically a spectrum of energy levels $q_i$ with probability $|c_i|^2$ when measured
  - $\{q_i\}$ is the collection of (real) eigenvalues of $H$
- Hamiltonian as a measurement
  - A quantum system is mathematically a wave function $\ket\psi$
  - Projections of $\ket\psi$ on unit eigenvectors of $H$ (observable) determines the probability of measuring the (real) eigenvalue
  - **$H$ determines possible outcomes, and $\ket\psi$ determines probability distribution of those outcomes.**
- Formulation
  - $H\ket{\psi_i}=q_i\ket{\psi_i}$ and $\braket{\psi_i|\psi_j}=\sigma_{ij}$ (always possible by selecting proper eigenvectors in each degenerate eigenspace)
  - $\ket\psi=\sum_i c_i\ket{\psi_i}\quad\Rightarrow\quad\braket{\psi|H|\psi}=\left(\sum_i c_i^*\bra{\psi_i}\right)H\left(\sum_j c_j\ket{\psi_j}\right)=\sum_i |c_i|^2 q_i$
  - Example:
    - For the Hamiltonian $X$, possible outcomes (spectrum) are $1$ and $-1$, and corresponding eigenvectors are $\ket+$ and $\ket-$. $\ket 0=\Rsr2\ket++\Rsr2\ket-$ have $|\Rsr2|^2=\frac{1}{2}$ probability of measuring $1$ and $-1$.
    - TL;DR: The Hamiltonian observable $X$ gives two outcomes: $\ket+$ and $\ket-$ encoded by their eigenvalues $1$ and $-1$.
- Quantum computational Hamiltonian
  - A system of $n$ qubits correspond to $2^n$ states, represented by a $2^n\times 2^n$ matrix $H$ with $2^n$ eigenvalues (energy configurations - a combination of $1$s and $0$s).
  - A Hamiltonian can be decomposed into $H=\sum_{i,\alpha}h_i^\alpha\sigma_\alpha^i+\sum_{i,j,\alpha\beta}h_{i,j}^{\alpha\beta}\sigma_\alpha^i\sigma_\beta^j+\ldots$
    - Sum of all one-qubit operations, then sum of two-qubit operations, then three and so on.
    - $\sigma_\alpha^i$ is the $\alpha$-th Pauli operator on the $i$-th qubit



---

- A unitary is used to implement quantum gates by evolving $U(H,t)=e^{-iHt/\hbar}$ with an engineered $H$ and precision timing.
  - $U$ is a rotation about the eigenstates of $H$ and therefore will not altering the measurement of $\ket\psi$ on $H$.
    - $\ket{\psi(t)}=U(H,t)\ket{\psi(0)}$
    - $\braket{\psi(t)|H|\psi(t)}=\braket{\psi(0)|U^\dagger HU|\psi(0)}=\braket{\psi(0)|U^\dagger UH|\psi(0)}=\braket{\psi(0)|H|\psi(0)}$ ... $U$ and $H$ commute
  - Schrödinger Equation
    - $\ket{\psi(t)}=e^{-iHt/\hbar}\ket{\psi(0)}$ satisfies $i\hbar\frac{\partial}{\partial t}\ket{\psi(t)}=H\ket{\psi(t)}$
      - $i\hbar\frac{\partial}{\partial t}\ket{\psi(t)}=i\hbar\frac{\partial}{\partial t}e^{-iHt/\hbar}\ket{\psi(0)}=i\hbar(-iH/\hbar)e^{-iHt/\hbar}\ket{\psi(0)}=H\ket{\psi(t)}$
  - Implementation of quantum gate to rotate the quantum state by $\Theta=(\theta_1,\theta_2,\ldots,\theta_n)$ about $H$
    - Apply $e^{-i\gamma Ht/\hbar}$ for a period of $t$, where $\gamma$ is an engineering parameter.
    - Example:
      - To implement rotation $R_x(\theta)$ we apply $e^{-i\gamma Xt/\hbar}$ for a period $t=\frac{\hbar\theta}{2\gamma}$.
      - To implement $X$, the period to apply the unitary (e.g., laser beam) is $\frac{\hbar\pi}{2\gamma}$ seconds.



---

- Hamiltonians, eigenvalues and phases

  - A Hamiltonian measures the energy of a quantum state (wave function) - the Schrödinger equation $H\ket\psi=E\ket\psi$.
  - $\ket{\psi_k}$ is an eigenstate of $H$. An arbitrary quantum state can be spanned by the eigenbasis of $H$: $\ket\phi=\sum_k\alpha_k\ket{\psi_k}$.
  - $H\ket\phi=\sum_k\alpha_kH\ket{\psi_k}=\sum_k\alpha_kE_k\ket\psi_k$ , and $\braket{\phi|H|\phi}=\sum_k\alpha_k^2E_k$ , the expectation value of $\ket\phi$ when measured by $H$.
  - In quantum algorithms, $H$ is represented by unitary $U(H)\equiv e^{-iH}$, of which the eigenvalues are $e^{-iE_k}$.
  - $U(H)\ket\phi=e^{-iH}\ket\phi=\sum_k\alpha_ke^{-iH}\ket{\psi_k}=\sum_k\alpha_ke^{-iE_k}\ket{\psi_k}$. The phase of $U$ represents the energies.
  - For time-independent evolution (annealing)
    - $\ket{\psi(t')}=e^{-iH(t'-t)}\ket{\psi(t)}$
    - $U(t',t)=e^{-iH(t'-t)}$. The time interval is the phase.
    - As time goes by the system will come to the minimal energy.
  - Minimum measurement on eigenstate
    - The expectation value of the minimal energy is *not* an eigenvalue but an "average".
    - The minimum expectation value should be 100% of the smallest eigenvalue (or a combination of multiple minima in degenerate case), hence by examining the eigenstate components of $\ket{\psi(t)}$ will "likely" give you the ground state energy.
  - Optimisation problems can be solved by
    - representing the problem as $H$ - e.g., a QUBO or Ising,
    - design $U(H)$ - e.g., QPE, circuit ansatz or graph embedding,
    - finding the lowest expectation value (energy) - e.g., QAOA, VQE, annealing evolution
    - interpreting the eigenstate of the minimum energy as the solution - e.g., top probability, scan through the solution set

## Hamiltonian (Classical) Mechanics

- Ref: https://en.wikipedia.org/wiki/Hamiltonian_mechanics
- Mechanical system: $(M,\mathcal L)$
  - $M$ is configuration space
  - $\mathcal L$ is Lagrangian (smooth function)
- Momenta: $p_i(\mathbf q,\mathbf{\dot q},t)\equiv\partial\mathcal L/\partial\dot q^i$
  - A function of position, speed and time, returning momentum along axis $i$
- Legendre transformation: $\mathcal L\equiv(\pmb q,\pmb{\dot{q}})\to(\pmb p,\pmb q)$
  - A mapping of position and speed to momentum and position
- Energy function $\displaystyle E_{\mathcal L}(\mathbf q,\mathbf{\dot q},t)\equiv\sum_i \dot q^i\frac{\partial\mathcal L}{\partial\dot q^i}-\mathcal L=\mathcal H\left(\frac{\partial\mathcal L}{\partial\pmb{\dot q}},\pmb q,t\right)$
- Hamiltonian $\mathcal H(\pmb p,\pmb q,t)=\sum_i p_i\dot q^i-\mathcal L(\pmb q,\pmb{\dot q},t)$


---

LaTeX

$$
\newcommand{\Rsr}[1]{\frac{1}{\sqrt{#1}}}
\newcommand{\Tr}{\mathrm{Tr}}
$$
