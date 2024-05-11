# Angled vs Pauli

## Observables

$$
X\otimes Y\otimes Z
=\begin{bmatrix}0&1\\1&0\end{bmatrix}\begin{bmatrix}0&-i\\i&0\end{bmatrix}\begin{bmatrix}1&0\\0&-1\end{bmatrix}
=\begin{bmatrix}0&1\\1&0\end{bmatrix}\begin{bmatrix}0&0&-i&0\\0&0&0&i\\i&0&0&0\\0&-i&0&0\end{bmatrix}
=\begin{bmatrix}
0&0&0&0&0&0&-i&0\\
0&0&0&0&0&0&0&i\\
0&0&0&0&i&0&0&0\\
0&0&0&0&0&-i&0&0\\
0&0&-i&0&0&0&0&0\\
0&0&0&i&0&0&0&0&\\
i&0&0&0&0&0&0&0&\\
0&-i&0&0&0&0&0&0&\\
\end{bmatrix}
$$

## Angled gate phase gain

- Recall: When $\displaystyle A^2=I,~~e^{i\theta A}
  =I\cos\theta+iA\sin\theta$.
  - Analogous to $e^{i\theta a}=\cos\theta+ia\sin\theta$, where $a^2=1$.
- Put $I$ as the horizontal axis and $A$ vertical, $e^{i\theta A}$ goes anti-clockwise when $\theta:0\to 2\pi$.

| $\theta$ | $e^{i\theta A}$        | $I\cos\theta+iA\sin\theta$ |
| -------- | ---------------------- | -------------------------- |
| $0$      | $I$                    | $I$                        |
| $\pi/2$  | $e^{i\frac{\pi}{2}A}$  | $iA$                       |
| $\pi$    | $e^{i\pi A}$           | $-I$                       |
| $3\pi/2$ | $e^{i\frac{3\pi}{2}A}$ | $-iA$                      |
| $2\pi$   | $e^{i2\pi A}$          | $I$                        |



- Observe the following
  - $R_x(\theta)=e^{-i\frac{\theta}{2}X}=I\cos(\theta/2)-i\sin(\theta/2)X$.
  - $R_y(\theta)=e^{-i\frac{\theta}{2}Y}=I\cos(\theta/2)-i\sin(\theta/2)Y$.
  - $R_z(\theta)=e^{-i\frac{\theta}{2}Z}=I\cos(\theta/2)-i\sin(\theta/2)Z$.
- Each angled Pauli gate $R_p(\theta)$
  - goes through a circle (+ve anti-clockwise) around the Bloch sphere as $\theta:0\to 2\pi$, generating a phase.
    - i.e., $R_p(0)=I, R_p(2\pi)=-I$, where $p=x,y,z$.
  - goes through a cycle (-ve clockwise) around the $I-A$ plane as $\theta:0\to 4\pi$.
    - i.e., $R_p(0)=I,R_p(4\pi)=I$, where $p=x,y,z$.

---

Ref: http://qtol.jackyko.org/information_theories/Rotation%20about%20Pauli%20Axes.html

- $R_x(\theta)
  =e^{-i{\theta\over 2}X}
  =\begin{bmatrix}
  \cos{\theta\over 2} & -i\sin{\theta\over 2}\\
  -i\sin{\theta\over 2} & \cos{\theta\over 2}
  \end{bmatrix}
  .~~
  R_x(\pi)=-iX
  .$
- $R_y(\theta)
  =e^{-i{\theta\over 2}Y}
  =\begin{bmatrix}
  \cos{\theta\over 2} & -\sin{\theta\over 2}\\
  \sin{\theta\over 2} & \cos{\theta\over 2}
  \end{bmatrix}
  .~~
  R_y(\pi)=-iY
  .$
- $R_z(\theta)
  =e^{-i{\theta\over 2}Z}
  =\begin{bmatrix}
  e^{-i\theta/2} & 0\\
  0 & e^{i\theta/2}
  \end{bmatrix}
  .~~
  R_z(\pi)=-iZ
  .$

---


- Note: While an angled gate around a Pauli axis gains a phase at each $2\pi$ cycle and have a $4\pi$ cycle, the $\mathrm{PhaseShift}$ gate does not gain extra phase and its cycle is $2\pi$.

