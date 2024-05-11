# Density Matrix

Ref: [Quantum Physics with Konstantin Lakic](https://youtu.be/kqnMgQzjLmQ) Playlist No. 105-107

## [Density Matrix for Pure Qubit States](https://youtu.be/kqnMgQzjLmQ)

- A pure state in general form: $\ket\psi=e^{i\omega}(\cos(\theta/2)\ket0+e^{i\phi}\sin(\theta/2)\ket1)=\alpha_0\ket0+\alpha_1\ket1=\begin{bmatrix}\alpha_0\\\alpha_1\end{bmatrix}$.
  - $\omega,\phi\in[0,2\pi)$.
  - $\alpha_0=e^{i\omega}\cos(\theta/2)=\braket{0|\psi}$.
  - $\alpha_1=e^{i\omega}e^{i\phi}\sin(\theta/2)=\braket{1|\psi}$.

- Dual vector: $\bra\psi=e^{-i\omega}(\cos(\theta/2)\bra0+e^{-i\phi}\sin(\theta/2)\bra1)=\alpha_0^*\bra0+\alpha_1^*\bra1=[\alpha_0^*~~\alpha_1^*]$.

- Density Matrix: $\rho=\ket\psi\bra\psi\
  =\begin{bmatrix}\alpha_0\\\alpha_1\end{bmatrix}[\alpha_0^*~~\alpha_1^*]\
  =\begin{bmatrix}\alpha_0\alpha_0^*&\alpha_0\alpha_1^*\\\alpha_1\alpha_0^*&\alpha_1\alpha_1^*\end{bmatrix}\
  =\begin{bmatrix}\cos^2(\theta/2)&e^{-i\phi}\cos(\theta/2)\sin(\theta/2)\\e^{i\phi}\sin(\theta/2)\cos(\theta/2)&\sin^2(\theta/2)\end{bmatrix}$.

- $\Tr\rho=|\alpha_0|^2+|\alpha_1|^2=\cos^2(\theta/2)+\sin^2(\theta/2)=1$.

  - Alternative views:

    - View 1: Einstein notation
      - $\rho^i_{~j}=\alpha_i\alpha^*_j$ .
      - $\Tr\rho=\rho^i_{~i}=\alpha_i\alpha^*_i=|\psi|^2=1$ for a pure state.

    - View 2: Braket notation
      - $\Tr\rho\
        =\braket{0|\psi}\braket{\psi|0}+\braket{1|\psi}\braket{\psi|1}\
        =\braket{\psi|0}\braket{0|\psi}+\braket{\psi|1}\braket{1|\psi}$
        $=\bra\psi(\ket0\bra0+\ket1\bra1)\ket\psi\
        =\braket{\psi|I|\psi}\
        =\braket{\psi|\psi}\
        =|\psi|^2$.

- Hermitian

  - $\rho^\dagger=(\ket\psi\bra\psi)^\dagger=\ket\psi\bra\psi=\rho$.

- Pureness test

  - Pure state

    - $\rho^2=\ket\psi\braket{\psi|\psi}\bra\psi=\ket\psi\bra\psi=\rho$.
    - Implying $\rho^n=\rho$.
    - Example:
      - $\ket\psi=\Rsr2(\ket0+\ket1)$.
      - $\rho=\ket\psi\bra\psi=\frac{1}{2}(I+X)$.
      - $\Tr\rho=1$.
    - Pauli pure states
      - $\rho_{x+}=\frac{1}{2}(\ket0\bra0+\ket0\bra1+\ket1\bra0+\ket1\bra1)=\frac{1}{2}(I+X)$.
      - $\rho_{x-}=\frac{1}{2}(\ket0\bra0-\ket0\bra1+\ket1\bra0-\ket1\bra1)=\frac{1}{2}(I-X)$.
      - $\rho_{y+}=\frac{1}{2}(\ket0\bra0-i\ket0\bra1+i\ket1\bra0+\ket1\bra1)=\frac{1}{2}(I+Y)$.
      - $\rho_{y-}=\frac{1}{2}(\ket0\bra0+i\ket0\bra1-i\ket1\bra0+\ket1\bra1)=\frac{1}{2}(I-Y)$.
      - $\rho_{z+}=\ket0\bra0=\frac{1}{2}(I+Z)$.
      - $\rho_{z-}=\ket1\bra1=\frac{1}{2}(I-Z)$.

  - Mixed state

    - $\rho'=\sum_i q_i\ket{\psi_i}\bra{\psi_i}$, where $\sum_i q_i=1$ and $\braket{\psi_i|\psi_j}=\delta_{ij}$ (eigen decomposition).

    - $\Tr\rho'\
      =\Tr\sum_i q_i\ket{\psi_i}\bra{\psi_i}\
      =\sum_i q_i\Tr\ket{\psi_i}\bra{\psi_i}\
      =\sum_i q_i\
      =1$.

    - $\rho'^2\
      =\sum_{i,j}q_iq_j\ket{\psi_i}\braket{\psi_i|\psi_j}\bra{\psi_j}$
      $=\sum_i q_i^2\ket{\psi_i}\braket{\psi_i|\psi_i}\bra{\psi_i}+\sum_{i\ne j}q_iq_j\ket{\psi_i}\braket{\psi_i|\psi_j}\bra{\psi_j}$.

    - $\Tr\rho'^2\le\Tr\rho^2=1$ and equal only applies if there is only one term in $\rho'$.

      - Note: $a_i\in[0,1),a_i^2\le a_i,\sum a_i^2\le \sum a_i$.

      - Note: If $\rho_n$ contains $n$ unique states, $\lim_{n\to\infty}\Tr\rho_n=0$ (maximum mixed state).
        - Assume equal probably of $n$ states, so $q=1/n$ and $\sum q^2=n/n^2=1/n$.

    - Example:

      - $\rho'=\frac{1}{2}\ket0\bra0+\frac{1}{2}\ket1\bra1$.

      - $\rho'^2\
        =\frac{1}{4}(\ket0\braket{0|0}\bra0+\ket0\braket{0|1}\bra1+\ket1\braket{1|0}\bra0+\ket1\braket{1|1}\bra1)$

        $=\frac{1}{4}(\ket0\bra0+\ket1\bra1)=\frac{1}{4}I$.

      - $\Tr\rho'^2=\frac{1}{2}$.



## [Density Matrix and Bloch Sphere Visualization](https://youtu.be/ZmU6vRFPHr8)

- Recall:
  $\rho=\ket\psi\bra\psi\
  =\begin{bmatrix}\alpha_0\\\alpha_1\end{bmatrix}[\alpha_0^*~~\alpha_1^*]\
  =\begin{bmatrix}\alpha_0\alpha_0^*&\alpha_0\alpha_1^*\\\alpha_1\alpha_0^*&\alpha_1\alpha_1^*\end{bmatrix}\
  =\begin{bmatrix}\cos^2(\theta/2)&e^{-i\phi}\cos(\theta/2)\sin(\theta/2)\\e^{i\phi}\sin(\theta/2)\cos(\theta/2)&\sin^2(\theta/2)\end{bmatrix}$

- $\rho\
  =\begin{bmatrix}\frac{1}{2}(1+\cos\theta)&\frac{1}{2}(\cos\phi-i\sin\phi)\sin\theta\\\frac{1}{2}(\cos\phi+i\sin\phi)\sin\theta&\frac{1}{2}(1-\cos\theta)\end{bmatrix}$
  $=\frac{1}{2}\left(\
  \begin{bmatrix}1&0\\0&1\end{bmatrix}\
  +\cos\phi\sin\theta\begin{bmatrix}0&1\\1&0\end{bmatrix}\
  +\sin\phi\sin\theta\begin{bmatrix}0&-i\\i&0\end{bmatrix}+\
  \cos\theta\begin{bmatrix}1&0\\0&-1\end{bmatrix}\
  \right)$
  $=\frac{1}{2}(I+\mathbf r\cdot\mathbf \sigma)$.
  - Bloch vector: $\mathbf r=[\sin\theta\cos\phi~~\sin\theta\sin\phi~~\cos\theta]\in\mathbb R^3$
    - $|\mathbf r|^2=\sin^2\theta\cos^2\phi+\sin^2\theta\sin^2\phi+\cos^2\theta=1$.

  - Pauli matrices: $\mathbf\sigma=[\sigma_x~~\sigma_y~~\sigma_z]$.


## [Maximally Mixed State at Bloch Sphere Center](https://youtu.be/LUzdNjqr0jA)

- $\rho=\frac{1}{2}(I+\mathbf r\cdot\mathbf \sigma)=\frac{1}{2}(I+x\sigma_x+y\sigma_y+z\sigma_z)$.

  - $\Tr\rho=\frac{1}{2}(2+x\Tr\sigma_x+y\Tr\sigma_y+z\Tr\sigma_z)=\frac{1}{2}(2+0+0+0)=1$.

  - $\Tr\sigma_i=0$, where $i$ is $x$, $y$, or $z$.

  - Let $T_{ij}=\Tr\sigma_i\sigma_j$.
    In the following, we write $\begin{bmatrix}a&b\\c&d\end{bmatrix}$ as $a,b,c,d$.

    | $ij$ | $\sigma_i\sigma_j$ | $\Tr\sigma_i\sigma_j$ |
    | ---- | ------------------ | --------------------- |
    | $xx$ | $I$                | $2$                   |
    | $xy$ | $iZ$               | $0$                   |
    | $xz$ | $-iY$              | $0$                   |
    | $yx$ | $-iZ$              | $0$                   |
    | $yz$ | $-iI$              | $-2i$                 |
    | $yy$ | $I$                | $2$                   |
    | $zx$ | $iY$               | $0$                   |
    | $zy$ | $iI$               | $2i$                  |
    | $zz$ | $I$                | $2$                   |

  - $\rho^2=\frac{1}{4}(I+2(\sum_k\sigma_k)+\sum_{ij}\sigma_i\sigma_j)$.

  - $\rho^2=\frac{1}{4}(I+2\sum_kk\sigma_k+\sum_{ij}ij\sigma_i\sigma_j)$.

  - $\Tr\rho^2=\frac{1}{4}(2+2(x^2+y^2+z^2))=\frac{1}{2}(1+|r|^2)$.

    - $\frac{1}{2}\le\Tr\rho^2\le 1$ as $0\le|r|^2\le 1$.


---

LaTeX

$$
\newcommand{\Rsr}[1]{\frac{1}{\sqrt{#1}}}
\newcommand{\Tr}{\mathrm{Tr}}
$$
