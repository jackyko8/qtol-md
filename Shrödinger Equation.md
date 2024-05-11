# Shrödinger Equation

## TL;DR

- Typical wave function
  - $\psi(x,t)=e^{i(kx-\omega t)}$, where $k=\frac{2\pi}{\lambda}$ and $\omega=\frac{2\pi}{T}=2\pi f$.
    - When $x=\lambda,kx=2\pi$ and when $t=T,\omega t=2\pi$.
  - Sinusoidal wave:
    - $e^{ikx}$ centred at $(0,1)$ and symmetrical about $x=0$.
    - $e^{-i\omega t}$ traversing to the right (e.g., at $kx=\pi/2$ the wave goes up initially)
- Momentum
  - Momentum is negative gradient of wave function wrt to space: $\boxed{\mathbf p=-i\hbar\nabla}$
  - $\mathbf p\Ket\psi=-i\hbar\nabla\Ket\psi=\vec p\Ket\psi$, where measurement $\vec p$ is an eigenvalue of operator $\mathbf p$.
  - $\mathbf p\Ket\psi=-i\hbar\left(\frac{\partial}{\partial x},\frac{\partial}{\partial y},\frac{\partial}{\partial z}\right)\Ket\psi=-i\hbar\cdot ik\Ket\psi=p\Ket\psi$, where $k=\frac{2\pi}{\lambda}$.
  - $\displaystyle\boxed{p=\hbar k=\frac{h}{\lambda}}$ ... $p=\frac{h}{2\pi}\frac{2\pi}{\lambda}=\frac{h}{\lambda}$.
- Energy
  - Energy is gradient of wave function wrt to time: $\displaystyle\boxed{\mathbf E=i\hbar\frac{\partial}{\partial t}}$
  - $\mathbf E\Ket\psi=i\hbar\frac{\partial}{\partial t}\Ket\psi=E\Ket\psi$, where measurement $E$ is an eigenvalue of operator $\mathbf E$.
  - $\mathbf E\Ket\psi=i\hbar\cdot(-i\omega)\Ket\psi=E\Ket\psi$, where $\omega=2\pi f$.
  - $\boxed{E=\hbar\omega=hf}$ ... $E=\frac{h}{2\pi}\cdot 2\pi f=hf$.
- Simple harmonic motion (SHM)
  - $-\kappa y=m\ddot y$, where $\kappa$ is the spring constant and $y$ is the offset (i.e., distance from neutral)
  - Solution: $y=xe^{i\omega t}$, where $\omega=\sqrt{\kappa/m}$ , and $x$ is the amplitude
    - $\ddot y=(i\omega)^2y=-\kappa y/m$.
  - Potential energy: $E_v=\int_0^y-\kappa y~dy=-\kappa\frac{1}{2}y^2=-\frac{1}{2}m\omega^2x^2e^{2i\omega t}$.
    - Absolution value (maximum when $\omega t=\pi/2$): $E_v=\frac{1}{2}m\omega^2x^2$.
  - Kinetic energy: $E_k\psi=-\frac{\hbar^2}{2m}\frac{\partial^2}{\partial x^2}\psi$.
  - Let $r=x\sqrt{\frac{m\omega}{\hbar}}$, so $x=r\sqrt{\frac{\hbar}{m\omega}}$ and $\frac{\partial^2}{\partial x^2}=\frac{m\omega}{\hbar}\frac{\partial^2}{\partial r^2}$
    - $E_v=\frac{1}{2}\hbar\omega r^2$ and $E_k=-\frac{\hbar^2}{2m}\frac{m\omega}{\hbar}\frac{\partial^2}{\partial r^2}\psi=-\frac{1}{2}\hbar\omega\frac{\partial^2}{\partial r^2}\psi$.
  - $E=E_k+E_v=\frac{1}{2}\hbar\omega(-\nabla_r^2+\mathbf r^2)\psi$, where $\boxed{\mathbf r\equiv \sqrt{\frac{m\omega}{\hbar}}\mathbf x}$.
    - $\boxed{H=\frac{1}{2}\hbar\omega(-\nabla^2+\mathbf r^2)}$, where $\nabla\equiv\nabla_r$​.
    - ?Comparing with the Schrödinger equation: $\displaystyle H=i\hbar\frac{\partial}{\partial t}=-\frac{\hbar^2}{2m}\frac{\partial^2}{\partial x^2}+V$​
      - $\nabla_r^2=\frac{m\omega}{\hbar}\nabla_x^2$
      - $-\frac{1}{2}\hbar\omega\frac{m\omega}{\hbar}=-\frac{\hbar^2}{2m}$
        - $m\omega=\hbar$.
      - $V=\frac{1}{2}\hbar\omega\frac{m\omega}{\hbar}\mathbf x^2=\frac{1}{2}\hbar\omega\mathbf x^2$​.
