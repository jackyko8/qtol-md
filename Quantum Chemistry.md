# Quantum Chemistry

This is my grain-of-salt interpretation of quantum chemistry, in preparation of the VQE molecule energy calculation.

- Mathematics background

  - Ladder operators - raising or lowering operator to increase or decrease the eigenvalue of another operator
    - Eigenvalue: $N\ket n=n\ket n$.
    - Commutation relation: $[N,X]=cX$​.   i.e., $NX-XN=cX$​.
      - $NX\ket n=(XN+cX)\ket n=Xn\ket n+cX\ket n=(n+c)X\ket n$.
      - i.e., $X\ket n$ is an eigenstate of $N$ with eigenvalue $n+c$.
    - If $N$ is Hermitian, $c$ must be real. $[N,X^\dagger]=[N^\dagger,X^\dagger]=N^\dagger X^\dagger-X^\dagger N^\dagger=(XN-NX)^\dagger=-c^*X^\dagger=-cX^\dagger$.
      - $NX^\dagger\ket n=(X^\dagger N-cX^\dagger)\ket n=X^\dagger n\ket n-cX^\dagger\ket n=(n-c)X^\dagger\ket n$.
      - i.e., $X^\dagger\ket n$ is an eigenstate of $N$ with eigenvalue $n-c$.
  - [Hartree product](https://en.wikipedia.org/wiki/Hartree_equation)
    - $\Psi_h(\mathbf x_1,\ldots,\mathbf x_p)=\psi_\alpha(\mathbf x_1)\ldots\psi_\pi(\mathbf x_p)$.
    - Not anti-symmetric so not satisfying Pauli exclusion principle.
  - [Slate determinant](https://en.wikipedia.org/wiki/Slater_determinant)
    - $\Psi_s(\mathbf x_1,\ldots,\mathbf x_p)=\Rsr{p!}\left|
      \begin{matrix}
      \psi_\alpha(\mathbf x_1)&\psi_\beta(\mathbf x_1)&\ldots&\psi_\pi(\mathbf x_1)\\
      \psi_\alpha(\mathbf x_2)&\ddots&\ldots&\psi_\pi(\mathbf x_2)\\
      \vdots&\vdots&\ddots&\vdots\\
      \psi_\alpha(\mathbf x_p)&\psi_\beta(\mathbf x_p)&\ldots&\psi_\pi(\mathbf x_p)
      \end{matrix}\right|$.
    - Linear combination of Hartree products
    - Anti-symmetric and satisfying Pauli exclusion principle.
      - If by exchanging two electrons forms $\Psi_s'$ which is indistinguishable from $\Psi_s$, since $\Psi_s=-\Psi_s'$, the only solution is $\Psi_s=-\Psi_s'=0$.
      - If two electrons can occupy the same spin state, exchanging them would yield the same wavefunction, which is 0. So no two electrons can occupy the same spin sate - Pauli exclusion principle.
- Basics

  - Quantum energy
    - A quantum system is a wavefunction $\psi$ with an angular frequency $\omega$.
      - $\psi$ is a joint state of all the particles in the molecule, including electrons and nuclei.
      - The system is in a superposition of multiple wavefunctions and therefore multiple frequencies.
    - The system's energy is quantised: $\Delta E=h\nu=h\frac{\omega}{2\pi}=\hbar\omega$.
    - The ground state, minimum energy of the system, is $E_0=\frac{\hbar\omega}{2}=\frac{\Delta E}{2}$.
      - The fact that minimum energy is not zero is related to the [Heisenberg uncertainty principle](https://en.wikipedia.org/wiki/Heisenberg_uncertainty_principle).
    - The system with frequency $\nu=\frac{\omega}{2\pi}$ can only absorb a photon of $h\nu$ to raise its energy by $\Delta E=h\nu$ to the next energy level.
    - The Hamiltonian $H$ measures the energy and gives $\braket{\psi|H|\psi}$.
      - If $\psi$ is in a superposition, $\braket{\psi|H|\psi}$ measures the expectation value.
    - The ground state wavefunction $\psi_0$ will measure an energy $\braket{\psi_0|H|\psi_0}=\frac{\hbar\omega}{2}$.
    - $H$ can be derived from the molecular structure, the mass and position of all its constituents.
    - Creation operator $a^\dagger$ to raise the energy by one level, and annihilation operator $a$ to lower the energy by one level.
  - Molecule configuration
    - Multiple atoms indexed by $I$ and $J$.
    - Each atoms have $Z_I$ electrons.
    - All electrons of the molecule are indexed by $i$ and $j$.
  - Hamiltonian:

    - $\displaystyle H=\sum_i\frac{\mathbf p_i^2}{2m}+\sum_I\frac{\mathbf P_I^2}{2M_I}+\sum_iV_{nucl}(\mathbf r_i)+\frac{1}{2}\sum_{i\ne j}\frac{e^2}{|\mathbf r_i-\mathbf r_j|}+\frac{1}{2}\sum_{I\ne J}\frac{Z_IZ_Je^2}{|\mathbf R_I-\mathbf R_J|}$.
    - Given $\mathbf p=-i\hbar\nabla$, $V_{nucl}(\mathbf r)=-\sum_I\frac{Z_Ie^2}{|\mathbf r-\mathbf R_I|}$, if we take $\hbar=1$, $m=1$ and $e=1$, the Hamiltonian can be simplified to
      - $\displaystyle H=-\sum_i\frac{\nabla_i^2}{2}-\sum_I\frac{\nabla_I^2}{2M_I}-\sum_{i,I}\frac{Z_I}{|\mathbf r_i-\mathbf R_I|}+\frac{1}{2}\sum_{i\ne j}\frac{1}{|\mathbf r_i-\mathbf r_j|}+\frac{1}{2}\sum_{I\ne J}\frac{Z_IZ_J}{|\mathbf R_I-\mathbf R_J|}$.

        - The reciprocal distance terms is the Coulombic interaction.
    - Given nuclei are much heavier than electrons, we can "freeze" the nuclei at equilibrium in one position, so pure nuclei terms can be omitted ([Born-Oppenheimer](https://en.wikipedia.org/wiki/Born%E2%80%93Oppenheimer_approximation)), and the Hamiltonian can be further simplified to
      - $\displaystyle H=-\sum_i\frac{\nabla_i^2}{2}-\sum_{i,I}\frac{Z_I}{|\mathbf r_i-\mathbf R_I|}+\frac{1}{2}\sum_{i\ne j}\frac{1}{|\mathbf r_i-\mathbf r_j|}$.
- A set of single-electron basis functions is  $\{\phi_p(\mathbf x_i)\}$, where $\mathbf x_i=(\mathbf r_i,s_i)$, which denotes the position and spin of the electron.
    - Each $\phi_p(\mathbf x_i)$ is called an orbital.
  - The state of electron $i$ is a normalised linear combination of $\phi_p(\mathbf x_i)$ - the electron is in a superposition of orbitals.
  - The number of orbitals $M$ is typically larger than the number of electrons $N$.

  - Anti-symmetry: Exchanging two electrons will result in a negative sign, so two electrons with the same wave function will result in zero everywhere ([Pauli exclusion principle](https://en.wikipedia.org/wiki/Pauli_exclusion_principle)) - probability of multiple electrons with the same $\sum_p\phi_p(\mathbf x)$ is zero.

  - [Slate determinant](https://en.wikipedia.org/wiki/Slater_determinant) of two fermions (e.g., electrons): $\Psi(\mathbf x_1,\mathbf x_2)
    =\Rsr{2!}(\phi_1(\mathbf x_1)\phi_2(\mathbf x_2)-\phi_1(\mathbf x_2)\phi_2(\mathbf x_1))
    =\Rsr{2!}\left|\begin{matrix}\phi_1(\mathbf x_1)&\phi_2(\mathbf x_1)\\\phi_1(\mathbf x_2)&\phi_2(\mathbf x_2)\end{matrix}\right|$

    - Observe that the Slate determinant is a wave function, not a scalar: $\Rsr2\phi_1(\mathbf x_1)\phi_2(\mathbf x_2)-\Rsr2\phi_1(\mathbf x_2)\phi_2(\mathbf x_1)$.
    - It is a superposition of electron 1 and 2 occupying orbital 1 and 2 respectively, and the other way around with a *negative* phase.
    - $\Psi(\mathbf x_1,\mathbf x_2)=-\Psi(\mathbf x_2,\mathbf x_1)$. It is anti-symmetry and therefore follows Pauli exclusion principle, ?which means the two are distinguishable.
    - This can be extended to more than 2 fermions: $\Psi(\ldots,\mathbf x_{p_1},\ldots,\mathbf x_{p_2}\ldots)=-\Psi(\ldots,\mathbf x_{p_2},\ldots,\mathbf x_{p_1}\ldots)$.
    - If both $\Psi$ are equal after the exchange of $x_{p_1}$ and $x_{p_2}$ (i.e., with no minus sign), both sides must be zero, which validate Pauli exclusion principle.
    - Slate determinant represented in Fork space, by an occupation number vector $\ket f=\ket{f_{M-1},\ldots,f_0}$, where $f_i$ is 1 or 0 for occupied or not.
    - Not all fermionic wave functions can be written as a single Slater determinant.
- Fermion [creation and annihilation operators](https://en.wikipedia.org/wiki/Creation_and_annihilation_operators) $a_p^\dagger$ and $a_p$ on electron $p$

  - $\boxed{a=\Rsr2(\nabla+\mathbf r)}$ and $\boxed{a^\dagger=\Rsr2(-\nabla+\mathbf r)}$, satisfying the Schrödinger equation.
    - Note: $a^\dagger$ and $a$ are not unitary, so $a^\dagger a\ne I$.
    - $H=-\frac{\hbar^2}{2m}\frac{d^2}{dx^2}+\frac{1}{2}m\omega^2x^2$.
      - $\boxed{H\psi(x)=E\psi(x)}$.
      - Simplified if distance is measured in $\sqrt{\frac{\hbar}{m\omega}}$.
      - Let $\mathbf r$ be an operator: $\mathbf r\phi\equiv r\phi$, where $r=\sqrt{\frac{m\omega}{\hbar}}x$ is a scalar.
      - Let $\nabla\equiv\frac{d}{dr}$.
      - We remodulate $\psi$ on $r$ instead of $x$ (symbol abuse).
      - $H=\frac{\hbar\omega}{2}\left(-\nabla^2+\mathbf r^2\right)$.
      - $-\nabla^2+\mathbf r^2=(-\nabla+\mathbf r)(\nabla+\mathbf r)+(\nabla\cdot\mathbf r-\mathbf r\cdot\nabla)=(-\nabla+\mathbf r)(\nabla+\mathbf r)+I=2(a^\dagger a+\frac{1}{2})$.
        - To prove $\nabla\cdot\mathbf r-\mathbf r\cdot\nabla=I$, let us consider an arbitary function $\phi(r)$.
        - $(\nabla\cdot\mathbf r)\phi(r)
          =\nabla(r\phi(r))
          =(\nabla r)\phi(r)+r\nabla\phi(r)
          =(I+\mathbf r\cdot\nabla)\phi(r)$.
        - $(\nabla\cdot\mathbf r-\mathbf r\cdot\nabla)\phi(r)=I\phi(r)$.
    - $\boxed{H=\hbar\omega\left(a^\dagger a+\frac{1}{2}\right)}$.
      - $a^\dagger a=\frac{1}{2}(-\nabla+\mathbf r)(\nabla+\mathbf r)=\frac{1}{2}(-\nabla^2+\mathbf r^2-I)=\frac{H}{\hbar\omega}-\frac{1}{2}$.
      - $aa^\dagger=\frac{1}{2}(\nabla+\mathbf r)(-\nabla+\mathbf r)=\frac{1}{2}(-\nabla^2+\mathbf r^2+I)=\frac{H}{\hbar\omega}+\frac{1}{2}$.
      - $[a,a^\dagger]=aa^\dagger-a^\dagger a=1$.
      - $[a^\dagger,a]=a^\dagger a-aa^\dagger=-1$.
      - $[H,a]=Ha-aH=\hbar\omega(a^\dagger aa+\frac{a}{2}-aa^\dagger a-\frac{a}{2})=\hbar\omega[a^\dagger,a]a=-\hbar\omega a$.
        - $(-\hbar\omega a)\psi(r)=Ha\psi(r)-aH\psi(r)=H(a\psi(r))-aE\psi(r)$.
        - $\boxed{H(a\psi(r))=(E-\hbar\omega)(a\psi(r))}$.
      - $[H,a^\dagger]=Ha^\dagger-a^\dagger H=\hbar\omega(a^\dagger aa^\dagger+\frac{a^\dagger}{2}-a^\dagger a^\dagger a-\frac{a^\dagger}{2})=\hbar\omega a^\dagger[a,a^\dagger]=\hbar\omega a^\dagger$.
        - $(\hbar\omega a^\dagger)\psi(r)=Ha^\dagger\psi(r)-a^\dagger H\psi(r)=H(a^\dagger\psi(r))-a^\dagger E\psi(r)$.
        - $\boxed{H(a^\dagger\psi(r))=(E+\hbar\omega)(a^\dagger\psi(r))}$.
    - For eigenstate $\psi$, with $H\psi=E\psi$,
      - $a^\dagger\psi$ is an eigenstate with energe $E+\hbar\omega$.
        - The creator $a^\dagger$ increase the energe by $\hbar\omega$.
      - $a\psi$​ is an eigenstate with energe $E-\hbar\omega$​.
        - The annihilator $a$ decrease the energe by $\hbar\omega$.
- Eigenvalue

  - Eigenstate energy
    - Let the series of energy from low to high be $\{\psi_0,\psi_1,\ldots,\psi_n,\ldots\}$ with $\psi_0\ne 0$.
      - The argument $r$ is omitted from now on.
    - If $H\psi_n=E_n\psi_n$, based on the creator/annihilator equations, it is necessary that $E_n=E_0+n\hbar\omega$.
    - Energy is quantised with smallest packet being $\hbar\omega=h\nu$.
    - A boundary condition that energy is non-negative: $a\psi_0=0$.
      - $\because\Rsr2(\nabla+\mathbf r)\psi_0=0,\therefore\frac{d}{dx}\psi_0=-r\psi_0$.
      - A solution is $\psi_0=Ce^{-r^2/2}$.
      - Normalisation condition: $\int_{-\infty}^\infty\psi_0^*\psi_0~dr=1$ gives $C=\pi^{-1/4}$.
        - $C^2\int_{-\infty}^\infty e^{-r^2}dr=C^2\sqrt\pi=1$.
      - $\displaystyle\boxed{\psi_0=\frac{e^{-r^2/2}}{\sqrt[4]\pi}}$, which is a normal distribution centred at $r=0$ and vanishing at infinity.
  - Let $N\equiv a^\dagger a$
    - We have
      - $aa^\dagger=N+1$.
      - $H=\hbar\omega(N+\frac{1}{2})$.
      - $N=\frac{1}{2}(-\nabla^2+\mathbf r^2-I)$.
    - $N\psi_0
      =\frac{1}{2}(-\nabla^2+\mathbf r^2-I)\frac{e^{-r^2/2}}{\sqrt[4]\pi}
      =\frac{1}{2\sqrt[4]\pi}\left(-\nabla^2e^{-r^2/2}+(r^2-1)e^{-r^2/2}\right)
      =\frac{1}{2\sqrt[4]\pi}\left(-(r^2-1)e^{-r^2/2}+(r^2-1)e^{-r^2/2}\right)
      =0$.
    - $E_0\psi_0=H\psi_0=\hbar\omega(N+\frac{1}{2})\psi_0=\hbar\omega N\psi_0+\frac{\hbar\omega}{2}\psi_0=\frac{\hbar\omega}{2}\psi_0$.
    - $\boxed{E_0=\frac{\hbar\omega}{2}}$.
    - $\boxed{E_n=\hbar\omega\left(n+\frac{1}{2}\right)}$, as $E_n=E_0+n\hbar\omega$.
    - $H\psi_n=E_n\psi_n\Rightarrow\hbar\omega(N+\frac{1}{2})\psi_n=\hbar\omega(n+\frac{1}{2})\psi_n$.
    - $\boxed{N\psi_n=n\psi_n}$.
    - Note:
        - If energy is measured in $\hbar\omega$, we can write $H=\left(N+\frac{1}{2}\right)$ and $E_n=n+\frac{1}{2}$.
  - Time evolution $\boxed{U(t)=e^{-itH/\hbar}}=e^{-it\omega(N+1/2)}$.
    - Its eigenvalue is $e^{-itE_n/\hbar}=e^{-it(n+1/2)\omega}=e^{-i\omega_n t}$, where $\omega_n=(n+1/2)\omega$ and $\omega$ is the particle's phase angular velocity.
    - It is a wave with angular frequency $\omega_n$, frequency $\nu=\frac{\omega_n}{2\pi}$ and period $T_n=\frac{2\pi}{\omega_n}$.
    - At ground state, these numbers are $\omega_0=\omega/2$, $\nu_0=\frac{\omega}{4\pi}$ and $T_0=\frac{4\pi}{\omega}$.
    - $E_0=\frac{\hbar\omega}{2}=\frac{h\omega}{4\pi}=\frac{h\nu}{2}$ and $\Delta E=h\nu$.
- Eigenstate

    - Givens
      - $\displaystyle\psi_0=\frac{e^{-r^2/2}}{\sqrt[4]\pi}$.
      - $\nabla\psi_0=-r\psi_0$.
    - The physicist's [Hermite polynomials](https://en.wikipedia.org/wiki/Hermite_polynomials)
      - $H_n(r)=(-1)^ne^{r^2}\nabla^n e^{-r^2}$.
        - $\nabla H_n=(-1)^n(\nabla e^{r^2}\nabla^n e^{-r^2}+e^{r^2}\nabla^{n+1}e^{-r^2})=2r H_n-H_{n+1}$.
        - $\nabla H_n=2r H_n-H_{n+1}$.
        - $H_n$ is a polyomial, not an operator. Use $r$, not $\mathbf r$.
      - $H_{n+1}=2rH_n-\nabla H_n$.
      - $\{H_0,H_1,\ldots\}=\{1,2r,4r^2-2,8r^3-12r,16r^4-48r^2+12,\ldots\}$.
    - Define $\boxed{\psi_n=\frac{1}{\sqrt{2^n n!}}\cdot H_n\cdot\psi_0}$.
    - RTP: $\boxed{a^\dagger\psi_n=\sqrt{n+1}\cdot\psi_{n+1}}$, where  $n\ge0$.
      - When $n=0$, $a^\dagger\psi_0=\Rsr2(-\nabla\psi_0+r\psi_0)=\Rsr2(2r)\psi_0=\Rsr2H_1\psi_0=\psi_1$.
      - $a^\dagger\psi_n
        =\frac{1}{\sqrt2}(-\nabla+\mathbf r)\psi_n
        =\frac{1}{\sqrt2}(-\nabla+\mathbf r)\left(\frac{1}{\sqrt{2^n n!}}\cdot H_n\cdot\psi_0\right)$
      - $=\frac{1}{\sqrt{2^{n+1}n!}}(-\nabla H_n\cdot\psi_0-H_n\nabla\psi_0+\mathbf r H_n\psi_0)$
      - $=\frac{1}{\sqrt{2^{n+1}n!}}(-(2rH_n-H_{n+1})\psi_0+rH_n\psi_0+rH_n\psi_0)$
      - $=\frac{\sqrt{n+1}}{\sqrt{2^{n+1}(n+1)!}}H_{n+1}\psi_0=\sqrt{n+1}\cdot\psi_{n+1}$.
    - RTP: $\boxed{a\psi_n=\sqrt n\cdot\psi_{n-1}}$, where $n\ge 1$.
      - When $n=1$, $a\psi_1
        =a\left(\Rsr2\cdot 2r\psi_0\right)
        =(\nabla+\mathbf r)r\psi_0
        =\nabla r\cdot\psi_0+r\nabla\psi_0+r^2\psi_0
        =\psi_0-r^2\psi_0+r^2\psi_0
        =\psi_0$.
      - $a\psi_n=a\left(\Rsr{n}a^\dagger\psi_{n-1}\right)
        =\Rsr n(N+1)\psi_{n-1}=\Rsr n(n-1+1)\psi_{n-1}=\sqrt n\cdot\psi_{n-1}$​.
    - This general solution can be found at [Quantum harmonic oscillator](https://en.wikipedia.org/wiki/Quantum_harmonic_oscillator).
    - [Matrix representation](https://en.wikipedia.org/wiki/Creation_and_annihilation_operators#Matrix_representation) of $a^\dagger$ and $a$.
      - $\braket{\psi_p|\psi_q}=\int_{-\infty}^\infty\psi_p^*\psi_q~dr
        =\frac{1}{2^nn!}\int_{-\infty}^\infty H_pH_q\psi_0^*\psi_0~dr=\ldots$.
- Implementation

  - Recall the Hamiltonian: $\displaystyle H=-\sum_i\frac{\nabla_i^2}{2}-\sum_{i,I}\frac{Z_I}{|\mathbf r_i-\mathbf R_I|}+\frac{1}{2}\sum_{i\ne j}\frac{1}{|\mathbf r_i-\mathbf r_j|}$.
  - We convert it to: $H=\sum_{p,q}h_{pq}a_p^\dagger a_q+\frac{1}{2}\sum_{p,q,r,s}h_{pqrs}a_p^\dagger a_q^\dagger a_ra_s$.
    - $h_{pq}=\braket{\phi_p|-\frac{\nabla^2}{2}-\sum_I\frac{Z_I}{|r-R_I|}|\phi_q}$.
    - $h_{pqrs}=\braket{\phi_p\phi_q|\frac{1}{|r_1-r_2|}|\phi_s\phi_r}$.
  - [Hartree-Fock method](https://en.wikipedia.org/wiki/Hartree%E2%80%93Fock_method)
- Jordan-Wigner encoding

  - Let $q_i=\ket1$ represent orbital $i$ being occupied and $q_i=\ket0$ being not.
  -
- WORKING

  - For electron $p$, $a_p=\Rsr2(\nabla_p+\mathbf r_p)$ and $a_p^\dagger\Rsr2(-\nabla_p+\mathbf r_p)$.
  - $[H,a_p]=Ha_p-a_pH$
  - If $[H,a_p]=(E_{n+1}-E_n)a_p$, then $H(a_p\phi(\mathbf x))=(E_n+(E_{n+1}-E_n))a_p\phi(\mathbf x)=E_{n+1}(a_p\phi(\mathbf x))$.
    - $a_p\phi(\mathbf x)$ is the first excited state.
    - Also, $a_p^\dagger(a_p\phi(\mathbf x))=\phi(\mathbf x)$ will bring the excited state back to the ground state.
  - For electrons $p$ and $q$, exciting $p$ and exciting $q$ is distinguishable and therefore $\{a_p,a_q\}=\{a_p^\dagger,a_q^\dagger\}=\{a_p,a_q^\dagger\}=\{a_p^\dagger,a_q\}=0$ when $p\ne q$.
  - From the
    - $Ha_1\phi_1(\mathbf x)=(E_1+\Delta E)a_1\phi_1(\mathbf x)$.
    - If the next higher energy is orbital $\phi_2$, we have $H\phi_2(\mathbf x)=E_2\phi_2(\mathbf x)$.
    - By comparison, $a_1\phi_1(\mathbf x)=\phi_2(\mathbf x)$, and $a_1^\dagger\phi_2(\mathbf x)=\phi_1(\mathbf x)$.
  - ?? $\{a_1,a_1^\dagger\}=a_1a_1^\dagger+a_1^\dagger a_1=2I$.
  - ?? $\{a_1,a_2\}=a_1a_2+a_2a_1=0$ so $a_1a_2=-a_2a_1$.
- WORKING

  - Fermion annihilation and creation operators: $\{a_p,a_p^\dagger\}$, corresponding to $\{\phi_p(\mathbf x_i)\}$.

    - ??For Hamiltonian measurement $H$, if $H\phi_p(\mathbf x_i)=E_n\phi_p(\mathbf x_i)$, i.e., the energy eigenvalue of orbital eigenstate of electron $i$ is $E_n$,
      - $H(a_p\phi_p(\mathbf x_i))=E_{n+1}H(a_p\phi_p(\mathbf x_i))$.
      - $H(a_p^\dagger\phi_p(\mathbf x_i))=E_{n-1}H(a_p^\dagger\phi_p(\mathbf x_i))$.
    - ??-nah $\{a_p,a_q\}=a_pa_q+a_qa_p=(a_q^\dagger a_p^\dagger+a_p^\dagger a_q^\dagger)^\dagger=\{a_q^\dagger,a_p^\dagger\}^\dagger=\{a_p^\dagger,a_q^\dagger\}^\dagger$.
    -
- WORKING

  - ??Two electrons are represented by $a_p=\ket{a_{p_{M-1}},\ldots,a_{p_0}}$ and $a_q=\ket{a_{q_{M-1}},\ldots,a_{q_0}}$.
  - Fermion annihilation and creation operators: $\{a_p,a_p^\dagger\}$, corresponding to $\{\phi_p(\mathbf x_i)\}$.

    - $\{a_p,a_q\}=\{a_p^\dagger,a_q^\dagger\}=0$, and $\{a_p,a_q^\dagger\}=\delta_{pq}$.
    - Here $\{A,B\}$ is anticommutator equals to $AB+BA$.
  - The Hamiltonian $H=\sum_{p,q}h_{pq}a_p^\dagger a_q+\frac{1}{2}\sum_{p,q,r,s}h_{pqrs}a_p^\dagger a_q^\dagger a_r a_s$.

    - $\displaystyle h_{pq}=\int d\mathbf x~\phi_p^*(\mathbf x)\left(-\sum\frac{\nabla^2}{2}-\sum_I\frac{Z_I}{|\mathbf r-\mathbf R_I|}\right)\phi_q(\mathbf x)$.
    - $\displaystyle h_{pqrs}=\int d\mathbf x_1~d\mathbf x_2\frac{\phi_p^*(\mathbf x_1)\phi_q^*(\mathbf x_2)\phi_r(\mathbf x_1)\phi_s(\mathbf x_2)}{|\mathbf r_1-\mathbf r_2|}$.


---

LaTeX

$$
\newcommand{\Rsr}[1]{\frac{1}{\sqrt{#1}}}
\newcommand{\Tr}{\mathrm{Tr}}
$$