- The $R_x$ and $R_y$ phase gain across $\Ket1$ can be attributed to the $\Ket1$ "hole" in Bloch sphere:
  ![Bloch vs Hilbert](http://qtol.jackyko.org/information_theories/images/HilbertToBloch.png)

- $R_x(\theta)$:

  - A global phase is gained per $2\pi$ cycle starting from $\Ket0$:
    | $\theta$ | $R_x(\theta)$              | Phase |
    | -------- | -------------------------- | ----- |
    | $0$      | $\Ket0$                    | $1$   |
    | $\pi/2$  | $\Rsr2\Ket0-\Rsr2 i\Ket1$  | $1$   |
    | $\pi$    | $-i\Ket1$                  | $-i$  |
    | $3\pi/2$ | $-\Rsr2\Ket0-\Rsr2 i\Ket1$ | $-1$  |
    | $2\pi$   | $-\Ket0$                   | $-1$  |
    | $5\pi/2$ | $-\Rsr2\Ket0+\Rsr2 i\Ket1$ | $-1$  |
    | $3\pi$   | $i\Ket1$                   | $i$   |
    | $7\pi/2$ | $\Rsr2\Ket0+\Rsr2 i\Ket1$  | $1$   |
    | $4\pi$   | $\Ket0$                    | $1$   |

  - Gain a $-\pi/2$ phase on each side of $\Ket1$

    - Gain a $-i$ phase approaching $\Ket1$ from $\theta\to\pi^-$.
    - Gain another $-i$ phase approaching $\Ket1$ from $\theta\to\pi^+$.
    - Accumulative phase gain across $\Ket1$ is $-1=(-i)^2$.

- $R_y(\theta)$:

  - A global phase is gained per $2\pi$ cycle starting from $\Ket0$:
    | $\theta$ | $R_y(\theta)$            | Phase |
    | -------- | ------------------------ | ----- |
    | $0$      | $\Ket0$                  | $1$   |
    | $\pi/2$  | $\Rsr2\Ket0+\Rsr2\Ket1$  | $1$   |
    | $\pi$    | $\Ket1$                  | $1$   |
    | $3\pi/2$ | $-\Rsr2\Ket0+\Rsr2\Ket1$ | $-1$  |
    | $2\pi$   | $-\Ket0$                 | $-1$  |
    | $5\pi/2$ | $-\Rsr2\Ket0-\Rsr2\Ket1$ | $-1$  |
    | $3\pi$   | $-\Ket1$                 | $1$   |
    | $7\pi/2$ | $\Rsr2\Ket0-\Rsr2\Ket1$  | $1$   |
    | $4\pi$   | $\Ket0$                  | $1$   |

  - Gain a $-\pi/2$ phase when "exiting" $\Ket1$ (approching from $\theta\to\pi^+$)

- $R_z(\theta)$:

  - A global phase is gained per $2\pi$ cycle starting from $\Rsr2\Ket0+\Rsr2\Ket1$:
    | $\theta$ | $R_z(\theta)$                                                | Phase            |
    | -------- | ------------------------------------------------------------ | ---------------- |
    | $0$      | $\Rsr2\Ket0+\Rsr2\Ket1$                                      | $1$              |
    | $\pi/2$  | $(1/2-i/2)\Ket0+(1/2+i/2)\Ket1=\left(\Rsr2-\Rsr2 i\right)\left(\Rsr2\Ket0+\Rsr2 i\Ket1\right)$ | $\Rsr2-\Rsr2 i$  |
    | $\pi$    | $-i\Rsr2\Ket0+i\Rsr2\Ket1$                                   | $-i$             |
    | $3\pi/2$ | $(-1/2-i/2)\Ket0+(-1/2+i/2)\Ket1=\left(-\Rsr2-\Rsr2 i\right)\left(\Rsr2\Ket0-\Rsr2 i\Ket1\right)$ | $-\Rsr2-\Rsr2 i$ |
    | $2\pi$   | $-\Rsr2\Ket0-\Rsr2\Ket1$                                     | $-1$             |
    | $5\pi/2$ | $(-1/2+i/2)\Ket0+(-1/2-i/2)\Ket1=\left(-\Rsr2+\Rsr2 i\right)\left(\Rsr2\Ket0+\Rsr2 i\Ket1\right)$ | $-\Rsr2+\Rsr2 i$ |
    | $3\pi$   | $i\Rsr2\Ket0-i\Rsr2\Ket1$                                    | $i$              |
    | $7\pi/2$ | $(1/2+i/2)\Ket0+(1/2-i/2)\Ket1=\left(\Rsr2+\Rsr2 i\right)\left(\Rsr2\Ket0-\Rsr2 i\Ket1\right)$ | $\Rsr2+\Rsr2 i$  |
    | $4\pi$   | $\Rsr2\Ket0+\Rsr2\Ket1$                                      | $1$              |

  - Gains a $-\theta/2$ phase continuously.

    - $\mathrm{PhaseShift}$: $\begin{bmatrix}1&0\\0&e^{i\theta}\end{bmatrix}$.
    - $Z$-angled: $\begin{bmatrix}e^{-i\frac{\theta}{2}}&0\\0&e^{i\frac{\theta}{2}}\end{bmatrix}
      =e^{-i\frac{\theta}{2}}\begin{bmatrix}1&0\\0&e^{i\theta}\end{bmatrix}$.




## Double-qubit angled gates

- Recall: When $\displaystyle A^2=I,~~e^{i\theta A}
  =I\cos\theta+iA\sin\theta$.

### $X\otimes X$

- $X\otimes X=\begin{bmatrix}0&0&0&1\\0&0&1&0\\0&1&0&0\\1&0&0&0\end{bmatrix}$.
  - $R_{xx}(\theta)=e^{-i\frac{\theta}{2}X\otimes X}
    =\begin{bmatrix}
    \cos(\theta/2)&0&0&-i\sin(\theta/2)\\
    0&\cos(\theta/2)&-i\sin(\theta/2)&0\\
    0&-i\sin(\theta/2)&\cos(\theta/2)&0\\
    -i\sin(\theta/2)&0&0&\cos(\theta/2)
    \end{bmatrix}$.
- Eigenvalues and eigenvectors
  - $X:\Ket+,-\Ket-$
  - $X\otimes X:\Ket+\Ket+,-\Ket+\Ket-,-\Ket-\Ket+,\Ket-\Ket-$.
    - $++++~~~-+-+~~~--++~~~+--+$.



### $X\otimes Y$

- $X\otimes Y=\begin{bmatrix}0&0&0&-i\\0&0&i&0\\0&-i&0&0\\i&0&0&0\end{bmatrix}$.
  - $R_{xy}(\theta)=e^{-i\frac{\theta}{2}X\otimes Y}
    =\begin{bmatrix}
    \cos(\theta/2)&0&0&\sin(\theta/2)\\
    0&\cos(\theta/2)&-\sin(\theta/2)&0\\
    0&\sin(\theta/2)&\cos(\theta/2)&0\\
    -\sin(\theta/2)&0&0&\cos(\theta/2)
    \end{bmatrix}$.

### $Y\otimes Y$

- $Y\otimes Y=\begin{bmatrix}0&0&0&-1\\0&0&1&0\\0&1&0&0\\-1&0&0&0\end{bmatrix}$.
  - $R_{xx}(\theta)=e^{-i\frac{\theta}{2}Y\otimes Y}
    =\begin{bmatrix}
    \cos(\theta/2)&0&0&i\sin(\theta/2)\\
    0&\cos(\theta/2)&-i\sin(\theta/2)&0\\
    0&-i\sin(\theta/2)&\cos(\theta/2)&0\\
    i\sin(\theta/2)&0&0&\cos(\theta/2)
    \end{bmatrix}$.

### $Z\otimes Z$

- $Z\otimes Z=\begin{bmatrix}1&0&0&0\\0&-1&0&0\\0&0&-1&0\\0&0&0&1\end{bmatrix}$.
  - $R_{zz}(\theta)=e^{-i\frac{\theta}{2}Z\otimes Z}
    =\begin{bmatrix}
    \cos(\theta/2)-i\sin(\theta/2)&0&0&0\\
    0&\cos(\theta/2)+i\sin(\theta/2)&0&0\\
    0&0&\cos(\theta/2)+i\sin(\theta/2)&0\\
    0&0&0&\cos(\theta/2)-i\sin(\theta/2)
    \end{bmatrix}$
    $=\begin{bmatrix}
    e^{-i\theta/2}&0&0&0\\
    0&e^{i\theta/2}&0&0\\
    0&0&e^{i\theta/2}&0\\
    0&0&0&e^{-i\theta/2}
    \end{bmatrix}$.
  - Prove $C_x(I\otimes R_z(\theta))C_x=R_{zz}(\theta)$.
    - $\mathrm{LHS}=C_x\begin{bmatrix}e^{-i\theta/2}&0&0&0\\0&e^{i\theta/2}&0&0\\0&0&e^{-i\theta/2}&0\\0&0&0&e^{i\theta/2}\end{bmatrix}C_x
      =\begin{bmatrix}e^{-i\theta/2}&0&0&0\\0&e^{i\theta/2}&0&0\\0&0&e^{i\theta/2}&0\\0&0&0&e^{-i\theta/2}\end{bmatrix}$.

---

Ref: http://qtol.jackyko.org/information_theories/Rotation%20-%20Matrix%20Exponential.html

When $\displaystyle A^2=I,~~e^{i\theta A}
=I\cos\theta+iA\sin\theta,~~$ where $\theta\in\mathbb{R}.$

Proof: $\displaystyle e^{i\theta A}
=\sum_{k=0}^\infty{1\over (2k)!}(i\theta~A)^{2k}+\sum_{k=0}^\infty{1\over (2k+1)!}(i\theta~A)^{2k+1}\\
=I\sum_{k=0}^\infty{1\over (2k)!}(-1)^k\theta^{2k}+iA\sum_{k=0}^\infty{1\over (2k+1)!}(-1)^k\theta^{2k+1}
=I\cos\theta+iA\sin\theta
.$

From https://en.wikipedia.org/wiki/Quantum_logic_gate#Ising_coupling_gates

## Multiple qubits

From [Eigenstate of Multi-Qubits](http://qtol.jackyko.org/information_theories/Eigenstate%20of%20Multi-Qubits.html):

- For two n-dimensional unitary matrices $A$ and $B$, their eigenvector representation would be $A\psi_i=\alpha_i\psi_i$ and $B\phi_j=\beta_j\phi_j$.
- $(A\otimes B)\Ket{\psi_i\phi_j}
  =A\Ket{\psi_i}\otimes B\Ket{\phi_j}
  =\alpha_i\Ket{\psi_i}\otimes\beta_j\Ket{\phi_j}
  =\alpha_i\beta_j\Ket{\psi_i\phi_j}
  .$
- Therefore, the $n^2$ eigenvalues of $A\otimes B$ are $\alpha_i\beta_j$ where $i,j=1,2\ldots,n,$ and their corresponding eigenvectors are $\Ket{\psi_i\phi_j}$.

A simpler and more common expression:

- $(A\otimes B)\Ket\psi_A\Ket\phi_B
  =A\Ket\psi_A\otimes B\Ket\phi_B
  =\alpha_i\beta_j\Ket\psi_A\Ket\phi_B
  =\alpha_i\beta_j\Ket{\psi\phi}$.

## Rotation about an arbitrary axis

From [Rotation Bloch Sphere](http://qtol.jackyko.org/information_theories/Rotation%20-%20Bloch%20Sphere.html)

- Let us represent vector $\Ket\phi$ as $\mathbf r_\phi=(r_x,r_y,r_z)$, its three components on Bloch sphere.
- Let $\mathbf R(\alpha)=(R_x(\alpha),R_y(\alpha),R_z(\alpha))$.
- An arbitrary vector $\Ket\psi$ rotates about $\Ket\phi$ by $\alpha$ to $\Ket{\psi'}$.
- $\boxed{\Ket{\psi'}=\mathbf{r_\phi}\cdot\mathbf R(\alpha).}$
- Proof:
  - ...

## CNOT Symmetry

- $C_x$
  - $C_x\Ket{++}=\frac{1}{2}(\Ket{00}+\Ket{01}+\Ket{11}+\Ket{10})=\Ket{++}$
  - $C_x\Ket{+-}=\frac{1}{2}(\Ket{00}-\Ket{01}+\Ket{11}-\Ket{10})=\Ket{--}$
  - $C_x\Ket{-+}=\frac{1}{2}(\Ket{00}+\Ket{01}-\Ket{11}-\Ket{10})=\Ket{-+}$
  - $C_x\Ket{--}=\frac{1}{2}(\Ket{00}-\Ket{01}-\Ket{11}+\Ket{10})=\Ket{+-}$
  - $C_x$ on basis $\{\Ket+,\Ket-\}$ has the same effect as $CNOT$ on $\{\Ket0,\Ket1\}$ with qubit swap.

## Eigendecomposition

- For unitary $U$, let its eigenvalues be $\{\lambda_1,\lambda_2,\ldots,\lambda_n\}$ and normalised eigenvectors be $\{v_1,v_2,\ldots,v_n\}$, which are orthornomal.
  - We have $\displaystyle
    U=\sum_{k=1}^n\lambda_k\Ket{v_k}\Bra{v_k}.$ (eigendecomposition)
  - Proof:
    - Given $\Ket{v_k}$ are orthonormal, for an arbitrary vector $\Ket\psi$,
      $\left(\sum_{k=1}^n\Ket{v_k}\Bra{v_k}\right)\Ket\psi
      =\sum_{k=1}^n\psi_k\Ket{v_k}
      =\Ket\psi.~~
      \therefore
      \sum_{k=1}^n\Ket{v_k}\Bra{v_k}=I
      .$
    - Let $U\Ket{v_k}=\lambda_k\Ket{v_k},$ where $k\in[1,n].~
      U
      =U\sum_{k=1}^n\Ket{v_k}\Bra{v_k}
      =\sum_{k=1}^nU\Ket{v_k}\Bra{v_k}
      =\sum_{k=1}^n\lambda_k\Ket{v_k}\Bra{v_k}
      .$

- The following is in `1_Running_quantum_circuits_on_simulators` as well:
  - $X$ with eigenbasis $\{+,-\}$ and eigenvalues $\{1,-1\}$.
  - $Y$ with eigenbasis $\left\{\Rsr2(\Ket0+i\Ket1),\Rsr2(\Ket0-i\Ket1)\right\}$ and eigenvalues $\{1,-1\}$.
  - $Z$ with eigenbasis $\{\Ket0,\Ket1\}$ and eigenvalues $\{1,-1\}$.
  - $H$ with eigenbasis $\left\{\sqrt{1-\Rsr2}\Big(\Ket0+\Rsr2(\Ket0+\Ket1)\Big),\sqrt{1-\Rsr2}\Big(\Ket1-\Rsr2(\Ket0-\Ket1)\Big)\right\}$ and eigenvalues $\{1,-1\}$.

- The process of a unitary operation $U$ on $\Ket\psi$:
  - eigendecompose $\Ket\psi$, i.e., $\Ket\psi=\sum_k\Ket{v_k}\Braket{v_k|\psi}$
  - scale each component by its corresponding eigenvalue, i.e., $\lambda_k\Ket{v_k}\Braket{v_k|\psi}$
  - combine them to get the result: $U\Ket\psi=\sum_k\lambda_k\Ket{v_k}\Braket{v_k|\psi}$

- Examples with $\Ket\psi=a\Ket0+b\Ket1$:
  - Eigendecompose $X=\Ket1\Bra0+\Ket0\Bra1=\Ket+\Bra+-\Ket-\Bra-=\frac{1}{2}\begin{bmatrix}1&1\\1&1\end{bmatrix}-\frac{1}{2}\begin{bmatrix}1&-1\\-1&1\end{bmatrix}=\begin{bmatrix}0&1\\1&0\end{bmatrix}$
    - $\Ket+\Braket{+|\psi}=\Rsr2(a+b)\Ket+$ and $\Ket-\Braket{-|\psi}=\Rsr2(a-b)\Ket-$.
    - $X\Ket\psi=\Rsr2(a+b)\Ket+-\Rsr2(a-b)\Ket-=b\Ket0+a\Ket1.$
  - Eigendecompose $Z=\Ket0\Bra0-\Ket1\Bra1=\begin{bmatrix}1&0\\0&-1\end{bmatrix}$
    - $\Ket0\Braket{0|\psi}=a\Ket0$ and $\Ket1\Braket{1|\psi}=b\Ket1$.
    - $Z\Ket\psi=a\Ket0-b\Ket1.$

- $U$ as an observable

  - Measure the target state on $U$ so it collapses onto an eigenvector $\Ket{v_k}$ of $U$ with measurement $\lambda_k$.

  - Expectation value: $\Braket{\psi|U|\psi}=\left(\sum_k\psi_k^*\Bra{v_k}\right)\sum_k\lambda_k\psi_k\Ket{v_k}=\sum_k\lambda_k|\psi_k|^2$.
    - Sum of probability measurements of $\Ket\psi$ on each eigenbasis vector scaled by its corresponding eigenvalue.
  - Examples
    - EV of $\Ket+$ on observable $Z$ is $0$.
    - EV of Bell state $\Rsr2(\Ket{00}+\Ket{11})$ on $Z\otimes Z$ is $1$.
      - $Z^{\otimes2}=\Ket{00}-\Ket{01}-\Ket{10}+\Ket{11}$
      - $\Ket+$ has a probability measurement of  $\frac{1}{2}$ on $\Ket{00}$ and $\Ket{11}$, both eigenstates have an eigenvalue of $1$.
      - EV is therefore $\frac{1}{2}+\frac{1}{2}=1$
  - GHZ states EV
    - $0$ for GHZ states with odd qubits

    - $1$ for GHZ states with even qubits



## Recall

- $(\Ket\psi)^\dagger=\Bra\psi$
- For unitary $U$
  - Eigenvalues are norm one: $\lvert\lambda_i\rvert=1$.
  - If $U\Ket{\psi_1}=\lambda_1\Ket{\psi_1}$  and $U\Ket{\psi_2}=\lambda_2\Ket{\psi_2}$ ,
    - $\Braket{\psi_1|\psi_2}=\Braket{\psi_1|U^\dagger U|\psi_2}=\lambda_1^*\lambda_2\Braket{\psi_1|\psi_2}$,
    - requiring either $\lambda_1^*\lambda_2=1$ or $\Braket{\psi_1|\psi_2}=0$.
    - Note: $\Ket{\psi_1}$ and $\Ket{\psi_2}$ are not necessarily norm one.
  - If $\lambda_1=\lambda_2,\lvert\lambda_1\rvert=\lvert\lambda_2\rvert=1$.
- $H$ eigenvectors $\Ket0+\Ket+$ and $\Ket1-\Ket-$ normalisation
  - For $\Ket0+\Ket+=(1+\Rsr2)\Ket0+\Rsr2\Ket1$, norm is $\sqrt{(1+\Rsr2)^2+\frac{1}{2}}=\sqrt{2+\sqrt2}$.
    - Normalisation factor is $\frac{1}{\sqrt{2+\sqrt2}}=\frac{\sqrt{2-\sqrt2}}{\sqrt{2}}=\sqrt{1-\Rsr2}$.
    - So for $H$, eigenvector correspond to eigenvalue +1 is $\sqrt{1-\Rsr2}\Big(\Ket0+\Ket+\Big)$.
  - For $\Ket1-\Ket-=-\Rsr2\Ket0+(1+\Rsr2)\Ket1$, it has the same norm as above.
    - So for $H$, eigenvector correspond to eigenvalue -1 is $\sqrt{1-\Rsr2}\Big(\Ket1-\Ket-\Big)$.

## CNOT general effect

$R_x(\theta)=e^{i\theta/2~X},~M=C_x(R_x(\theta)\otimes I)=\begin{bmatrix}1&0&0&0\\0&1&0&0\\0&0&0&1\\0&0&1&0\end{bmatrix}\begin{bmatrix}\cos\theta/2&0&-i\sin\theta/2&0\\0&\cos\theta/2&0&-i\sin\theta/2\\-i\sin\theta/2&0&\cos\theta/2&0\\0&-i\sin\theta/2&0&\cos\theta/2\end{bmatrix}=\begin{bmatrix}\cos\theta/2&0&-i\sin\theta/2&0\\0&\cos\theta/2&0&-i\sin\theta/2\\0&-i\sin\theta/2&0&\cos\theta/2\\-i\sin\theta/2&0&\cos\theta/2&0\end{bmatrix}.$

$M\Ket{00}=\cos\theta/2\Ket{00}-i\sin\theta/2\Ket{11}.$

When $\theta=\pi/4, M\Ket{00}\approx 0.924\Ket{00}-0.383i\Ket{11},$ while $R_x(\pi/4)\Ket0=0.924\Ket0-0.383i\Ket1.$

## Expectation Value

- 1 qubit on $Z=\begin{bmatrix}1&0\\0&-1\end{bmatrix}$
  - $\Braket{0|Z|0}=1$
  - $\Braket{1|Z|1}=-1$
  - $EV=0$
- 2 qubits on $Z\otimes Z=\begin{bmatrix}1&0&0&0\\0&-1&0&0\\0&0&-1&0\\0&0&0&1\end{bmatrix}$
  - $\Braket{00|Z\otimes Z|00}=1$
  - $\Braket{01|Z\otimes Z|01}=-1$
  - $\Braket{10|Z\otimes Z|10}=-1$
  - $\Braket{11|Z\otimes Z|11}=1$
  - $EV=0$
- 1 qubit on $H=\Rsr2\begin{bmatrix}1&1\\1&-1\end{bmatrix}$
  - $\Braket{0|H|0}=\Rsr2$
  - $\Braket{1|H|1}=-\Rsr2$
  - $EV=0$
- 2 qubit2 on $H\otimes H=\frac{1}{2}\begin{bmatrix}1&1&1&1\\1&-1&1&-1\\1&1&-1&-1\\1&-1&-1&1\end{bmatrix}$
  - $\Braket{00|H\otimes H|00}=\frac{1}{2}$
  - $\Braket{01|H\otimes H|01}=-\frac{1}{2}$
  - $\Braket{10|H\otimes H|10}=-\frac{1}{2}$
  - $\Braket{1|H\otimes H|1}=\frac{1}{2}$
  - $EV=0$

## Multilinearity

$$
O_uu=u+u'\\
O_vv=v+v'\\
(O_u,O_v)\Ket{u,v}=\frac{1}{2}(\Ket{u,v}+\Ket{u',v}+\Ket{u,v'}+\Ket{u',v'})
$$

---

$$
X\Ket0=\Ket1=\Ket0+(-\Ket0+\Ket1),\quad u=\Ket0,~u'=-\Ket0+\Ket1\\
Y\Ket1=-i\Ket0=\Ket1+(-\Ket1-i\Ket0),\quad v=\Ket1,~v'=-\Ket1-i\Ket0\\
(X,Y)\Ket{01}=\Ket{01}+(-\Ket0+\Ket1)\Ket1+\Ket0(-\Ket1-i\Ket0)+(-\Ket0+\Ket1)(-\Ket1-i\Ket0)\\
=\Ket{01}-\Ket{01}+\Ket{11}-\Ket{01}-i\Ket{00}+\Ket{01}+i\Ket{00}-\Ket{11}-i\Ket{10}\\
=-i\Ket{10}
$$

---

$$
\mathrm{RHS}=\frac{1}{2}(\Ket{u,v}+\Ket{O_uu-u,v}+\Ket{u,O_vv-v}+\Ket{O_uu-u,O_vv-v})\\
=\frac{1}{2}(\Ket{u+O_uu-u+u+O_uu-u,v+v+O_v-v+O_vv-v})\\
=\Ket{O_uu,O_vv}
$$



## Bell's Theorem

Ref:

- https://www.on.kitp.ucsb.edu/online/qgravityt_c20/preskill/ (31:00)
- https://www.on.kitp.ucsb.edu/online/qgravityt_c20/preskill/oh/38.html

Donald prepares a pair of entangled qubits and send one to Alice and another to Bob.

Alice takes "head" as being $\Ket{e_x}$, and bob as $\Ket{e_y}$. The quantum state of the two joint qubits is: $\Ket\psi=\Rsr2(\Ket{e_x}\otimes \Ket{e_y}-\Ket{e_y}\otimes \Ket{e_x})=\Rsr2(\Ket{e_xe_y}-\Ket{e_ye_x})$.

Donald prepares two more pairs of entangled qubits, which has a $\pi/3$ phase shift from the first pair.

| Pair | ---- Alice Heads ---- | ---- Bob Heads ---- |
| ---- | ------------------------------------- | ------------------------------------- |
| 1    | $\Ket{e_x}$                                 | $\Ket{e_y}$                                 |
| 2    | $\frac{1}{2}\Ket{e_x}+\frac{\sqrt3}{2}\Ket{e_y}$  | $-\frac{\sqrt3}{2}\Ket{e_x}+\frac{1}{2}\Ket{e_y}$ |
| 3    | $-\frac{1}{2}\Ket{e_x}+\frac{\sqrt3}{2}\Ket{e_y}$ | $-\frac{\sqrt3}{2}\Ket{e_x}-\frac{1}{2}\Ket{e_y}$ |

Qubit state:

- $\Ket{\psi_1}=\Rsr2(\Ket{e_xe_y}-\Ket{e_ye_x})$
- $\Ket{\psi_2}=\Rsr2\left((\frac{1}{2}\Ket{e_x}+\frac{\sqrt3}{2}\Ket{e_y})(-\frac{\sqrt3}{2}\Ket{e_x}+\frac{1}{2}\Ket{e_y})-(-\frac{\sqrt3}{2}\Ket{e_x}+\frac{1}{2}\Ket{e_y})(\frac{1}{2}\Ket{e_x}+\frac{\sqrt3}{2}\Ket{e_y}\right)=\Rsr2(\Ket{e_xe_y}-\Ket{e_ye_x})$
- $\Ket{\psi_3}=\Rsr2\left((-\frac{1}{2}\Ket{e_x}+\frac{\sqrt3}{2}\Ket{e_y})(-\frac{\sqrt3}{2}\Ket{e_x}-\frac{1}{2}\Ket{e_y})-(-\frac{\sqrt3}{2}\Ket{e_x}-\frac{1}{2}\Ket{e_y})(-\frac{1}{2}\Ket{e_x}+\frac{\sqrt3}{2}\Ket{e_y}\right)=\Rsr2(\Ket{e_xe_y}-\Ket{e_ye_x})$

So, $\Ket{\psi_1}=\Ket{\psi_2}=\Ket{\psi_3}=\Ket{\psi}=\Rsr2(\Ket{e_xe_y}-\Ket{e_ye_x})$.

When they both measure the same pair.

| Pair | Measurement operator                                         | ---- Result ----                                             |
| ---- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 1    | $\Bra\phi=\Bra{e_xe_y}$                                      | $\Braket{\phi|\psi}=\Rsr2$                                   |
| 2    | $\Bra\phi=-\frac{\sqrt3}{4}\Bra{e_xe_x}+\frac{1}{4}\Bra{e_xe_y}-\frac{3}{4}\Bra{e_ye_x}+\frac{\sqrt3}{4}\Bra{e_ye_y}$ | $\Braket{\phi|\psi}=\frac{1}{4\sqrt2}+\frac{3}{4\sqrt2}=\Rsr2$ |
| 3    | $\Bra\phi=\frac{\sqrt3}{4}\Bra{e_xe_x}+\frac{1}{4}\Bra{e_xe_y}-\frac{3}{4}\Bra{e_ye_x}-\frac{\sqrt3}{4}\Bra{e_ye_y}$ | $\Braket{\phi|\psi}=\frac{1}{4\sqrt2}+\frac{3}{4\sqrt2}=\Rsr2$ |

When they measure different pairs for 00:

| Pair A, B | Measurement operator                                         | Result                     | Probability   |
| --------- | ------------------------------------------------------------ | -------------------------- | ------------- |
| 1, 2      | $\Bra\phi=-\frac{\sqrt3}{2}\Bra{e_xe_x}+\frac{1}{2}\Bra{e_xe_y}$ | $\Braket{\phi|\psi}=\Rsr8$ | $\frac{1}{8}$ |
| 2, 3      | $\Bra\phi=-\frac{\sqrt3}{4}\Bra{e_xe_x}-\frac{1}{4}\Bra{e_xe_y}-\frac{3}{4}\Bra{e_ye_x}-\frac{\sqrt3}{4}\Bra{e_ye_y}$ | $\Braket{\phi|\psi}=\Rsr8$ | $\frac{1}{8}$ |
| 3, 1      | $\Bra\phi=-\frac{1}{2}\Bra{e_xe_y}+\frac{\sqrt3}{2}\Bra{e_ye_y}$ | $\Braket{\phi\psi}=-\Rsr8$ | $\frac{1}{8}$ |

When they measure different pairs for 11:

| Pair A, B | Measurement operator                                         | Result                                | Probability   |
| --------- | ------------------------------------------------------------ | ------------------------------------- | ------------- |
| 1, 2      | $\Bra\phi=-\frac{1}{2}\Bra{e_ye_x}+\frac{\sqrt3}{2}\Bra{e_ye_y}$ | $\Braket{\phi|\psi}=\Rsr8$            | $\frac{1}{8}$ |
| 2, 3      | $\Bra\phi=\frac{\sqrt3}{4}\Bra{e_xe_x}+\frac{3}{4}\Bra{e_xe_y}+\frac{1}{4}\Bra{e_ye_x}+\frac{\sqrt3}{4}\Bra{e_ye_y}$ | $\Braket{\phi|\psi}=\frac{1}{\sqrt8}$ | $\frac{1}{8}$ |
| 3, 1      | $\Bra\phi=-\frac{\sqrt3}{2}\Bra{e_xe_x}+\frac{1}{2}\Bra{e_ye_x}$ | $\Braket{\phi\psi}=-\Rsr8$            | $\frac{1}{8}$ |

In each experiment, probability of either 00 or 11 occurs is $\frac{1}{4}$.


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