- Creation and annihilation
  - Ref: https://en.wikipedia.org/wiki/Creation_and_annihilation_operators
  - Let $\boxed{a\equiv\Rsr2(\nabla+\mathbf r)}$ and $\boxed{a^\dagger\equiv\Rsr2(-\nabla+\mathbf r)}$.
  - $\nabla\mathbf r\phi-\mathbf r\nabla\phi=\phi+\mathbf r\nabla\phi-\mathbf r\nabla\phi=\phi~\Rightarrow~\nabla\mathbf r-\mathbf r\nabla=1$.
  - $aa^\dagger=\frac{1}{2}\left(-\nabla^2+\nabla\mathbf r-\mathbf r\nabla+\mathbf r^2\right)=\frac{1}{2}\left(-\nabla^2+\mathbf r^2+1\right)$.
  - $a^\dagger a=\frac{1}{2}\left(-\nabla^2-\nabla\mathbf r+\mathbf r\nabla+\mathbf r^2\right)=\frac{1}{2}\left(-\nabla^2+\mathbf r^2-1\right)$.
  - $\frac{H}{\hbar\omega}=\frac{1}{2}(-\nabla^2+r^2)=aa^\dagger-\frac{1}{2}=a^\dagger a+\frac{1}{2}$.
  - $Ha=\frac{1}{2}\hbar\omega(-\nabla^2+\mathbf r^2)a=\hbar\omega(aa^\dagger a-a/2)=a\hbar\omega\left(\frac{H}{\hbar\omega}-1\right)=Ea-\hbar\omega a$.
    - $\boxed{Ha=(E-\hbar\omega)a}$ ... annihilation
  - $Ha^\dagger=\frac{1}{2}\hbar\omega(-\nabla^2+\mathbf r^2)a^\dagger=\hbar\omega(a^\dagger aa^\dagger+a^\dagger/2)=a^\dagger\hbar\omega\left(\frac{H}{\hbar\omega}+1\right)=Ea^\dagger+\hbar\omega a^\dagger$.
    - $\boxed{Ha^\dagger=(E+\hbar\omega)a^\dagger}$ ... creation
- Ground energy
  - ??
    - Lowest energy when $xp=h/2$.
    - $p=\hbar k,xp=\hbar kx=h/2,kx=\pi$.
    - $\psi=e^{i(kx-\omega t)}$
    - $H=\frac{1}{2}\hbar\omega(-\nabla^2\psi+\mathbf r^2\psi)=\frac{1}{2}\hbar\omega(\frac{k^2\hbar}{m\omega}+\frac{m\omega}{\hbar}x^2)$

  - $\because E_0=\frac{1}{2}\hbar\omega,~\therefore\boxed{E_n=\hbar\omega\left(n+\frac{1}{2}\right)}$.
  - Since $H=\hbar\omega(a^\dagger a+\frac{1}{2})$, we define $\boxed{N\equiv a^\dagger a}$ ($N\psi=n\psi$) and have $H=\hbar\omega(N+\frac{1}{2})$.
  - Solving $N\psi=0$
    - $\frac{1}{2}\left(-\nabla^2+\mathbf r^2-1\right)\psi=0$.
    - $(-\nabla^2+\mathbf r^2)\psi=\psi$.
    -



## Derivations

Ref: https://www.youtube.com/playlist?list=PL54DF0652B30D99A4

