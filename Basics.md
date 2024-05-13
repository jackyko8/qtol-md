# Basics of Quantum Mechanics

## Postulates

Ref: [Postulates](https://en.wikipedia.org/wiki/Mathematical_formulation_of_quantum_mechanics)

1. The state of an isolated physical system is represented, at a fixed time $t$, by a state vector $\ket\psi$ belonging to a Hilbert space $\mathcal H$ called the *state space*.
2. The Hilbert space of a composite system is the Hilbert space [tensor product](https://en.wikipedia.org/wiki/Tensor_product) of the state spaces associated with the component systems. For a non-relativistic system consisting of a finite number of distinguishable particles, the component systems are the individual particles.
   1. Every measurable physical quantity $A$ is described by a Hermitian operator $A$ acting in the state space $\mathcal H$. This operator is an observable, meaning that its eigenvectors form a basis for $\mathcal H$. The result of measuring a physical quantity $A$ must be one of the eigenvalues of the corresponding observable $A$.
   2. When the physical quantity $A$ is measured on a system in a normalized state $\ket\psi$, the probability of obtaining an eigenvalue (denoted $a_n$ for discrete spectra and $\alpha$ for continuous spectra) of the corresponding observable $A$ is given by the *amplitude squared* of the appropriate wave function (projection onto corresponding eigenvector).
   3. If the measurement of the physical quantity $A$ on the system in the state $\ket\psi$ gives the result $a_n$, then the state of the system immediately after the measurement is the normalized projection of $\ket\psi$ onto the eigensubspace associated with $a_n$​.
3. The time evolution of the state vector $\ket{\psi(t)}$ is governed by the [Schrödinger equation](./Schrödinger Equation.md), where $H(t)$ is the observable associated with the total energy of the system, the [Hamiltonian](./Hamiltonian.md).
4. The wavefunction of a system of $N$​ identical particles (in 3D) is either totally symmetric (Bosons) or totally antisymmetric (Fermions) under interchange of any pair of particles.

### Illustration of the postulates

1. **State space**: A quantum state is a state vector $\ket\psi$ in Hilbert space $\mathcal H$. A state vector that is not a basis vector of $\mathcal H$ can be expressed as a superposition of the basis vectors, forming a linear combination of these non-trivial elements.
2. **Composite system**: The state space of a composite system is the tensor product of individual state spaces. Each eigenstate in the composite system is a tensor product of eigenstates in individual state spaces. The behaviour of composite systems exhibits as the entanglement phenomenon.
   1. **Observable**: The dimension of $\mathcal H$ equals to the number of measurable physical (real) quantities, each being an eigenvalue $\lambda_n$ of an normalised eigenvector $\ket{\psi_n}$ in the eigenbasis of $\mathcal H$.
   2. **Measurement probability**: Eigenvalues $\lambda_n$ are the only possible measurement outcomes. The probability of measuring $\lambda_n$ is the square of the (complex) amplitude of the normalised state vector $\ket\psi$ on eigenstate $\ket{\psi_n}$ - the [Born Rule](https://en.wikipedia.org/wiki/Born_rule).
   3. **Measurement collapse**: The system state "collapses" to the eigenstate $\ket{\psi_n}$ right after the measurement that obtain $\lambda_n$. Further measurements will obtain $\lambda_n$ with certainty.
3. **Evolution**: $\ket{\psi(t)}$ evolves following the Schrödinger equation, $\hat H(t)=i\hbar\frac{d}{dt}$ where the Hamiltonian $\hat H(t)$​ is the observable of the total energy of the system.

The evolution postulate governs the behaviours of a quantum system, much like the Newton's laws governing classical systems. The wave function evolves deterministically; the probability nature of a quantum system lies in the measurement. The phase factor $i$​​ in the Schrödinger equation is to make the eigenvalue real (non-imaginary). See [Quantum Operators](https://youtu.be/LZie2QC5Jbc).

### Visualisation

#### Wave function as a complex field in space-time

A quantum state is represented as a wave function, which is a complex function in space and time domains: $\psi(\mathbf r,t)$ or $\ket\psi$ in the Braket notation (with the function domains implied). It follows that

- $\bra\psi=\psi(\mathbf r,t)^*$,
- $\braket{\phi|\psi}=\int_{\mathbb R^3}\phi(\mathbf r,t)^*\psi(\mathbf r,t)~dx$​, and
- $|\ket{\psi}|=\braket{\psi|\psi}=\int_{\mathbb R^3}|\psi(\mathbf r,t)|^2dx$. (When $|\ket\psi|=1$, we say it is normalised.)

For a simple illustration, we often use a single dimensional space so we can replace the vector $\mathbf r$ with the scalar $x$ and the integral would become $\int_{-\infty}^\infty$​.

Visually, a wave function is a continuous complex number field in all of space and time constrained by the Schrödinger equation. In particular, the Hamiltonian operator $\hat H$ acting on a wave function $\psi$ would produce another continuous complex field $\hat H\psi$, which if happens to be a direct scaling of $\psi$ with a real factor, i.e., $\hat H\psi=E\psi$, the real-valued scale factor $E$​ is the energy of the quantum system.

The scale factor $E$ is a "precise" measurement of the quantum system, which is not always possible experimentally. See Superposition below.

### Energy eigenbasis

In this context, $\psi$ is said to be an **eigenstate** of $\hat H$ with a corresponding **eigenvalue** $E$. While each eigenstate corresponds to only one eigenvalue (required by $\hat H\psi=E\psi$), the same eigenvalue may have multiple linear-independent eigenstates, a situation called degeneracy. The eigenstates sharing the same eigenvalue are called **degenerate eigenstates**. The vector space spanned by all such degenerate eigenstates is called the **eigenspace** of the eigenvalue. The dimension of the eigenspace is called the **degree of degeneracy** of the eigenvalue.

It can be proven that all vectors in the eigenspace are eigenstates as well, and you can choose multiple mutually orthogonal eigenstates in the eigenspace up to the degree of degeneracy. The non-degenerate eigenvalue has a one degree of degeneracy. The sum of degree of degeneracy of all eigenvalues equals to the dimension of $\mathcal H$. A basis of $\mathcal H$ can be constructed by selecting a set of mutually orthogonal eigenstates equal in number to the dimension of $\mathcal H$​. This type of basis is known as an **eigenbasis**.

Please note that position and momentum measurements observables generally do not degenerate as their spectra are continuous and each quantum state corresponds to only one position or momentum. Their Hilbert space has a dimension of infinity.

For the energy observable, the time evolution of a system can go through a continuous spectrum. For example, a photo may gain and lose energy continuously. However, at a fixed moment in time, a bounded quantum system can only have discrete levels of energy, possibly in superposition. That is why an atom can only emit and absorb photons of certain discrete energy levels in the continuous light spectrum.

Note: Although an eigenstate is a wave function, we cannot define an eigenstate without relating it to an observable $\hat A$. For example, $\delta(x-x_0)$ is an eigenstate of positional observable $\hat x$, and $e^{ikx}$ is one of momentum observable $\hat p$.

### Superposition

When the quantum system is bounded (with boundary conditions when solving the Schrödinger equation), energy eigenvalues $E$ are discrete. For example, in the one-dimensional "particle in a box" problem, the value of $\psi$ needs to be $0$ at both end. Another example is the orbitals, in which the cycle of electron waves around the nuclear needs to be a whole number.

When a quantum system is not in an eigenstate, it does not have an eigenvalue and therefore no energy level can be determined. However, the system's wave function $\psi$ can be expressed as a linear combination of eigenbasis vectors: $\psi=\sum_k c_k\psi_k$, where $\psi_k$ are eigenstates.

It follows that $\hat H\psi=\sum_k c_k\hat H\psi_k=\sum_k c_k E_k\psi_k$. We say that the quantum state is in a **superposition** of of $E_k$, each with an **amplitude** of $c_k$, assuming the eigenbasis is normalised. When we measure the energy of the system, the probability of obtaining $E_k$ (or the quantum state collapsing to $\psi_k$) is $|c_k|^2$.



## Amplitude

The complex number $\psi(x_0,t_0)$ represents the probability amplitude of position measurement at $x_0$ and $t_0$. Let us assume time-independency and simplify the complex number to to $\psi(x_0)$. Its corresponding eigenstate is $\delta(x-x_0)$, with amplitude of unit length.

However, $\psi(x_0)$ is *not* the amplitude of other non-positional observable. For example, for the momentum observable $\hat p=-i\hbar\frac{\partial}{\partial x}$, each eigenstate depends on the wave function in its entire domain. E.g., $\hat p (e^{ikx})=\hbar k(e^{ikx})$ has the eigenstate of $\hbar k$ based on wave function $e^{ikx}$ with $x\in(-\infty,\infty)$, not just at $x_0$.

In order to have the wave function peak at $x_0$, i.e., to have maximum *position* amplitude at $x_0$, you would need a multitude of $k$ in a linear combination, e.g., $\psi(x)=\sum_j c_j e^{ik_j(x-x_0)}$, which a common peak at $x=x_0$​. The more terms the sharper the peak, which is a simple illustration of the [uncertainty principle](https://en.wikipedia.org/wiki/Uncertainty_principle).

Relating this back to the concept of superposition:

- The momentum of $\psi(x)$ is in a superposition of eigenstate $e^{ik_j(x-x_0)}$ with an amplitude of $c_j$.
  - The continuous form is $\psi(x)=\int_{-\infty}^\infty c(y)e^{iy(x-x_0)}~dy$, where $c(y)$ is the amplitude of $e^{iy(x-x_0)}$.
- The position of $\psi(x)$ is in a superposition of eigenstate $\delta(x-x_j)$ with an amplitude of $\psi(x_j)$​.
  - The continuous form is $\psi(x)=\int_{-\infty}^\infty\psi(y)\delta(x-x_0)~dy$, where $\psi(y)$ is the amplitude of $\delta(x-x_0)$.



## Observables

WORKING

- Observables: operators to a wave function to obtain a physical quantity distribution
  - Position operator: $\hat x=x$, i.e., $\hat x\psi(x)=x\psi(x)$.
    - Analysis:
      - $\ket{x_0}$, the eigenstate of "precise" position $x_0$, is a function $\psi(x)$ satisfying $\hat x\psi(x)=x_0\psi(x)$ for any $x$, which means it has to be $\ket{x_0}=\delta(x-x_0)$.
      - The "precise" measurement of $x_0$ is $\hat x\delta(x-x_0)=x_0\delta(x-x_0)$​.
      - The wave function $\psi(x)=\int_{-\infty}^\infty\psi(y)\delta(x-y)dy$.
        - A theorem relating to the Dirac delta function
        - Represent a linear combination over a basis of an infinite dimension.
        - Each value of $x$ determine an integral, and the result of the integration over $y$ is the value of $\psi(x)$.
        - $\psi(x_0)$ is the amplitude of $x=x_0$.
    - Position is an eigenvalue of $\hat x\ket{x_0}=x_0\ket{x_0}$.
    - $|\ket{\psi_0}|^2$ is the probability of realising the measurement of the eigenvalue $x_0$.
    - Position is visualised as the "swell" of the wave function.
    - A positional quantum state is also called a wave function: $\psi(x,t)=\braket{x|\psi(t)}$.
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
      - When the system is gaining energy (through a combined net gain in momentum and potential change), its temporal frequency becomes faster.



## Measurements

Generally, if observable $\hat A$ has an eigenstate $\ket{k}$ with eigenvalue $\lambda_k$, there is a projector $\hat P_k=\ket k\bra k$ in the measurement operator. When $\psi=\ket k$, $\hat A\psi=\hat A\ket k=\lambda_k\ket k$ and the projection $(\lambda_k\hat P_k)\psi=\lambda_k\ket k\braket{k|k}=\lambda_k\ket k$, which is essentially a special $\hat A$ only on $\ket k$.

If we combine all projectors of all possible eigenvalues $\lambda_k$, we have $\hat P=\sum_k\lambda_k\hat P_k=\sum_k\lambda_k\ket k\bra k$, and for any eigenstate $\ket k$ we have $\hat P\ket k=\lambda_k\ket k$, so $\hat P$ essentially becomes $\hat A$. Therefore, $\boxed{\hat A=\sum_k\lambda_k\hat P_k}$.

In a superposition of $\psi=\sum_j a_j\ket j$, where $\ket j$ is an eigenstate of $\hat A$ and $a_j$ is its amplitude, $\braket{\psi|\hat P_k|\psi}=\left(\sum_i a_j^*\bra i\right)\left(\sum_k\ket k\bra k\right)\left(\sum_j a_j\ket j\right)=\sum_k a_k^*a_k=|a_k|^2$, which is the probability of measuring $\lambda_k$. Since $\hat A=\sum_k\lambda_k\hat P_k$, $\braket{\psi|\hat A|\psi}=\sum_k\braket{\psi|\lambda_k\hat P_k|\psi}=\sum_j|a_j|^2\lambda_j$​​​, which is the expectation value of the measurement.

While the observable operator $\hat A$ is a mathematical device (e.g., $\hat p=-i\hbar\frac{\partial}{\partial x}$) to describe the relationship between a quantum system and its corresponding physical quantities, the measurement operator $\hat P_k$ is a macroscopic apparatus which interacts (entangles) with the quantum system to form a composite system. The reading of the apparatus collapses the composite system and gives us the reading through its macroscopic indicator, a flash or a needle moving.

Experimentally, the apparatus does not have a full range. For example, a position measurement will not detect a particular area outside of the measuring box, although its amplitude is not zero outside of the box. In other words, not all $k$ in $\sum_k\lambda_k\hat P_k$ are configured or capable of the apparatus. Nonetheless, the measurement operator entangles with the quantum system in its full range, but eigenstates with no corresponding macroscopic indication do not give a reading on the apparatus.




---

LaTeX

$$
\newcommand{\Rsr}[1]{\frac{1}{\sqrt{#1}}}
\newcommand{\Tr}{\mathrm{Tr}}
$$
