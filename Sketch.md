# QC Sketch 2

- Bell state measurement

  - $\Ket\psi=\Rsr2(\Ket{01}-\Ket{10})$

    - $H\Ket1=\Rsr2(\Ket0-\Ket1)$
    - $Cx(0, 1)(H\Ket1\otimes\Ket1)=\Rsr2(\Ket{01}-\Ket{10})$

  - Measurement along $Z$

    - $Z\otimes Z\Ket\psi=\begin{bmatrix}1&0&0&0\\0&-1&0&0\\0&0&-1&0\\0&0&0&1\end{bmatrix}\Rsr2\begin{bmatrix}0\\1\\-1\\0\end{bmatrix}=\Rsr2\begin{bmatrix}0\\-1\\1\\0\end{bmatrix}.$
    - Expectation value: $\Bra\psi Z\otimes Z\Ket\psi=\frac{1}{2}[0~~1~-1~~0]\begin{bmatrix}0\\1\\-1\\0\end{bmatrix}=1.$

  - Measurement along $H$

    - $H\otimes H\Ket\psi=\frac{1}{2}\begin{bmatrix}1&1&1&1\\1&-1&1&-1\\1&1&-1&-1\\1&-1&-1&1\end{bmatrix}\Rsr2\begin{bmatrix}0\\1\\-1\\0\end{bmatrix}=\Rsr2\begin{bmatrix}0\\-1\\1\\0\end{bmatrix}$

    - Expectation value: $\Bra\psi H\otimes H\Ket\psi=\frac{1}{2}[0~~1~-1~~0]\begin{bmatrix}0\\1\\-1\\0\end{bmatrix}=1$

- Measurement basis
  - The computational basis is $\{\Ket0, \Ket1\}$, which is a projection $\Braket{0|\psi}$.
  - The "observable" is the Hamiltonian with eigenvectors being the measurement basis.
    - Let $\mathcal O$ be the observable and $\{\Ket{e_0}, \Ket{e_1}\}$ its measurement basis with eigenvalue $\lambda_0$ and $\lambda_1$ respectively.
    - Any $\Ket\psi$ to be measured can be decomposed into $\Ket\psi=c_0\Ket{e_0}+c_1\Ket{e_1}.$
    - $\mathcal O\Ket\psi=c_0\mathcal O\Ket{e_0}+c_1\mathcal O\Ket{e_1}=c_0\lambda_0\Ket{e_0}-c_1\lambda_1\Ket{e_1}.$
      - When $\lambda_0=1$ and $\lambda_1=-1$, $\mathcal O\Ket\psi$ is a flip over basis $\Ket{e_0}$.
    - $\Bra\psi=\alpha^*\Bra{e_0}+\beta^*\Bra{e_1}.$
    - $\Bra\psi\mathcal O\Ket\psi=\alpha^*\alpha-\beta^*\beta$
  - Other (non-$Z$) measurement basis, such as $\

## Observable

- To measure on $X$ is to transforming its eigenstates $\{\Ket+,\Ket-\}$ to $\{\Ket0,\Ket1\}$ respectively with $H$, then measure on $Z$.
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
  - $ECR\Ket{00}=\Rsr2(\Ket{0}-i\Ket{1})\Ket1$
  - $ECR\Ket{01}=\Rsr2(\Ket{0}+i\Ket{1})\Ket0$
  - $ECR\Ket{10}=\Rsr2(\Ket{0}-i\Ket{1})\Ket1$
  - $ECR\Ket{11}=\Rsr2(\Ket{0}+i\Ket{1})\Ket0$



## Transforming an arbitrary $U$ to $Z^\otimes$

??

Problem: Find $\mathcal M_U:U\mapsto Z^\otimes$

Example: $\mathcal M_X:X\mapsto Z$, then $\mathcal M_X=ZX$

## Basics

- Entanglement
  - Bell state: $\Ket\Psi=\Rsr2(\Ket{00}+\Ket{11})=\Rsr2\begin{bmatrix}1\\0\\0\\1\end{bmatrix}$.
  - $B=C_x(H\otimes I)=\Rsr2\begin{bmatrix}1&0&0&0\\0&1&0&0\\0&0&0&1\\0&0&1&0\end{bmatrix}\begin{bmatrix}1&0&1&0\\0&1&0&1\\1&0&-1&0\\0&1&0&-1\end{bmatrix}=\Rsr2\begin{bmatrix}1&0&1&0\\0&1&0&1\\0&1&0&-1\\1&0&-1&0\end{bmatrix}$.
    - The columns represent the four Bell states.
    - $B\Ket{00}=\Ket\Psi$.
  - $B^\dagger=\Rsr2\begin{bmatrix}1&0&0&1\\0&1&1&0\\1&0&0&-1\\0&1&-1&0\end{bmatrix}$.
    - $\Bra{00}B^\dagger=\Rsr2\begin{bmatrix}1&0&0&1\end{bmatrix}$
  - $\Ket\Psi\Bra\Psi=B\Ket{00}\Bra{00}B^\dagger=\frac{1}{2}\begin{bmatrix}1&0&0&1\\0&0&0&0\\0&0&0&0\\1&0&0&1\end{bmatrix}$.
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