- I1
  - Max Planck quantise energy: $\Delta E_n=nhf$​
    - $\boxed{E_n=(n+1/2)hf}$​
    - $nhf=\Delta E_n=E_n-E_0=(n+1/2)hf-E_0$
    - $E_0=\frac{1}{2}hf$
  - Einstein quantise light: $E_{photo}=\Delta E_{adj}=E_{n+1}-E_n=hf$
    - $\boxed{\Delta E=hf}$
  - Bohr quantised angular momentum: Neighbouring orbit jump $\Delta E=E_{final}-E_{initial}=hf$
    - $L=pr=\frac{h}{\lambda}r=hr\frac{n}{2\pi r}=n\frac{h}{2\pi}=n\hbar$
    - $\boxed{L=n\hbar}$
    - See I2 for $p=\frac{h}{\lambda}$
- I2
  - Einstein: $E^2=m^2c^4+p^2c^2$
  - For a photon, $m=0$ and therefore $E=pc$.
  - Because $E=hf,c=\lambda f,hf=pc=p\lambda f,$ we have $\boxed{p=\frac{h}{\lambda}}$
  - de Broglie: Same as matter, a wave with wavelength
  - Light: classical $x=ct$, quantum $\lambda=h/p$
- I3
  - Wave: $\psi(x,t)=A\sin[k(x-vt)]$
  - When $t=0$
    - $\psi(x)=A\sin(kx)$
    - When $x=\lambda,\psi(x)=0$, so $k\lambda=2\pi,\boxed{k=\frac{2\pi}{\lambda}}$
  - When $x=0$
    - $\psi(t)=A\sin(-kvt)$
    - When $t=T,\psi(t)=0$, so $kvT=2\pi,\boxed{kv=\omega}$
    - $\psi(x,t)=A\sin(kx-kvt)$
    - $\boxed{\psi(x,t)=A\sin(kx-\omega t)}$
  - $k$ and $\omega$
    - $k$ - wave number - the radian completed in 1 meter -  $2\pi$ in $\lambda$, hence $2\pi/\lambda$.
    - $\omega$ - angular velocity - the radian completed in 1 second - $2\pi$ in $T$, hence $2\pi/T$.
- I4
  - Fitting $n$ half-waves to length $\mathcal l=n\frac{\lambda}{2}$
  - Since $\boxed{\lambda=\frac{2\mathcal l}{n}},p=h/\lambda$, we have kinetic energy $E_k=\frac{p^2}{2m}=\frac{h^2}{2m\lambda^2}=\frac{h^2}{2m}\cdot\frac{n^2}{4\mathcal l^2}=\frac{n^2h^2}{8m\mathcal l^2}=\frac{n^2\pi^2\hbar^2}{2m\mathcal l^2}$
  - $\boxed{E_k=\frac{n^2\pi^2\hbar^2}{2m\mathcal l^2}}$
  - Standing wave is a combination of two opposite waves, e.g., left and right
    - $\psi(x,t)=\psi_R+\psi_L=\frac{A}{2}\sin(kx-\omega t)+\frac{A}{2}\sin(kx+\omega t)$
    - $\boxed{\psi(x,t)=A\sin(kx)\cos(\omega t)}$
    - Simplify by subtracting an imaginary term from $\psi(x,t)$
      - $\psi(x,t)=A\sin(kx)\cos(\omega t)-iA\sin(kx)\sin(\omega t)$
      - $\boxed{\psi(x,t)=A\sin(kx)e^{-i\omega t}}$
      - If $\psi$ is time-independent (still waving but the amplitude and spatial properties remain the same)
        - $\boxed{\psi(x,t)=\psi(x)e^{-i\omega t}}$
      - By convention, the wave propagate to the right, hence the minor sign
