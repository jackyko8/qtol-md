# Basics of Quantum Mechanics

## [Postulates](https://en.wikipedia.org/wiki/Mathematical_formulation_of_quantum_mechanics)

1. The state of an isolated physical system is represented, at a fixed time $t$, by a state vector $\ket\psi$ belonging to a Hilbert space $\mathcal H$ called the *state space*.
2. The Hilbert space of a composite system is the Hilbert space [tensor product](https://en.wikipedia.org/wiki/Tensor_product) of the state spaces associated with the component systems. For a non-relativistic system consisting of a finite number of distinguishable particles, the component systems are the individual particles.
   1. Every measurable physical quantity $A$ is described by a Hermitian operator $A$ acting in the state space $\mathcal H$. This operator is an observable, meaning that its eigenvectors form a basis for $\mathcal H$. The result of measuring a physical quantity $A$ must be one of the eigenvalues of the corresponding observable $A$.
   2. When the physical quantity $A$ is measured on a system in a normalized state $\ket\psi$, the probability of obtaining an eigenvalue (denoted $a_n$ for discrete spectra and $\alpha$ for continuous spectra) of the corresponding observable $A$ is given by the *amplitude squared* of the appropriate wave function (projection onto corresponding eigenvector).
   3. If the measurement of the physical quantity $A$ on the system in the state $\ket\psi$ gives the result $a_n$, then the state of the system immediately after the measurement is the normalized projection of $\ket\psi$ onto the eigensubspace associated with $a_n$​.
3. The time evolution of the state vector $\ket{\psi(t)}$ is governed by the Schrödinger equation, where $H(t)$ is the observable associated with the total energy of the system (called the [Hamiltonian](https://en.wikipedia.org/wiki/Hamiltonian_(quantum_mechanics))).
4. The wavefunction of a system of $N$​ identical particles (in 3D) is either totally symmetric (Bosons) or totally antisymmetric (Fermions) under interchange of any pair of particles.

### Illustration of the postulates

1. **State space**: A quantum state is a state vector $\ket\psi$ in Hilbert space $\mathcal H$.
2. **Composite system**: The state space of a composite system is the tensor product of individual state spaces. The composite eigenbasis (with each basis vector a tensor product of basis vectors of individual state spaces) corresponding to a measurement of the composite system.
   1. **Observable**: The dimension of $\mathcal H$ equals to the number of measurable (real) physical quantities, each being an eigenvalue $\lambda_n$ of an normalised eigenvector $\ket{\psi_n}$ in the eigenbasis of $\mathcal H$.
   2. **Measurement probability**: The square of the (complex) amplitude of the normalised state vector $\ket\psi$ on $\ket{\psi_n}$, denoted by $a_n$, is the probability of obtaining $\lambda_n$ in the measurement.
   3. **Measurement collapse**: The system state "collapses" to the eigenstate $\ket{\psi_n}$ right after the measurement that obtain $\lambda_n$.
3. **Evolution**: $\ket{\psi(t)}$ evolves following the Schrödinger equation, $\hat H(t)=i\hbar\frac{d}{dt}$ where the Hamiltonian $\hat H(t)$ is the observable of the total energy of the system.

## Observables

- Observables: operators to a wave function to obtain a physical quantity distribution
  - Position operator: $\hat x=x$.
    - Position is an eigenvalue of $\hat x\ket{\psi_0}=x_0\ket{\psi_0}$.
    - $|\ket{\psi_0}|^2$ is the probability of realising the measurement of the eigenvalue $x_0$.
    - Position is visualised as the "swell" of the wave function.
  - Momentum operator: $\hat p=-i\hbar\frac{\partial}{\partial x}$.
    - Momentum is an eigenvalue of $\hat p\ket{\psi_0}=p_0\ket{\psi_0}$.
    - $|\ket{\psi_0}|^2$ is the probability of realising the measurement of the eigenvalue $p_0$.
    - Momentum is visualised as the wave function spatial frequency, the shorter the wavelength the higher the momentum).
  - Energy operator (Hamiltonian): $\hat H=\hat T+\hat V$
    - Kinetic energy operator: $\hat T=\frac{\hat p^2}{2m}=-\frac{\hbar^2}{2m}\frac{\partial^2}{\partial x^2}$.
    - Potential energy: $\hat V$ depends on the set up, such as a potential field or SHM.
    - Energy is an eigenvalue of $\hat H\ket{\psi_0}=E\ket{\psi_0}$.
    - Schrödinger equation requires $\hat H=i\hbar\frac{\partial}{\partial t}$
      - Total energy is an eigenvalue of $\hat H\ket\psi=i\hbar\frac{\partial}{\partial t}\ket\psi=-\frac{\hbar^2}{2m}\frac{\partial^2}{\partial x^2}\ket\psi+V\ket\psi=E\ket\psi$.
      - $|\ket{\psi_0}|^2$ is the probability of realising the measurement of the eigenvalue $E$.
    - Total energy is visualised as the wave function temporal frequency, the faster the rotation the higher the energy.
      - When the system is going up the potential well, its temporal frequency becomes faster.

### Measurement

A measurement operator is in the form of $\ket{p_0}\bra{p_0}$, where $p_0$ is an eigenstate of the observable. For example, $\ket{p_0}\braket{p_0|\psi}$ projects $\ket\psi$ onto $\ket{p_0}$. $\braket{p_0|\psi}$ is the amplitude and the probability of measuring $p_0$ is $|\braket{p_0|\psi}|^2$​​.

Experimentally, the measurement operator is "casted" on the wave function to "extract" the real eigenvalue.

## Quantisation phenomena

Quantisation phenomena, such as discrete levels of (total) energy, are the result of boundary conditions when solving the Schrödinger equation. For example, in the one-dimensional "particle in a box" problem, the value of $\psi$ needs to be $0$ at both end. Another example is the orbitals, in which the cycle of waves around the nuclear needs to be a whole number.

On the other hand, position and momentum measurements are continuous. Their Hilbert space has a dimension of infinity.

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
