# Sketch

- Bell state measurement

  - $\ket\psi=\Rsr2(\ket{01}-\ket{10})$

    - $H\ket1=\Rsr2(\ket0-\ket1)$
    - $Cx(0, 1)(H\ket1\otimes\ket1)=\Rsr2(\ket{01}-\ket{10})$

  - Measurement along $Z$

    - $Z\otimes Z\ket\psi=\begin{bmatrix}1&0&0&0\\0&-1&0&0\\0&0&-1&0\\0&0&0&1\end{bmatrix}\Rsr2\begin{bmatrix}0\\1\\-1\\0\end{bmatrix}=\Rsr2\begin{bmatrix}0\\-1\\1\\0\end{bmatrix}.$
    - Expectation value: $\bra\psi Z\otimes Z\ket\psi=\frac{1}{2}[0~~1~-1~~0]\begin{bmatrix}0\\1\\-1\\0\end{bmatrix}=1.$

  - Measurement along $H$

    - $H\otimes H\ket\psi=\frac{1}{2}\begin{bmatrix}1&1&1&1\\1&-1&1&-1\\1&1&-1&-1\\1&-1&-1&1\end{bmatrix}\Rsr2\begin{bmatrix}0\\1\\-1\\0\end{bmatrix}=\Rsr2\begin{bmatrix}0\\-1\\1\\0\end{bmatrix}$

    - Expectation value: $\bra\psi H\otimes H\ket\psi=\frac{1}{2}[0~~1~-1~~0]\begin{bmatrix}0\\1\\-1\\0\end{bmatrix}=1$

- Measurement basis
  - The computational basis is $\{\ket0, \ket1\}$, which is a projection $\braket{0|\psi}$.
  - The "observable" is the Hamiltonian with eigenvectors being the measurement basis.
    - Let $\mathcal O$ be the observable and $\{\ket{e_0}, \ket{e_1}\}$ its measurement basis with eigenvalue $\lambda_0$ and $\lambda_1$ respectively.
    - Any $\ket\psi$ to be measured can be decomposed into $\ket\psi=c_0\ket{e_0}+c_1\ket{e_1}.$
    - $\mathcal O\ket\psi=c_0\mathcal O\ket{e_0}+c_1\mathcal O\ket{e_1}=c_0\lambda_0\ket{e_0}-c_1\lambda_1\ket{e_1}.$
      - When $\lambda_0=1$ and $\lambda_1=-1$, $\mathcal O\ket\psi$ is a flip over basis $\ket{e_0}$.
    - $\bra\psi=\alpha^*\bra{e_0}+\beta^*\bra{e_1}.$
    - $\bra\psi\mathcal O\ket\psi=\alpha^*\alpha-\beta^*\beta$
  - Other (non-$Z$) measurement basis, such as $\

## Observable

- To measure on $X$ is to transforming its eigenstates $\{\ket+,\ket-\}$ to $\{\ket0,\ket1\}$ respectively with $H$, then measure on $Z$.
- Generally, measuring on $\alpha$ is to transform its eigenstates to $Z$'s
  - $X$: $H=\Rsr2\begin{bmatrix}1&1\\1&-1\end{bmatrix}$
  - $Y$: $HS^\dagger=\Rsr2\begin{bmatrix}1&-i\\1&i\end{bmatrix}$
  - $Z$: $I=\begin{bmatrix}1&0\\0&1\end{bmatrix}$
  - $H$: $HTR_x(\pi/2)=H\begin{bmatrix}1&0\\0&e^{i\pi/4}\end{bmatrix}\Rsr2\begin{bmatrix}1&-i\\-i&1\end{bmatrix}=H\Rsr2\begin{bmatrix}1&-i\\e^{-i\pi/4}&e^{i\pi/4}\end{bmatrix}=\frac{1}{2}\begin{bmatrix}1+e^{-i\pi/4}&-i+e^{i\pi/4}\\1-e^{-i\pi/4}&-i-e^{i\pi/4}\end{bmatrix}$
  - $\Rsr2\begin{bmatrix}1&-i\\-i&1\end{bmatrix}\Rsr2\begin{bmatrix}1\\1\end{bmatrix}=\begin{bmatrix}1&-i\\-i&1\end{bmatrix}$