- I5
  - $k_n=\frac{2\pi}{\lambda_n},\lambda_n=\frac{2\mathcal l}{n},p_n=\frac{h}{\lambda_n},E_k=\frac{n^2\pi^2\hbar^2}{2m\mathcal l^2}$
  - $p=\frac{h}{\lambda}=h\frac{k}{2\pi}=\hbar k$ ... action over space - $\lambda\uparrow~\Rightarrow~k\downarrow~\Rightarrow~p\downarrow$
  - Total energy $E=hf=\frac{h}{2\pi}\cdot 2\pi f=\hbar\omega$ ... action over time - $T\uparrow~\Rightarrow~\omega\downarrow~\Rightarrow~E\downarrow$
  - Kinetic energy $E_k=\frac{p^2}{2m}=\frac{\hbar^2k^2}{2m}$
  - $E=E_k+V$
    - $\boxed{E=\hbar\omega=\frac{\hbar^2k^2}{2m}+V}$
  - $\displaystyle\frac{\partial^2\psi}{\partial x^2}=-k^2\psi$
    - $\displaystyle-\frac{\hbar^2}{2m}\frac{\partial^2\psi}{\partial x^2}=\frac{\hbar^2k^2}{2m}\psi=(\hbar\omega-V)\psi$
    - $\displaystyle\hbar\omega\psi=-\frac{\hbar^2}{2m}\frac{\partial^2\psi}{\partial x^2}+V\psi$
  - $\displaystyle\frac{\partial\psi}{\partial t}=-i\omega\psi$
    - $\displaystyle i\hbar\frac{\partial\psi}{\partial t}=\hbar\omega\psi$
  - $\boxed{\displaystyle i\hbar\frac{\partial\psi}{\partial t}=-\frac{\hbar^2}{2m}\frac{\partial^2\psi}{\partial x^2}+V\psi}$ Time-dependent Schrödinger Equation
  - When it is time-independent, the wave is a standing wave
    - $\displaystyle i\hbar\frac{\partial}{\partial t}\psi(x)e^{-i\omega t}=-\frac{\hbar^2}{2m}\frac{\partial^2}{\partial x^2}\psi(x)e^{-i\omega t}+V(x)\psi(x)e^{-i\omega t}$
    - $\displaystyle i\hbar(-i\omega)\psi(x)\cdot e^{-i\omega t}=-\frac{\hbar^2}{2m}\frac{\partial^2}{\partial x^2}\psi(x)\cdot e^{-i\omega t}+V(x)\psi(x)\cdot e^{-i\omega t}$
  - $\boxed{\displaystyle E\psi=-\frac{\hbar^2}{2m}\nabla^2\psi+V(x)\psi}$ Time-independent Schrödinger Equation
    - considering $\nabla^2=\left(\frac{\partial^2}{\partial x^2},\frac{\partial^2}{\partial y^2},\frac{\partial^2}{\partial z^2}\right)$
  - Define Hamiltonian $\displaystyle\boxed{H\equiv i\hbar\frac{\partial}{\partial t}=-\frac{\hbar^2}{2m}\nabla^2+V}$
  - The time-independent Schrödinger Equation becomes $\boxed{H\psi=E\psi}$.
  - $\boxed{E\to i\hbar\frac{\partial}{\partial t}}$ ... how fast the wave function move in time
  - $\boxed{\vec p\to -i\hbar\nabla}$ ... how steep the wave function dip in space
  - $\hbar$ has a unit of *action* (product of energy and time)
    - Energy is action over time
    - Momentum is action over space

## Standing wave

