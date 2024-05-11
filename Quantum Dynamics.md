# Quantum Dynamics

## Schrödinger equation

https://en.wikipedia.org/wiki/Schr%C3%B6dinger_equation

### Basics

- Operators: https://youtu.be/LZie2QC5Jbc

  - Wave function $\Psi(x,t)$ is a complex number defined at all positions and all times.
  - Position operator: $\hat x\Psi=x\Psi$   or   $\hat{\mathbf r}\Psi=r\Psi$.
    - Sum of all amplitudes $\int_{-\infty}^\infty|\Psi(x)|^2dx=1$.
    - The absolute value accounts for "waving" (in a non-zero energy system) - both real and imaginary parts are included.
    - For a stationary system of a known position ("waving" or not), $|\Psi(x)|^2$ is the probability of measuring the position at $x$.

      - $\hat x$ is a Dirac delta operator that is equal to $x$ at position $x$ and zero everywhere else: $\delta_a(x)=\lim_{a\to 0}\frac{1}{|a|\sqrt\pi}e^{-(x/a)^2}$.
      - ?$x$ is the only eigenvalue of $\hat x$​, hence the only possible measurement.
    - For a system of superposition of positions, $\Psi$ is a (normalised) linear combination of Dirac delta functions of distinct $x$ (may have a different phase each).
      - Example: A balanced superposition of two positions, with a phase difference $\phi$: $\Psi(x)=\frac{1}{\sqrt{2}}\left[\delta(x-x_1)+e^{i\phi}\delta(x-x_2)\right]$​.

      - For a continuous probability distribution, $\Psi(x)=\psi(x)\delta(x)$, where $\psi(x)=|\Psi(x)|^2$, the probability of measuring $x$. For example, $\psi(x)=\mathcal N(x_0,\sigma^2)$, a normal distribution around $x_0$ with standard deviation of $\sigma$ (the spread around $x_0$).

    - ??Measurement: "entangle" an apparatus with an $\hat x$ basis in range $[x_1,x_2]$, which is a superposition (of infinite dimension) of $\delta(x)$.
      - ??If the position is outside of $[x_1,x_2]$, the measurement is nil.
  - Momentum operator: $\hat p\Psi=-i\hbar\frac{\partial}{\partial x}\Psi$.
    - For a system moving in space, the momentum is the spatial frequency of $\Psi$ - how fast it is changing in unit length - the wave number $k$ as in $e^{ikx}$.
    - The factor $-i$ turns the "side-way" change direction by $-\pi/2$ to align with $\Psi$ in order to make it an eigenvector.
    - For a system of superposition of momentums, $\Psi$ is a (normalised) linear combination of $e^{ikx}$ of distinct $k$.
    - ??Measurement: "entangle" an apparatus with a $\hat p$ basis in range $[p_1,p_2]$, which is a superposition of homogenous wave $e^{ikx}$.
      - ??If the momentum is outside of $[p_1,p_2]$, the measurement is nil.
  - Energy operator: $\hat E\Psi=i\hbar\frac{\partial}{\partial t}\Psi$.
    - For a constant non-zero energy system "waving" at a constant $\omega$ (at all positions), the energy is the time frequency of $\Psi$ - how fast it is changing in unit time - the angular frequency $\omega$ as in $e^{-i\omega t}$.
    - The factor $i$ turns the "side-way" change direction by $\pi/2$ to align with $\Psi$ in order to make it an eigenvector.
    - For a system of superposition of energies, $\Psi$ is a (normalised) linear combination of $e^{-i\omega t}$ of distinct $\omega$.
    - ??Measurement: "entangle" an apparatus with a $\hat E$ basis in range $[E_1,E_2]$, which is a superposition of homogenous wave $e^{-i\omega t}$.
      - ??If the momentum is outside of $[E_1,E_2]$, the measurement is nil.
  - Heisenberg uncertainty principle (a side note)
    - $\hat x\hat p\Psi=-i\hbar x\frac{\partial}{\partial x}\Psi$.
    - $\hat p\hat x\Psi=-i\hbar\frac{\partial}{\partial x}(x\Psi)=-i\hbar(\Psi+x\frac{\partial}{\partial x}\Psi)$.
    - $[\hat x\hat p,\hat p\hat x]\Psi=\hat x\hat p-\hat p\hat x=-i\hbar x\frac{\partial}{\partial x}\Psi+i\hbar\Psi+i\hbar x\frac{\partial}{\partial x}\Psi=i\hbar\Psi$.
    - $\sigma_x\sigma_p\ge\frac{1}{2}\left|[\hat x\hat p,\hat p\hat x]\right|=\hbar/2$.
      - [Robertson-Schrödinger uncertainty relation](https://www.nature.com/articles/srep36616)
      - $\sigma_x$ and $\sigma_p$ is the standard deviation of the $x$ and $p$ measurement.
    - $\boxed{\sigma_x\sigma_p\ge\hbar/2}$.
    - Same applies to energy and time: $\boxed{\sigma_E\sigma_t\ge\hbar/2}$.
  - $\Psi$ as a whole: $\Psi(x,t)=\psi(x,t)e^{i(kx-\omega t)}$​ contains all information of
    - $x$ in its amplitude $\psi(x,t)$,
    - $p$ in its spatial frequency $k$, and
    - $E$ in its time frequency $\omega$.
    - Two relationships to provide the behaviour of the system:
      - Normalisation: $\int_{-\infty}^\infty\psi(x,t)=1$ at all times $t$.
      - Schrödinger Equation (SE): $i\hbar\frac{\partial}{\partial t}\Psi(x,t)=-\frac{\hbar^2}{2m}\frac{\partial^2}{\partial{x^2}}\Psi(x,t)+V(x,t)\Psi(x,t)$.
- Schrödinger Equation: $\displaystyle\left[i\hbar\frac{\partial}{\partial t}\right]\Psi(x,t)=\left[-\frac{\hbar^2}{2m}\frac{\partial^2}{\partial{x^2}}+V(x,t)\right]\Psi(x,t)$.

  - Describe the behaviour of the system - how amplitude, spatial frequency and time frequency work together to form the system.
  - ??Visual examples:
    - In a flat potential region (constant $V$), when we inject energy into the system, the time frequency $\omega$ will increase, so the wave function is "waving" faster (LHS) and the wave length is shorter - larger $k=\frac{2\pi}{\lambda}$ and shorter $\lambda$.
    - When we know the energy $E$, the region of higher potential $V$ will see a lower kinetic energy $E_k$. The wave function will "turn" at a constant speed $\omega$ everywhere, the high $V$ region will have a low wave number $k$ and large wave length $\lambda=\frac{2\pi}{k}$.
- Energy

  - Kinetic Energy: $\displaystyle\hat{E_k}=\frac{\hat p^2}{2m}=-\frac{\hbar^2}{2m}\frac{\partial^2}{\partial x^2}$.
    - The eigenvalues of $\hat E_k$ is the spectrum of kinetic energy. $\hat E_k\Psi=E_k\Psi$.
  - Potential Energy: $\hat V(x,t)$.
    - The potential (for the particle species) at position at time.
  - Total Energy: $\displaystyle\hat E=i\hbar\frac{\partial}{\partial t}$.
    - The eigenvalues of $\hat E$ is the spectrum of total energy. $\hat E\Psi=E\Psi$.

  - SE is an energy equation
    - The $LHS$ is the total energy; the $RHS$ contains the kinetic energy and potential energy.
    - The dimension of the reduced Planck constant $\hbar$ is energy $\times$ time $\left(\left[\frac{\hbar^2}{2m}\cdot\frac{1}{x^2}\right]=\left[\frac{E^2T^2}{ET^2}\right]=[E]\right)$.
- In relation to the quantum mechanics basics
  - Planck-Einstein relation: $E=hf$, where time frequency $f=\frac{c}{\lambda}$ (for photon) and $h=2\pi\hbar$.
  - $\boxed{E=\hbar\omega}$, where $\omega=2\pi f$.
  - Kinetic energy $E=pv$. For a photon, $E=cp,~hf=p\lambda f,~p=\frac{h}{\lambda}$.

  - Illustration with SE:
    - $E_k=-\frac{\hbar^2}{2m}\frac{\partial^2}{\partial{x^2}}\Psi(x,t)$.
    - The phase factor of $\Psi$ (e.g., right propagating $e^{i(kx-\omega t)}$) gives a $i\hbar\cdot-i\omega$ factor and $LHS=\hbar\omega\Psi=E\Psi$.

### Example: Particle in a box

![Traveling wave package](https://upload.wikimedia.org/wikipedia/commons/8/8f/InfiniteSquareWellAnimation.gif)

- Prepare for differential equations
  - $\frac{d^2}{dx^2}f(x)=-k^2f(x)$, where $k\in\mathbb R$.
    - $f(x)=Ae^{i(kx+C)}$, where amplitude and phase $A,C\in\mathbb R$.
    - $\frac{d^2}{dx^2}f(x)=\frac{d^2}{dx^2}Ae^{i(kx+C)}=\frac{d}{dx}ikAe^{i(kx+C)}=-k^2Ae^{i(kx+C)}=-k^2f(x)$.
    - $f(x)=A(\cos(kx+C)+i\sin(kx+C))$.
    - $=A[(\cos(kx)\cos(C)-\sin(kx)\sin(C))+i(\sin(kx)\cos(C)+\cos(kx)\sin(C))]$
    - $\Re(f(x))=A_1\cos(kx)+A_2\sin(kx)$, with phase $C$ built into $A_1$ and $A_2$.
  - $\frac{d^2}{dx^2}f(x)=k^2f(x)$, where $k\in\mathbb R$.
    - $f(x)=Ae^{kx}$, where amplitude $A\in\mathbb R$.
    - $\frac{d^2}{dx^2}f(x)=\frac{d^2}{dx^2}Ae^{kx}=\frac{d}{dx}kAe^{kx}=k^2Ae^{kx}=k^2f(x)$.
  - Generally
    - DE: $\frac{d^2}{dx^2}f(x)=\alpha f(x)$, where $\alpha\in\mathbb Z$.
    - Solution: $f(x)=Ae^{x\sqrt\alpha}$, where $A\in\mathbb Z$.
- Set up:
  - The box is width is $L$ and $x=0$ at the left edge.
  - $\Psi(x,t)=0$ when $x=0,L$.
  - $V(x,t)=\left\{\begin{matrix}0&\ldots&x\in[0,L]\\\infty&\ldots&otherwise\end{matrix}\right.$.
- ??Solution
  - Consider only $x\in[0,L]$ where $V=0$.
  - $E=E_k+V=E_k$.
  - $E\psi=-\frac{\hbar^2}{2m}\frac{\partial^2}{\partial{x^2}}\psi$, where $\Psi=\psi e^{-i\omega t}$ and the phase factor cancels out on both sides.
  - $\frac{\partial^2}{\partial x^2}\psi=-\frac{2mE}{\hbar^2}\psi=-k^2\psi$,
    - where the wave number $k=\sqrt{\frac{2mE}{\hbar^2}}$.
    - Solution: $\psi=A_1\cos(kx)+A_2\sin(kx)$.
    - When $x=0,\psi=0$. So $A_1=0$.
    - When $x=L,\psi=0$. So $kL=n\pi$ and $\boxed{k_n=\frac{n\pi}{L}}$.
    - $\psi=A_2\sin(n\pi x/L).$
    - When $n=1,\int_0^L|\psi|^2dx=\int_0^LA_2^2\sin^2(\pi x/L)dx=A_2^2L/\pi\int_0^\pi \sin^2(y)dy=A_2^2L/\pi\cdot\pi/2=1$.
      - $A_2=\sqrt{2/L}$.
      - $\boxed{\psi_n=\sqrt{2/L}\sin(n\pi x/L)}$.
    - $E_n=\frac{\hbar^2k^2}{2m}$.
    - $\boxed{E_n=\hbar\omega_n=\frac{n^2\pi^2\hbar^2}{2mL^2}}$
    -

### Hamiltonian operator

- Motivation
  - To manipulating a quantum system by the way of a Hamiltonian operator
    - Applying certain "influence" over time to change the state of the system
    - The energy of the system may remain a constant

  - Define an observable, the *Hamiltonian* operator, $\hat H\equiv-\frac{\hbar^2}{2m}\frac{\partial^2}{\partial{x^2}}+V(x,t)$
  - $\displaystyle i\hbar\frac{\partial}{\partial t}\ket{\Psi(t)}=\hat H\ket{\Psi(t)}=E\ket{\Psi(t)}$.
    - $i\hbar\dot\psi=H\psi$ on Schrödinger's gravestone (the simplest form possible)

- Time-independent Hamiltonian
  - The Hamiltonian remains constant over time.
  - The observable $\hat H$ corresponds to energy, so its eigenvalues are energies observed (as a spectrum of probabilities).
    - A different Hamiltonian may measure a different spectrum with different probability distribution.

  - $\hat H\ket\Psi=E\ket\Psi$.
    - $E$ is energy (scalar).
  - ??The expectation value of $E$ is $\bra\Psi\hat H\ket\Psi$ or $\bra\Psi i\hbar\frac{\partial}{\partial t}\ket\Psi$.

- Unitary for time-independent $\hat H$
  - $\hat H$ is Hermitian, $\hat H^\dagger=\hat H$, not necessarily unitary but $e^{-i(t'-t)H}$ is. Let's see how.

  - Verify that $\ket{\Psi(t)}=e^{-i\mathbf{H}t}\ket{\Psi(0)}$ satisfies the Schrödinger equation, where $\mathbf{H}=\hat H/\hbar$.

    - For an infinitesimal time period $dt$,
    - $\ket{\Psi(t+dt)}
      =e^{-i\mathbf{H}(t+dt)}\ket{\Psi(0)}
      =e^{-i\mathbf{H}dt}e^{-i\mathbf{H}t}\ket{\Psi(0)}
      =e^{-i\mathbf{H}dt}\ket{\Psi(t)}$
    - $\ket{\Psi(t+dt)}-\ket{\Psi(t)}=(e^{-i\mathbf{H}dt}-1)\ket{\Psi(t)}=\frac{1}{e^{-i\mathbf Ht}}(e^{-i\mathbf{H}(t+dt)}-e^{-i\mathbf Ht})\ket{\Psi(t)}$,
    - $\frac{\ket{\Psi(t+dt)}-\ket{\Psi(t)}}{dt}=\frac{1}{e^{-i\mathbf Ht}}\frac{e^{-i\mathbf{H}(t+dt)}-e^{-i\mathbf{H}t}}{dt}\ket{\Psi(t)}$,
    - $\frac{\partial}{\partial t}\ket{\Psi(t)}=\frac{1}{e^{-i\mathbf Ht}}\left(\frac{\partial}{\partial t}e^{-i\mathbf Ht}\right)\ket{\Psi(t)}=-i\mathbf H\ket{\Psi(t)}=-\frac{i}{\hbar}\hat H\ket{\Psi(t)}$.
    - $\displaystyle i\hbar\frac{\partial}{\partial t}\ket{\Psi(t)}=\hat H\ket{\Psi(t)}~\ldots~$Q.E.D.

  - The infinitestimal interval $dt$ can be generalised to an arbitrary interval $\Delta t$.

    - $\ket{\Psi(t+\Delta t}=U\ket{\Psi(t)}$, where $U=U(\Delta t)=e^{-i\frac{\hat H}{\hbar}\Delta t}$ .
    - $\ket{\Psi(t+n\Delta t}=U^n\ket{\Psi(t)}=\left(e^{-i\frac{\hat H}{\hbar}\Delta t}\right)^n\ket{\Psi(t)}=e^{-i\frac{\hat H}{\hbar}n\Delta t}\ket{\Psi(t)}$ .

  - Time-independent evolution: $\boxed{\ket{\Psi(t')}=e^{-i\frac{\hat H}{\hbar}(t'-t)}\ket{\Psi(t)}}$.

  - Phase factor

    - For energy $E_n$ ($n^{th}$ eigenvalue of $\hat H$), $E_n=\hbar\omega_n$.
    - The phase factor is therefore $e^{-i\omega_n t}=e^{-iE_n t/\hbar}$.
- Unitary for time-dependent $\hat H$.

  - In the infinitestimal interval $dt$, $\hat H$ can be taken as a constant.
  - $U(t+dt,t)=e^{-i\frac{\hat H(t)}{\hbar}dt}$.
  - Time-dependent evolution: $\boxed{\ket{\Psi(t+dt)}=e^{-i\frac{\hat H(t)}{\hbar}dt}\ket{\Psi(t)}}$.

## Side nodes

### Schrödinger equation for engineers

- Ref
  - https://youtu.be/vsjGPRRhjlY
  - https://youtu.be/Q_rBTDwaNt0
- Quantum Well (QW)
  - Potential energy $V(x)=\left\{\begin{matrix}0&\ldots&x\in[-L/2,L/2]\\+\infty&\ldots&\mathrm{otherwise}\end{matrix}\right.$.
  - Equation: $\displaystyle\frac{\partial^2}{\partial x^2}\psi=-k^2\psi$.
  - Solution: $x=A\cos(kx)+B\sin(kx)$.
- What is $k$?
  - Given $\hat H\equiv-\frac{\hbar^2}{2m}\frac{\partial^2}{\partial{x^2}}+V(x,t)$ and $\hat H\ket\Psi=E\ket\Psi$,
  - $-\frac{\hbar^2}{2m}\frac{\partial^2}{\partial{x^2}}\psi+V\psi=E\psi$,
  - $\frac{\partial^2}{\partial{x^2}}\psi=-\frac{2m}{\hbar^2}(E-V)\psi$,
  - $\boxed{k=\sqrt{\frac{2m(E-V)}{\hbar^2}}}$,
  - $k$ is the wave number: spatial frequency - how many $2\pi$ per unit length.
  - $E$ is total energy and $V$ is potential energy.
  - So $k^2\psi=-\frac{\partial^2}{\partial x^2}\psi$ is related to kinetic energy - how steep the spatial down-hill slope is.

### Hamiltonian mechanics (as a comparison)

https://en.wikipedia.org/wiki/Hamiltonian_mechanics

- In Hamiltonian mechanics, $\mathcal H=\mathcal H(q,p,t)$ is called the Hamiltonian, which depends on position $q$, momentum $p$ and time $t$.
-  $\mathcal H=T+V$, where kinetic energy $T=\frac{p^2}{2m}$ and potential energy $V=V(q)$.
- Hamilton's equations:
  - Newtonian force is the negative gradient of potential energy: $\displaystyle\boxed{\frac{dp}{dt}=-\frac{\partial\mathcal H}{\partial q}}$.
  - Velocity is the derivative of kinetic energy wrt momentum: $\displaystyle\boxed{\frac{dq}{dt}=\frac{d\mathcal H}{dp}}$.
  - Illustration when $V=0$:
    - $\displaystyle\mathrm{RHS}=\frac{d}{dp}\frac{p^2}{2m}=\frac{p}{m}=v=\mathrm{LHS}$.

### Quantum Computing

http://www.theory.caltech.edu/~preskill/ph219/chap2_15.pdf

- Quantum state evolves from time $t$ to $t'$: $\ket{\psi(t')}=U(t',t)\ket{\psi(t)}$.
- Schrödinger equation: $\displaystyle i\hbar\frac{\partial}{\partial t}\ket{\psi(t)}=H(t)\ket{\psi(t)}$ at an instance of time.
  - $H$ is called the *Hamiltonian* of the system, with the dimension of energy (J).
  - Let $\hbar=1$, i.e. $\mathbf H=\frac{H}{\hbar}$.
  - $\frac{\ket{\psi(t+dt)}-\ket{\psi(t)}}{dt}=-i\mathbf H(t)\ket{\psi(t)}$
  - $\Rightarrow\ket{\psi(t+dt)}=\ket{\psi(t)}-i\mathbf H(t)dt\ket{\psi(t)}$
  - $\Rightarrow\ket{\psi(t+dt)}=(I-i\mathbf H(t)dt)\ket{\psi(t)}$.
  - Definition: $U(t+dt,t)\equiv I-i\mathbf H(t)dt$ in the infinitestimal time period $t\to t+dt$.
    - $H=H^\dagger$
    - $U^\dagger=I+i\mathbf H^\dagger(t)dt=I+i\mathbf H(t)dt$
    - $UU^\dagger=I+\mathbf H^2(t)d^2t\to I$ for a small $dt$.
- Time-independent evolution
  - $\mathbf H$ is independent of time
  - $\mathbf H$ is Hermitian.


---

LaTeX

$$
\newcommand{\Rsr}[1]{\frac{1}{\sqrt{#1}}}
\newcommand{\Tr}{\mathrm{Tr}}
$$

