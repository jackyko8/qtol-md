# Density Matrix

Ref: [Quantum Physics with Konstantin Lakic](https://youtu.be/kqnMgQzjLmQ) Playlist No. 105-107

## [Density Matrix for Pure Qubit States](https://youtu.be/kqnMgQzjLmQ)

- A pure state in general form: $\Ket\psi=e^{i\omega}(\cos(\theta/2)\Ket0+e^{i\phi}\sin(\theta/2)\Ket1)=\alpha_0\Ket0+\alpha_1\Ket1=\begin{bmatrix}\alpha_0\\\alpha_1\end{bmatrix}$.
  - $\omega,\phi\in[0,2\pi)$.
  - $\alpha_0=e^{i\omega}\cos(\theta/2)=\Braket{0|\psi}$.
  - $\alpha_1=e^{i\omega}e^{i\phi}\sin(\theta/2)=\Braket{1|\psi}$.
  
- Dual vector: $\Bra\psi=e^{-i\omega}(\cos(\theta/2)\Bra0+e^{-i\phi}\sin(\theta/2)\Bra1)=\alpha_0^*\Bra0+\alpha_1^*\Bra1=[\alpha_0^*~~\alpha_1^*]$.

- Density Matrix: $\rho=\Ket\psi\Bra\psi\
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
        =\Braket{0|\psi}\Braket{\psi|0}+\Braket{1|\psi}\Braket{\psi|1}\
        =\Braket{\psi|0}\Braket{0|\psi}+\Braket{\psi|1}\Braket{1|\psi}$ 
        $=\Bra\psi(\Ket0\Bra0+\Ket1\Bra1)\Ket\psi\
        =\Braket{\psi|I|\psi}\
        =\Braket{\psi|\psi}\
        =|\psi|^2$.

- Hermitian

  - $\rho^\dagger=(\Ket\psi\Bra\psi)^\dagger=\Ket\psi\Bra\psi=\rho$.

- Pureness test

  - Pure state

    - $\rho^2=\Ket\psi\Braket{\psi|\psi}\Bra\psi=\Ket\psi\Bra\psi=\rho$.
    - Implying $\rho^n=\rho$.
    - Example:
      - $\Ket\psi=\Rsr2(\Ket0+\Ket1)$.
      - $\rho=\Ket\psi\Bra\psi=\frac{1}{2}(I+X)$.
      - $\Tr\rho=1$.
    - Pauli pure states
      - $\rho_{x+}=\frac{1}{2}(\Ket0\Bra0+\Ket0\Bra1+\Ket1\Bra0+\Ket1\Bra1)=\frac{1}{2}(I+X)$.
      - $\rho_{x-}=\frac{1}{2}(\Ket0\Bra0-\Ket0\Bra1+\Ket1\Bra0-\Ket1\Bra1)=\frac{1}{2}(I-X)$.
      - $\rho_{y+}=\frac{1}{2}(\Ket0\Bra0-i\Ket0\Bra1+i\Ket1\Bra0+\Ket1\Bra1)=\frac{1}{2}(I+Y)$.
      - $\rho_{y-}=\frac{1}{2}(\Ket0\Bra0+i\Ket0\Bra1-i\Ket1\Bra0+\Ket1\Bra1)=\frac{1}{2}(I-Y)$.
      - $\rho_{z+}=\Ket0\Bra0=\frac{1}{2}(I+Z)$.
      - $\rho_{z-}=\Ket1\Bra1=\frac{1}{2}(I-Z)$.
  
  - Mixed state
  
    - $\rho'=\sum_i q_i\Ket{\psi_i}\Bra{\psi_i}$, where $\sum_i q_i=1$ and $\Braket{\psi_i|\psi_j}=\delta_{ij}$ (eigen decomposition).
  
    - $\Tr\rho'\
      =\Tr\sum_i q_i\Ket{\psi_i}\Bra{\psi_i}\
      =\sum_i q_i\Tr\Ket{\psi_i}\Bra{\psi_i}\
      =\sum_i q_i\
      =1$.
  
    - $\rho'^2\
      =\sum_{i,j}q_iq_j\Ket{\psi_i}\Braket{\psi_i|\psi_j}\Bra{\psi_j}$ 
      $=\sum_i q_i^2\Ket{\psi_i}\Braket{\psi_i|\psi_i}\Bra{\psi_i}+\sum_{i\ne j}q_iq_j\Ket{\psi_i}\Braket{\psi_i|\psi_j}\Bra{\psi_j}$.
  
    - $\Tr\rho'^2\le\Tr\rho^2=1$ and equal only applies if there is only one term in $\rho'$.
      
      - Note: $a_i\in[0,1),a_i^2\le a_i,\sum a_i^2\le \sum a_i$.
  
      - Note: If $\rho_n$ contains $n$ unique states, $\lim_{n\to\infty}\Tr\rho_n=0$ (maximum mixed state).
        - Assume equal probably of $n$ states, so $q=1/n$ and $\sum q^2=n/n^2=1/n$.
      
    - Example:
    
      - $\rho'=\frac{1}{2}\Ket0\Bra0+\frac{1}{2}\Ket1\Bra1$.
    
      - $\rho'^2\
        =\frac{1}{4}(\Ket0\Braket{0|0}\Bra0+\Ket0\Braket{0|1}\Bra1+\Ket1\Braket{1|0}\Bra0+\Ket1\Braket{1|1}\Bra1)$ 
    
        $=\frac{1}{4}(\Ket0\Bra0+\Ket1\Bra1)=\frac{1}{4}I$.
    
      - $\Tr\rho'^2=\frac{1}{2}$.



## [Density Matrix and Bloch Sphere Visualization](https://youtu.be/ZmU6vRFPHr8)

- Recall:
  $\rho=\Ket\psi\Bra\psi\
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

### jko

$$
\require{cancel}
\newcommand{\Ket}[1]{\left|{#1}\right\rangle}
\newcommand{\Bra}[1]{\left\langle{#1}\right|}
\newcommand{\Braket}[1]{\left\langle{#1}\right\rangle}
\newcommand{\Rsr}[1]{\frac{1}{\sqrt{#1}}}
\newcommand{\RSR}[1]{1/\sqrt{#1}}
\newcommand{\Verti}{\rvert}
\newcommand{\HAT}[1]{\hat{\,#1~}}
\DeclareMathOperator{\Tr}{Tr}
$$