- Standing wave:
  - Combining two waves in opposite directions, starting from zero when $t=0$ (a phase shift of $i$):
    - $\phi_R=ie^{i(kx+\omega t)}$ ... starting from $0$ moving to the right
      - When $(x,t)=(0,0),\phi_R=i\cos(0)-\sin(0)=i$.
      - When $\omega t=\pi/2$,
        - $kx=0~\Rightarrow~i\cos(\pi/2)-\sin(\pi/2)=-1$.
        - $kx=\pi/2~\Rightarrow~i\cos(\pi)-\sin(\pi)=-i$.
        - $kx=\pi~\Rightarrow~i\cos(3\pi/2)-\sin(3\pi/2)=1$.

    - $\phi_L=ie^{i(-kx+\omega t)}$ ... starting from $0$ moving to the left
      - When $(x,t)=(0,0),\phi_L=i\cos(0)-\sin(0)=i$.
      - When $\omega t=\pi/2$,
        - $kx=0~\Rightarrow~i\cos(\pi/2)-\sin(\pi/2)=-1$.
        - $kx=\pi/2~\Rightarrow~i\cos(0)-\sin(0)=i$.
        - $kx=\pi~\Rightarrow~i\cos(-\pi/2)-\sin(-\pi/2)=1$.

    - $\phi=\frac{1}{2}\phi_R+\frac{1}{2}\phi_L=\frac{1}{2}ie^{i\omega t}(e^{ikx}+e^{-ikx})=i\cos(kx)e^{i\omega t}$.

  - Combining two waves in opposite directions, starting from peak when $t=0$:
    - $\phi_R=e^{i(kx-\omega t)}$ ... starting from peak moving to the right
      - When $(x,t)=(0,0),\phi_R=\cos(0)+i\sin(0)=i$.
      - When $\omega t=\pi/2$,
        - $kx=-\pi/2~\Rightarrow~\cos(-\pi)+i\sin(-\pi)=-1$.
        - $kx=0~\Rightarrow~\cos(-\pi/2)+i\sin(-\pi/2)=-i$.
        - $kx=\pi/2~\Rightarrow~\cos(0)+i\sin(0)=1$.
    - $\phi_L=e^{i(kx+\omega t)}$ ... starting from peak moving to the left
      - When $(x,t)=(0,0),\phi_L=\cos(0)+i\sin(0)=1$.
      - When $\omega t=\pi/2$,
        - $kx=-\pi/2~\Rightarrow~\cos(0)+i\sin(0)=1$.
        - $kx=0~\Rightarrow~\cos(\pi/2)+i\sin(\pi/2)=i$.
        - $kx=\pi/2~\Rightarrow~\cos(\pi)+i\sin(\pi)=-1$.
    - $\phi=\frac{1}{2}\phi_R+\frac{1}{2}\phi_L=\frac{1}{2}e^{ikx}(e^{-i\omega t}+e^{i\omega t})=\cos(\omega t)e^{ikx}$.
  - In both cases $\phi=i\cos(kx)e^{i\omega t}$ and $\phi=\cos(\omega t)e^{ikx}$:
    - First case:
      - $\mathbf p\Ket\phi=-i\hbar\nabla\Ket\phi=-i\hbar k\Ket\phi$.
      -
    - $\mathbf p^2\Ket\phi=-\hbar^2\nabla^2\Ket\phi=\hbar^2k^2\Ket\phi$.
    - ??
      - $\mathbf E\Ket\phi=i\hbar\frac{\partial}{\partial t}\Ket\phi=i\hbar(i\omega)\Ket\phi=-\hbar\omega\Ket\phi$
      - $=-i\hbar\omega\sin(\omega t)e^{ikx}$
      - $\mathbf E\Ket\phi=i\hbar\frac{\partial}{\partial t}i\cos(kx)e^{i\omega t}=-i\hbar \omega\cos(kx)e^{i\omega t}=-i\hbar\omega(\cos(kx)\cos(\omega t)+i\cos(kx)\sin(\omega t))$
      - $\mathbf E\Ket\phi=i\hbar\frac{\partial}{\partial t}\cos(\omega t)e^{ikx}=-i\hbar \omega\sin(\omega t)e^{ikx}=-i\hbar\omega(\cos(kx)\sin(\omega t)+i\sin(kx)\sin(\omega t))$
      -


---

LaTeX

$$
\require{cancel}
\newcommand{\Ket}[1]{\left|{#1}\right\rangle}
\newcommand{\Bra}[1]{\left\langle{#1}\right|}
\newcommand{\Braket}[1]{\left\langle{#1}\right\rangle}
\newcommand{\Rsr}[1]{\frac{1}{\sqrt{#1}}}
\newcommand{\RSR}[1]{1/\sqrt{#1}}
\newcommand{\Verti}{\rvert}
\newcommand{\HAT}[1]{\hat{\,#1~}}
\newcommand{\Tr}{\mathrm{Tr}}
$$
