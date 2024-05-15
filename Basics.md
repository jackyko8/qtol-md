# Basics of Quantum Mechanics

## Postulates

Ref: [Postulates](https://en.wikipedia.org/wiki/Mathematical_formulation_of_quantum_mechanics) (verbatim, almost)

1. The state of an isolated physical system is represented, at a fixed time $t$, by a state vector $\ket\psi$ belonging to a Hilbert space $\mathcal H$ called the *state space*.
2. The Hilbert space of a composite system is the Hilbert space [tensor product](https://en.wikipedia.org/wiki/Tensor_product) of the state spaces associated with the component systems. For a non-relativistic system consisting of a finite number of distinguishable particles, the component systems are the individual particles.
   1. Every measurable physical quantity $A$ is described by a Hermitian operator $A$ acting in the state space $\mathcal H$. This operator is an observable, meaning that its eigenvectors form a basis for $\mathcal H$. The result of measuring a physical quantity $A$ must be one of the eigenvalues of the corresponding observable $A$.
   2. When the physical quantity $A$ is measured on a system in a normalized state $\ket\psi$, the probability of obtaining an eigenvalue (denoted $a_n$ for discrete spectra and $\alpha$ for continuous spectra) of the corresponding observable $A$​ is given by the *amplitude squared* of the appropriate wave function (projection onto corresponding eigenvector).
      | Probability                                          | Spectrum                  |
      | ---------------------------------------------------- | ------------------------- |
      | $\mathbb P(a_n)=|\braket{a_n|\psi}|^2$               | Discrete, nondegenerate   |
      | $\mathbb P(a_n)=\sum_i^{g_n}|\braket{a_n^i|\psi}|^2$ | Discrete, degenerate      |
      | $d\mathbb P(\alpha)=|\braket{\alpha|\psi}|^2d\alpha$ | Continuous, nondegenerate |

   3. If the measurement of the physical quantity $A$ on the system in the state $\ket\psi$ gives the result $a_n$, then the state of the system immediately after the measurement is the normalized projection of $\ket\psi$ onto the eigensubspace associated with $a_n$​​
      $\displaystyle\ket\psi\xRightarrow{a_n}\frac{P_n\ket\psi}{\sqrt{\braket{\psi|P_n|\psi}}}$ , where $P_n=\sum_i^{g_n}\ket{a_{ni}}\bra{a_{ni}}$, where $g_n$ is the degree of degeneracy.
3. Time evolution

   1. The time evolution of the state vector $\ket{\psi(t)}$ is governed by the [Schrödinger equation](./Schrödinger Equation.md), where $H(t)$​ is the observable associated with the total energy of the system, the [Hamiltonian](./Hamiltonian.md).
      $\displaystyle i\hbar\frac{d}{dt}\ket{\psi(t)}=H(t)\ket{\psi(t)}$​.
   2. The time evolution of a [closed system](https://en.wikipedia.org/wiki/Closed_system#In_quantum_physics) is described by a [unitary transformation](https://en.wikipedia.org/wiki/Unitary_transformation_(quantum_mechanics)) on the initial state.
      $\ket{\psi(t)}=U(t;t_0)\ket{\psi(t_0)}$.

4. The wavefunction of a system of $N$​ identical particles (in 3D) is either totally symmetric (Bosons) or totally antisymmetric (Fermions) under interchange of any pair of particles.

### Illustration of the postulates

1. **State space**: A quantum state is a state vector $\ket\psi$ in Hilbert space $\mathcal H$.
2. **Composite system**: The state space of a composite system is the tensor product of individual state spaces. Each eigenvector in the composite system is a tensor product of eigenvectors in individual state spaces. The behaviour of composite systems exhibits as the entanglement phenomenon.
   1. **Observable**: The dimension of $\mathcal H$ equals to the number of measurable physical (real) quantities, each being an eigenvalue $\lambda_n$ of an normalised eigenvector $\ket{\psi_n}$ in the eigenbasis of $\mathcal H$.
   2. **Measurement probability**: Eigenvalues $\lambda_n$ are the only possible measurement outcomes. The probability of measuring $\lambda_n$ is the square of the (complex) amplitude of the normalised state vector $\ket\psi$ on eigenvector $\ket{\psi_n}$ (or sum of amplitudes in degeneracy) - the [Born Rule](https://en.wikipedia.org/wiki/Born_rule).
   3. **Measurement collapse**: The system state "collapses" to the eigenvector $\ket{\psi_n}$ right after the measurement that obtain $\lambda_n$. Further measurements will obtain $\lambda_n$ with certainty.
3. **Dynamics**: $\ket{\psi(t)}$ evolves following the Schrödinger equation, $\hat H(t)=i\hbar\frac{d}{dt}$ where the Hamiltonian $\hat H(t)$​ is the observable of the total energy of the system.

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

In this context, $\psi$ is said to be an **eigenvector** of $\hat H$ with a corresponding **eigenvalue** $E$. While each eigenvector corresponds to only one eigenvalue (required by $\hat H\psi=E\psi$), the same eigenvalue may have multiple linear-independent eigenvectors, a situation called degeneracy. The eigenvectors sharing the same eigenvalue are called **degenerate eigenvectors**. The vector space spanned by all such degenerate eigenvectors is called the **eigenspace** of the eigenvalue. The dimension of the eigenspace is called the **degree of degeneracy** of the eigenvalue.

It can be proven that all vectors in the eigenspace are eigenvectors as well, and you can choose multiple mutually orthogonal eigenvectors in the eigenspace up to the degree of degeneracy. The non-degenerate eigenvalue has a one degree of degeneracy. The sum of degree of degeneracy of all eigenvalues equals to the dimension of $\mathcal H$. A basis of $\mathcal H$ can be constructed by selecting a set of mutually orthogonal eigenvectors equal in number to the dimension of $\mathcal H$​. This type of basis is known as an **eigenbasis**.

Please note that position and momentum measurements observables generally do not degenerate as their spectra are continuous and each quantum state corresponds to only one position or momentum. Their Hilbert space has a dimension of infinity.

For the energy observable, the time evolution of a system can go through a continuous spectrum. For example, a photo may gain and lose energy continuously. However, at a fixed moment in time, a bounded quantum system can only have discrete levels of energy, possibly in superposition. That is why an atom can only emit and absorb photons of certain discrete energy levels in the continuous light spectrum.

Note: Although an eigenvector is a wave function, we cannot define an eigenvector without relating it to an observable $\hat A$. For example, $\delta(x-x_0)$ is an eigenvector of positional observable $\hat x$, and $e^{ikx}$ is one of momentum observable $\hat p$.

### Superposition

When the quantum system is bounded (with boundary conditions when solving the Schrödinger equation), energy eigenvalues $E$ are discrete. For example, in the one-dimensional "particle in a box" problem, the value of $\psi$ needs to be $0$ at both end. Another example is the orbitals, in which the cycle of electron waves around the nuclear needs to be a whole number.

When a quantum system is not in an eigenvector, it does not have an eigenvalue and therefore no energy level can be determined. However, the system's wave function $\psi$ can be expressed as a linear combination of eigenbasis vectors: $\psi=\sum_j c_j\psi_j$, where $\psi_j$ are eigenvectors.

It follows that $\hat H\psi=\sum_j c_j\hat H\psi_j=\sum_j c_j E_j\psi_j$. We say that the quantum state is in a **superposition** of of $E_j$, each with an **amplitude** of $c_j$, assuming the eigenbasis is normalised. When we measure the energy of the system, the probability of obtaining $E_j$ (or the quantum state collapsing to $\psi_j$) is $|c_j|^2$.



## Amplitude

The complex number $\psi(x_0,t_0)$ represents the probability amplitude of position measurement at $x_0$ and $t_0$. Let us assume time-independency and simplify the complex number to to $\psi(x_0)$. Its corresponding eigenvector is $\delta(x-x_0)$, with amplitude of unit length.

However, $\psi(x_0)$ is *not* the amplitude of other non-positional observable. For example, for the momentum observable $\hat p=-i\hbar\frac{\partial}{\partial x}$, each eigenvector depends on the wave function in its entire domain. E.g., $\hat p (e^{ikx})=\hbar k(e^{ikx})$ has the eigenvector of $\hbar k$ based on wave function $e^{ikx}$ with $x\in(-\infty,\infty)$, not just at $x_0$.

In order to have the wave function peak at $x_0$, i.e., to have maximum *position* amplitude at $x_0$, you would need a multitude of $k$ in a linear combination, e.g., $\psi(x)=\sum_r c_r e^{ik_r(x-x_0)}$, which a common peak at $x=x_0$. The more terms the sharper the peak, which is a simple illustration of the [uncertainty principle](https://en.wikipedia.org/wiki/Uncertainty_principle).

Relating this back to the concept of superposition:

- The momentum of $\psi(x)$ is in a superposition of eigenvector $e^{ik_r(x-x_0)}$ with an amplitude of $c_r$.
  - The continuous form is $\psi(x)=\int_{-\infty}^\infty c(y)e^{iy(x-x_0)}~dy$, where $c(y)$ is the amplitude of $e^{iy(x-x_0)}$.
- The position of $\psi(x)$ is in a superposition of eigenvector $\delta(x-x_r)$ with an amplitude of $\psi(x_r)$​.
  - The continuous form is $\psi(x)=\int_{-\infty}^\infty\psi(y)\delta(x-x_0)~dy$, where $\psi(y)$ is the amplitude of $\delta(x-x_0)$.



## Observables

This is a brief of some basic observables. Please refer to their individual articles for details of each observable describe.

An observable $\hat Q$ is an operator acting on a wave function to obtain a physical quantity distribution, with an expectation value $\braket{\psi|\hat Q|\psi}=\sum_j a_j^*a_j\lambda_j\ket{\psi_j}$, where $\ket{\psi}=\sum_j a_j\ket{\psi_j}$ and $\forall k,\hat Q\ket{\psi_j}=\lambda_j\ket{\psi_j}$​.

Each eigenvalue $\lambda_j$ is a real number representing the "precise" measurement of the physical quantity of $\hat Q$ corresponding to the eigenvector $\ket{\psi_j}$. The probability amplitude of $\ket\psi$ on $\ket{\psi_j}$ is $\braket{\psi_j|\psi}=a_j$.

### Position operator

The position operator is deceivingly simple: $\hat{\mathbf r}\ket\psi=\mathbf r\ket\psi$, or in one-dimension $\hat x\ket\psi=x\ket\psi$. Each position is a possible measurement, and any $x_0\in(-\infty,\infty)$ is an engenvalue of $\hat x$, with $\hat x\ket{x_0}=x\ket{x_0}=x_0\ket{x_0}$. The second equal sign means that the eigenvector $\ket{x_0}$ needs to be a function of $x$ which is $1$ at $x=x_0$ and zero everywhere else.

Although such function cannot be realised mathematically, we can approximate it using the Dirac delta function $\delta(x)=\left\{\begin{matrix}\infty,&x=0\\0,&x\ne 0\end{matrix}\right.$  and $\displaystyle\int_{-\infty}^\infty\delta(x-x_0)~dx=1$​.

Theorem: $\int_{-\infty}^\infty f(y)\delta(y-x)~dy=f(x)$. In other words, the integral is taking the value of $f$ at where $\delta$ integrates to $1$.

The eigenvector is therefore: $\ket{x_0}=\delta(x-x_0)$, and the amplitude of $\ket{\psi}$ on $\ket{x_0}$ is $\braket{x_0|\psi}=\int_{-\infty}^\infty\delta(x-x_0)\psi(x)~dx=\psi(x_0)$.



- Position operator: $\hat x=x$, i.e., $\hat x\psi(x)=x\psi(x)$.
  - Analysis:
    - $\ket{x_0}$, the eigenvector of "precise" position $x_0$, is a function $\psi(x)$ satisfying $\hat x\psi(x)=x_0\psi(x)$ for any $x$, which means it has to be $\ket{x_0}=\delta(x-x_0)$.
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

Generally, if observable $\hat A$ has an eigenvector $\ket{k}$ with eigenvalue $\lambda_j$, there is a projector $\hat P_j=\ket k\bra k$ in the measurement operator. When $\psi=\ket k$, $\hat A\psi=\hat A\ket k=\lambda_j\ket k$ and the projection $(\lambda_j\hat P_j)\psi=\lambda_j\ket k\braket{k|k}=\lambda_j\ket k$, which is essentially a special $\hat A$ only on $\ket k$.

If we combine all projectors of all possible eigenvalues $\lambda_j$, we have $\hat P=\sum_j\lambda_j\hat P_j=\sum_j\lambda_j\ket k\bra k$, and for any eigenvector $\ket k$ we have $\hat P\ket k=\lambda_j\ket k$, so $\hat P$ essentially becomes $\hat A$. Therefore, $\boxed{\hat A=\sum_j\lambda_j\hat P_j}$.

In a superposition of $\psi=\sum_r a_r\ket j$, where $\ket j$ is an eigenvector of $\hat A$ and $a_r$ is its amplitude, $\braket{\psi|\hat P_j|\psi}=\left(\sum_i a_r^*\bra i\right)\left(\sum_j\ket k\bra k\right)\left(\sum_r a_r\ket j\right)=\sum_j a_j^*a_j=|a_j|^2$, which is the probability of measuring $\lambda_j$. Since $\hat A=\sum_j\lambda_j\hat P_j$, $\braket{\psi|\hat A|\psi}=\sum_j\braket{\psi|\lambda_j\hat P_j|\psi}=\sum_r|a_r|^2\lambda_r$, which is the expectation value of the measurement.

While the observable operator $\hat A$ is a mathematical device (e.g., $\hat p=-i\hbar\frac{\partial}{\partial x}$) to describe the relationship between a quantum system and its corresponding physical quantities, the measurement operator $\hat P_j$ is a macroscopic apparatus which interacts (entangles) with the quantum system to form a composite system. The reading of the apparatus collapses the composite system and gives us the reading through its macroscopic indicator, a flash or a needle moving.

Experimentally, the apparatus does not have a full range. For example, a position measurement will not detect a particular area outside of the measuring box, although its amplitude is not zero outside of the box. In other words, not all $k$ in $\sum_j\lambda_j\hat P_j$ are configured or capable of the apparatus. Nonetheless, the measurement operator entangles with the quantum system in its full range, but eigenvectors with no corresponding macroscopic indication do not give a reading on the apparatus.




---

LaTeX

$$
\newcommand{\Rsr}[1]{\frac{1}{\sqrt{#1}}}
\newcommand{\Tr}{\mathrm{Tr}}
$$
