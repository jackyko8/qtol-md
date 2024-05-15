# Heisenberg picture

The [Uncertainty principal](https://en.wikipedia.org/wiki/Uncertainty_principle) is an intriguing feature of quantum mechanics, due to that the position operator $\hat x$ and the momentum operator $\hat p$ do not commute. This means applying $\hat x$ then $\hat p$ to the wave function yields a different result from applying $\hat p$ then $\hat x$. In particular, $[\hat x, \hat p]=\hat x\hat p - \hat p\hat x=i\hbar$​.

## Poisson brackets

Ref: https://youtu.be/Nd4b0_vJZUk

#### Classical

The poisson bracket is defined as $\displaystyle\{Q_1, Q_2\}=\frac{\partial Q_1}{\partial x}\frac{\partial Q_2}{\partial p}-\frac{\partial Q_1}{\partial p}\frac{\partial Q_2}{\partial x}$, where $Q_1$ and $Q_2$ are functions of $x$ and $p$​.

We will have $\displaystyle\frac{dQ}{dt}=\{Q,H\}$.

> Proof:
>
> Take the time derivative of $Q$: $\frac{dQ}{dt}=\frac{\partial Q}{\partial x}\frac{dx}{dt}+\frac{\partial Q}{\partial p}\frac{dp}{dt}$​.
>
> Given classical Hamiltonian $H(x,t)=\frac{p^2}{2m}+U(x)$, so $\frac{\partial H}{\partial x}=\frac{dU}{dx}=-\frac{dp}{dt}$ and $\frac{\partial H}{\partial p}=\frac{p}{m}=\frac{dx}{d t}$​, we have $\displaystyle\frac{dQ}{dt}=\frac{\partial Q}{\partial x}\frac{\partial H}{\partial p}-\frac{\partial Q}{\partial p}\frac{\partial H}{\partial x}=\{Q,H\}$.

As a result, $\{x,H\}=\frac{dx}{dt}=v$ and $\{p,H\}=\frac{dp}{dt}=F$.

$\displaystyle\frac{dH}{dt}=\{H,H\}=0$, which is the Hamiltonian Noether Theorem related to symmetry and conservation laws.

$\displaystyle\{x,p\}=\frac{\partial x}{\partial x}\frac{\partial p}{\partial p}-\frac{\partial x}{\partial p}\frac{\partial p}{\partial x}=1$.

### ?Quantum

In Heisenberg picture, the time evolution operator $ \hat{U}(t) = e^{-i\hat{H}t/\hbar} $ represents the quantum system, which satisfies the Schrödinger equation for operators $i\hbar\frac{d}{dt}\hat U(t)=\hat H\hat U(t)$, analogous to $i\hbar\frac{d}{dt}\ket\psi=\hat H\ket\psi$.

Given an observable $\hat Q$, which is a fixed operator in Heisenberg picture, we define the Heisenberg operator as $\hat Q_H(t)=\hat U^\dagger(t)\hat Q\hat U(t)$, analogous to $\braket{\psi(t)|\hat Q|\psi(t)}$.

Considering the time derivative $\frac{d}{dt}\hat Q_H(t)=\frac{d}{dt}\left(\hat U^\dagger(t)\right)\hat Q\hat U(t)+\hat U^\dagger(t)\hat Q\frac{d}{dt}\left(\hat U(t)\right)$.





---

The commutator in quantum mechanics has a similar property to the poisson bracket in classical mechanics: $[\hat Q_1,\hat Q_2]=\hat Q_1\hat Q_2-\hat Q_2\hat Q_1$.

Schrödinger equation: $\displaystyle\hat H=i\hbar\frac{\partial}{\partial t}=-\frac{\hbar^2}{2m}\frac{\partial^2}{\partial x^2}+V(x,t)$.

It can be written as $\hat H=\frac{\hat p^2}{2m}+V$, where $\hat p=-i\hbar\frac{\partial}{\partial x}$.