## ECR (OQC Lucy)

Echoed Cross-Resonance

- $ECR=\Rsr2\begin{bmatrix}0&1&0&i\\1&0&-i&0\\0&i&0&1\\-i&0&1&0\end{bmatrix}$
  - $ECR^2=I$
  - $ECR\ket{00}=\Rsr2(\ket{0}-i\ket{1})\ket1$
  - $ECR\ket{01}=\Rsr2(\ket{0}+i\ket{1})\ket0$
  - $ECR\ket{10}=\Rsr2(\ket{0}-i\ket{1})\ket1$
  - $ECR\ket{11}=\Rsr2(\ket{0}+i\ket{1})\ket0$



## Transforming an arbitrary $U$ to $Z^\otimes$

??

Problem: Find $\mathcal M_U:U\mapsto Z^\otimes$

Example: $\mathcal M_X:X\mapsto Z$, then $\mathcal M_X=ZX$

## Basics

- Entanglement
  - Bell state: $\ket\Psi=\Rsr2(\ket{00}+\ket{11})=\Rsr2\begin{bmatrix}1\\0\\0\\1\end{bmatrix}$.
  - $B=C_x(H\otimes I)=\Rsr2\begin{bmatrix}1&0&0&0\\0&1&0&0\\0&0&0&1\\0&0&1&0\end{bmatrix}\begin{bmatrix}1&0&1&0\\0&1&0&1\\1&0&-1&0\\0&1&0&-1\end{bmatrix}=\Rsr2\begin{bmatrix}1&0&1&0\\0&1&0&1\\0&1&0&-1\\1&0&-1&0\end{bmatrix}$.
    - The columns represent the four Bell states.
    - $B\ket{00}=\ket\Psi$.
  - $B^\dagger=\Rsr2\begin{bmatrix}1&0&0&1\\0&1&1&0\\1&0&0&-1\\0&1&-1&0\end{bmatrix}$.
    - $\bra{00}B^\dagger=\Rsr2\begin{bmatrix}1&0&0&1\end{bmatrix}$
  - $\ket\Psi\bra\Psi=B\ket{00}\bra{00}B^\dagger=\frac{1}{2}\begin{bmatrix}1&0&0&1\\0&0&0&0\\0&0&0&0\\1&0&0&1\end{bmatrix}$.
  - ?? $\Rsr2\begin{bmatrix}1&0&1&0\\0&1&0&1\\1&0&-1&0\\0&1&0&-1\end{bmatrix}\begin{bmatrix}1&0&0&0\\0&1&0&0\\0&0&0&1\\0&0&1&0\end{bmatrix}=\Rsr2\begin{bmatrix}1&0&0&1\\0&1&1&0\\1&0&0&-1\\0&1&-1&0\end{bmatrix}$.

## Inspiration

- https://aws.amazon.com/blogs/opensource/creating-a-bridge-between-machine-learning-and-quantum-computing-with-pennylane/
- QML is like ML in 80s
  - Critical factors to growth
  - Hardware advances - speed and error correction
    - Software advances - open source
    - Public accessibility and availability to the above
    - Cloud - Braket
      - Lower the entry barrier - abstraction and education
  - Leading to new ideas, algorithms etc
  - Motivation
    - Theoretical algorithms assuming infinite quantum volume
      - Proof
      - Vision for future
  - Practical approach on NISQ
      - Heuristic and practial
    - Useful - QML - PennyLane
      - Outcome now
- Approach
    - Using familiar ML techniques and frameworks (PyTorch, JAX, TensorFlow) for QML
  - Parallel circuit execution
  - Research
  - Research results -> software frameworks richness
    - New software features -> open up reearch avenues


---

LaTeX

$$
\newcommand{\Rsr}[1]{\frac{1}{\sqrt{#1}}}
\newcommand{\Tr}{\mathrm{Tr}}
$$
