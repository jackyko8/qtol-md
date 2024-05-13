# Measurements

## Basics

A measurement can be viewed as observing the **composite system** of the measurement apparatus and the quantum system being measured. The observation **collapses** the composite system into an eigenstate that can be observed macroscopically.

This view is consistent with the composite system postulate (observable, measurement probability and collapse). In other words, the apparatus **entangle** with the quantum system being measured, and the collapse gives the observation result.

The original state of the quantum system is essentially destroyed (or cannot be known) after the measurement. Further measurements on the same system will give the same result with certainty. This irreversibility is the foundation of the [uncertainty principle](https://en.wikipedia.org/wiki/Uncertainty_principle).

## Mathematical illustration

Mathematically, a measurement operator is in the form of $\hat P_{p_k}=\ket{p_k}\bra{p_k}$, where $\ket{p_k}$ is an eigenstate of the observable. That is $\hat p\ket{p_k}=p_k\ket{p_k}$, where $\hat p$ is the observable operator and $\ket{p_k}$ is in the state space of $\ket\psi$​.

For example, with a time-independent wave function $\psi(x)$, which is short for $\ket{\psi(x)}$, $\braket{\phi|\psi}\equiv\int_{-\infty}^\infty\phi(x)^*\psi(x)dx$. With the position operator $\hat x\psi(x)=x\psi(x)$, every $x_k\in(-\infty,\infty)$ is an eigenvalue. Its corresponding eigenstate is the delta function $\ket{x_k}=\delta(x-x_k)$.

In formal notation: $\hat x\ket{x_k}=x_k\ket{x_k}=x_k\delta(x-x_k)$. The projection of $\ket\psi$ on $\ket{x_k}$ is $\braket{x_k|\psi}=\int_{-\infty}^\infty\delta(x-x_k)\psi(x)dx=\psi(x_k)$, which represents the amplitude of $\psi$ at $x_k$.

The projector $\hat P_{x_k}\psi(x)=\ket{x_k}\braket{x_k|\psi}=\psi(x_k)\ket{x_k}$, with probability of $|\psi(x_k)|^2$ to obtain result $x_k$.

While $\ket{x_k}$ is an eigenstate of $\hat x$ with eigenvalue $x_k$, it is also an eigenvalue of $\hat P_{x_k}$ since $\hat P_{x_k}\ket{x_k}=\ket{x_k}\braket{x_k|x_k}=\ket{x_k}$ with an eigenvalue of $1$.





---

WORKING



For example, with the (continuous) positional observable $\hat x=x$, it is easy to see that any $x_k\in(-\infty,\infty)$ is an eigenvalue: $\hat x\ket{x_k}=x_k\ket{x_k}$. Therefore, $\hat X_k=\ket{x_k}\bra{x_k}$ and $\hat X_k\ket\psi=\ket{x_k}\braket{x_k|\psi}$ gives the $\ket{x_k}$ eigenstate with amplitude $\braket{x_k|\psi}$.

For example, $\ket{p_k}\braket{p_k|\psi}$ projects $\ket\psi$ onto $\ket{p_k}$. $\braket{p_k|\psi}$ is the amplitude and the probability of measuring $p_k$ is $|\braket{p_k|\psi}|^2$.

Experimentally, all eigenvalues of the measurement operator correspond to all possible measurement results: $P=\sum_k\ket{p_k}\bra{p_k}$ or $\int\ket p\bra p~dp$. All projection vectors are mutually orthogonal: $\braket{p_m|p_n}=\delta_{mn}$​​.

## Example: momentum measurement

The momentum measurement operator



Recalls that an observable $\hat A$ acting on the wave function transform it to another complex function $\hat A\ket{\psi(x,t)}$ with a spectrum of eigenvalues in the probability distribution of the amplitude squared of their corresponding eigenstates.

A composite system after the measurement becomes $P\hat A\ket{\psi(x,t)}=\sum_k\ket{p_k}\bra{p_k}\hat A\ket{\psi(x,t)}$. The observation collapses the system into a particular $k$, giving $\ket{p_k}$ with the probability of $\bra{p_k}\hat A\ket{\psi(x,t)}$.



## Example: position measurement

In this example, we use the position operator is $\hat x=x$ (corresponding to $\hat A$ above) and the Gaussian wave function $\psi(x)=\frac{1}{(\sqrt{2\pi}\sigma)^{1/2}}e^{-\frac{(x-x_c)^2}{4\sigma^2}}e^{ip_0x/\hbar}$, assuming time independency.

The whole wave function in domain $(-\infty,\infty)$ is the state vector, and is defined as $\ket\psi\equiv\int_{-\infty}^\infty\psi(x)dx$, and therefore $\bra{\psi}=\int_{-\infty}^\infty\psi(x)^*dx$.

Define $\braket{\phi|\psi}\equiv\int_{-\infty}^\infty\phi(x)^*\psi(x)dx$. We have $\braket{\psi|\psi}=\int_{-\infty}^\infty\psi(x)^*\psi(x)dx=1$. (Detailed proof is omitted here.)

The positional observable transform the wave function into a probability distribution of possible position measurements: $\hat x\psi(x)=x\psi(x)$. In vector form: $\hat x\ket\psi=\int_{-\infty}^\infty x\psi(x)dx$ and $\bra{x_k}\equiv\int_{-\infty}^\infty\delta(x-x_k)dx$.

The projection $\braket{x_k|\hat x\psi}=\int_{-\infty}^\infty\delta(x-x_k)x\psi(x)dx$. As $\delta(x-x_k)=0$ everywhere except for $x_k$, the projection becomes $x_k\left(\int_{-\infty}^\infty\delta(x-x_k)\psi(x)dx\right)=x_k\braket{x_k|\psi}$.

In other words, $\hat P_k\ket{\hat x\psi}=\ket{x_k}\braket{x_k|\hat x\psi}=\ket{x_k}\left(x_k\braket{x_k|\psi}\right)=x_k\hat P_k\ket\psi$.

$\hat P_k\ket{\hat x\psi}=x_k\ket{\hat x\psi}$



of the positional state $\hat x\ket\psi$ would be $\left(\ket{x_k}\bra{x_k}\right)\left(\hat x\ket{\psi}\right)=\ket{x_k}\braket{x_k|\hat x\psi}=\ket{x_k}\left(\int_{-\infty}^\infty\delta(x-x_k)x\psi(x)dx\right)$.

As $\delta(x-x_k)=0$ everywhere except for $x_k$, the projection becomes $\ket{x_k}x_k\left(\int_{-\infty}^\infty\delta(x-x_k)\psi(x)dx\right)=\ket{x_k}x_k\left(\int_{-\infty}^\infty\delta(x-x_k)\psi(x)dx\right)=\left(x_k\braket{x_k|\psi}\right)\ket{x_k}$​.



To simplify the illustration, we assume $\psi(x)$ $x_c=0$ and $p_0=0$, i.e., peak at $0$ and not moving. The phase factor is 1 and $\psi(x)$ becomes real: $\displaystyle\psi(x)=\frac{1}{(\sqrt{2\pi}\sigma)^{1/2}}e^{-\frac{x^2}{4\sigma^2}}$.





$\ket{\psi}=\psi(x), \bra{\psi}=\psi(x)^*=\psi(x)$​.

As illustrated before, if the measurement were discrete, the measurement operator would be like $P=\sum_k\ket{p_k}\bra{p_k}$ and the discrete wave function will be a linear combination of its eigenstates: $\ket\psi=\sum_k a_k\ket{\psi_k}$, where $a_k$ is the amplitude measuring $x_k$. As a result, $\hat x\ket\psi=\sum_k x_k a_k\ket{\psi_k}$, and $P\hat x\ket\psi=\sum_k x_k a_k\ket{p_k}\braket{p_k|\psi_k}$.

??If the measurement apparatus can measure position from $a$ to $b$ inclusively, the measurement operator is $\int_a^b\delta(x-p)\psi(p)~dp$.



---

In quantum mechanics, measurement is often described by projection operators or observables. For position, a measurement would involve projecting the wave function onto a specific position eigenstate. If we want to measure whether a particle is found at a specific position $x_0$, we use a Dirac delta function to represent that state:
$ \hat{P}_{x_0} = |x_0\rangle\langle x_0| $
where $|x_0\rangle$ is the position eigenstate at $x_0$.

When this projection operator acts on a general wave function, it yields the amplitude of the wave function at $x_0$:
$ \hat{P}_{x_0} \psi(x) = \delta(x - x_0) \psi(x_0) $

This operation gives the probability amplitude of finding the particle exactly at position $x_0$.

### Example with a Gaussian Wave Function:

Suppose we have a Gaussian wave function $\psi(x)$ centered at position $x_c$ with a standard deviation $\sigma$:
$ \psi(x) = \frac{1}{(\sqrt{2\pi} \sigma)^{1/2}} e^{-\frac{(x - x_c)^2}{4\sigma^2}} $

**Applying the Position Operator**:
The position operator $\hat{x}$ acts on the wave function as:
$ \hat{x} \psi(x) = x \cdot \frac{1}{(\sqrt{2\pi} \sigma)^{1/2}} e^{-\frac{(x - x_c)^2}{4\sigma^2}} $

**Position Measurement Operator**:
If we are interested in the probability of finding the particle at position $x_0$, we can apply the projection operator $\hat{P}_{x_0}$ to the wave function:
$ \hat{P}_{x_0} \psi(x) = \delta(x - x_0) \psi(x_0) = \delta(x - x_0) \cdot \frac{1}{(\sqrt{2\pi} \sigma)^{1/2}} e^{-\frac{(x_0 - x_c)^2}{4\sigma^2}} $

The result shows that the wave function collapses to position $x_0$, and the coefficient in front is the probability amplitude of finding the particle at that position.
