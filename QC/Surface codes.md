# [Surface codes](https://arxiv.org/pdf/1208.0928.pdf)

- Pauli Gates Symmetry
  - Page 3 and 40
  - $\sigma_x=\begin{bmatrix}0&1\\1&0\end{bmatrix},\sigma_y=\begin{bmatrix}0&-i\\i&0\end{bmatrix},\sigma_z=\begin{bmatrix}1&0\\0&-1\end{bmatrix}.$
    - $\sigma_x^2=\sigma_y^2=\sigma_z^2=I.$
    - $\sigma_x\sigma_y=i\sigma_z=-\sigma_y\sigma_x.$
    - $\sigma_y\sigma_z=i\sigma_x=-\sigma_z\sigma_y.$
    - $\sigma_z\sigma_x=i\sigma_y=-\sigma_x\sigma_z.$
  - $\hat X=\begin{bmatrix}0&1\\1&0\end{bmatrix},\hat Y=-i\sigma_y=\begin{bmatrix}0&-1\\1&0\end{bmatrix},\hat Z=\begin{bmatrix}1&0\\0&-1\end{bmatrix}.$
    - $X^2=-Y^2=Z^2=I.$
    - $\hat X\hat Y=\hat Z=-\hat Y\hat X, $ and therefore $\hat X\hat Y-\hat Y\hat X=2\hat Z.$
    - $\hat Y\hat Z=\hat X=-\hat Z\hat Y.$
    - $\hat Z\hat X=-\hat Y=-\hat X\hat Z.$
  - On Page 3 that $\hat X\hat Y-\hat Y\hat X=-2\hat Z$, contrary to the above.
    - Alternatively, letting $\hat Y=i\sigma_y=\begin{bmatrix}0&1\\-1&0\end{bmatrix}$ will resolve the issue:
    - $X^2=-Y^2=Z^2=I.$
    - $\hat X\hat Y=-\hat Z=-\hat Y\hat X,$ and therefore $\hat X\hat Y-\hat Y\hat X=-2\hat Z.$
    - $\hat Y\hat Z=-\hat X=-\hat Z\hat Y.$
    - $\hat Z\hat X=\hat Y=-\hat X\hat Z.$

- Operators on different qubits commute
  - $[\hat X_a,\hat Z_b]=(\hat X_a\otimes\hat I_b)(\hat I_a\otimes\hat Z_b)-(\hat I_a\otimes\hat Z_b)(\hat X_a\otimes\hat I_b)$
    - $=\hat X_a\hat I_a\otimes\hat I_b\hat Z_b-\hat I_a\hat X_a\otimes\hat Z_b\hat I_b$
    - $=(\hat X_a\hat I_a-\hat I_a\hat X_a)\otimes(\hat I_b\hat Z_b-\hat Z_b\hat I_b)=0.$

  - Likewise, $[\hat Z_a,\hat X_b]=0.$
  - That means measuring on $q_a$ does not affect subsequent measurment on $q_b$.

- Operators on joint-qubit states commute
  - $[\hat X_a\hat X_b,\hat Z_a\hat Z_b]=(\hat X_a\hat X_b)(\hat Z_a\hat Z_b)-(\hat Z_a\hat Z_b)(\hat X_a\hat X_b)$
    - $=\hat X_a\hat Z_a\hat X_b\hat Z_b-\hat Z_a\hat X_a\hat Z_b\hat X_b=\hat X_a\hat Z_a\hat X_b\hat Z_b-\hat X_a\hat Z_a\hat X_b\hat Z_b=0.$

  - Each of $\hat X_a\hat X_b$ and $\hat Z_a\hat Z_b$ has four eigenstates:
    - $\hat X_a\hat X_b=\begin{bmatrix}0&0&0&1\\0&0&1&0\\0&1&0&0\\1&0&0&0\end{bmatrix}$.
      - Four eigenstates: $\frac{1}{2}\begin{bmatrix}1\\1\\1\\1\end{bmatrix},-\frac{1}{2}\begin{bmatrix}1\\-1\\1\\-1\end{bmatrix},-\frac{1}{2}\begin{bmatrix}1\\1\\-1\\-1\end{bmatrix},\frac{1}{2}\begin{bmatrix}1\\-1\\-1\\1\end{bmatrix}$.
      - Or: $\frac{1}{2}\Ket{++},-\frac{1}{2}\Ket{+-},-\frac{1}{2}\Ket{-+},\frac{1}{2}\Ket{--}$.
      - For eigenvalue $+1$, $\Ket{++}$ and $\Ket{--}$ forms a 2D eigenspace, containing $\Rsr2(\Ket{00}+\Ket{11})$ and $\Rsr2(\Ket{01}+\Ket{10})$.
      - For eigenvalue $-1$, $\Ket{+-}$ and $\Ket{-+}$ forms a 2D eigenspace, containing $\Rsr2(\Ket{00}-\Ket{11})$ and $\Rsr2(\Ket{01}-\Ket{10})$.

    - $\hat Z_a\hat Z_b=\begin{bmatrix}1&0&0&0\\0&-1&0&0\\0&0&-1&0\\0&0&0&1\end{bmatrix}$.
      - Four eigenstates: $\begin{bmatrix}1\\0\\0\\0\end{bmatrix},-\begin{bmatrix}0\\1\\0\\0\end{bmatrix},-\begin{bmatrix}0\\0\\1\\0\end{bmatrix},\begin{bmatrix}0\\0\\0\\1\end{bmatrix}$.
      - Or: $\Ket{00},-\Ket{01},-\Ket{10},\Ket{11}$.
      - For eigenvalue $+1$, $\Ket{00}$ and $\Ket{11}$ forms a 2D eigenspace, containing $\Rsr2(\Ket{00}\pm\Ket{11})$.
      - For eigenvalue $-1$, $\Ket{01}$ and $\Ket{10}$ forms a 2D eigenspace, containing $\Rsr2(\Ket{01}\pm\Ket{10})$.

    - Four simultaneous eigenvectors

      | $\hat Z_a\hat Z_b$ eigenvalue | $\hat X_a\hat X_b$ eigenvalue | Simultaneous eigenstate    |
      | ----------------------------- | ----------------------------- | -------------------------- |
      | $+1$                          | $+1$                          | $\Rsr2(\Ket{00}+\Ket{11})$ |
      | $+1$                          | $-1$                          | $\Rsr2(\Ket{00}-\Ket{11})$ |
      | $-1$                          | $+1$                          | $\Rsr2(\Ket{01}+\Ket{10})$ |
      | $-1$                          | $-1$                          | $\Rsr2(\Ket{01}-\Ket{10})$ |

    - These four states can be measured repeatedly by $\hat X_a\hat X_b\hat Z_a\hat Z_b$ or $\hat Z_a\hat Z_b\hat X_a\hat X_b$ without collapsing on other observables.

- Stabiliser operator

  - Repeatedly measuring the system using commuting operator to stabilise the system from errors.

  - The stabiliser operation $\hat X_a\hat X_b\hat Z_a\hat Z_b=\hat Z_a\hat Z_b\hat X_a\hat X_b=\begin{bmatrix}0&0&0&1\\0&0&-1&0\\0&-1&0&0\\1&0&0&0\end{bmatrix}$ (order agnostic as they commute)

    | Stabliser eigenvalue | Simultaneous eigenstates (Bell states)   |
    | -------------------- | ---------------------------------------- |
    | $+1$                 | $\Ket{\beta_0}=\Rsr2(\Ket{00}+\Ket{11})$ |
    | $-1$                 | $\Ket{\beta_1}=\Rsr2(\Ket{00}-\Ket{11})$ |
    | $-1$                 | $\Ket{\beta_2}=\Rsr2(\Ket{01}+\Ket{10})$ |
    | $+1$                 | $\Ket{\beta_3}=\Rsr2(\Ket{01}-\Ket{10})$ |

  - Error on a single qubit:

    | Error                    | Transformation                                               |
    | ------------------------ | ------------------------------------------------------------ |
    | $\hat X_a$ or $\hat X_b$ | $\Ket{\beta_0}\leftrightarrow\Ket{\beta_2}$, $\Ket{\beta_1}\leftrightarrow\Ket{\beta_3}$ |
    | $\hat Z_a$ or $\hat Z_b$ | $\Ket{\beta_0}\leftrightarrow\Ket{\beta_1}$, $\Ket{\beta_2}\leftrightarrow\Ket{\beta_3}$ |

  - In both cases, the sign of the stabiliser eigenvalue has changed, but we cannot tell which error occurred.

- Surface code

  - | F++  | T++  |      | F+-  | T+-  |      | F-+  | T--  |      | F--  | T-+  |
    | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
    | 1    | 1    |      | 1    | 1    |      | 1    | 1    |      | 1    | 1    |
    | 1    | 1    |      | -1   | -1   |      | 1    | -1   |      | -1   | 1    |
    | 1    | 1    |      | 1    | 1    |      | -1   | -1   |      | -1   | -1   |
    | 1    | 1    |      | -1   | -1   |      | -1   | 1    |      | 1    | -1   |

  - $HXH=Z$

  - $H_AH_BCxH_AH_B
    =\Rsr2\begin{bmatrix}H&H\\H&-H\end{bmatrix}\begin{bmatrix}I&0\\0&X\end{bmatrix}\Rsr2\begin{bmatrix}H&H\\H&-H\end{bmatrix}
    =\frac{1}{2}\begin{bmatrix}H&H\\H&-H\end{bmatrix}\begin{bmatrix}H&H\\XH&-XH\end{bmatrix}$

    $=\frac{1}{2}\begin{bmatrix}I+Z&I-Z\\I-Z&I+Z\end{bmatrix}
    =\begin{bmatrix}1&0&0&0\\0&0&0&1\\0&0&1&0\\0&1&0&0\end{bmatrix}$

  - $\begin{bmatrix}1&1&1&1\\1&-1&1&-1\\1&1&-1&-1\\1&-1&1&-1\end{bmatrix}$.

  - $I_AH_BCxI_AH_B
    =\begin{bmatrix}H&0\\0&H\end{bmatrix}\begin{bmatrix}I&0\\0&X\end{bmatrix}\begin{bmatrix}H&0\\0&H\end{bmatrix}
    =\begin{bmatrix}I&0\\0&Z\end{bmatrix}=C_z.$

  - ![Surface code p3](./Surface codes p6.png)

  -







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

