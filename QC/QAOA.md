# QAOA

- Ref

  - [Quantum Approximate Optimisation Algorithm](https://pennylane.ai/qml/demos/tutorial_qaoa_intro.html)

  - [Hamiltonian](./Hamiltonia.md)

- Hamiltonian $H$ is a Hermitian operator with real eigenvalues and therefore used in measurements: $\Braket{\psi|H|\psi}$.

- A unitary is used to implement quantum gates by evolving $U(H,t)=e^{-iHt/\hbar}$ with an engineered $H$ and precision timing.

- For commuting Hamiltonians $H_k$, we have $e^{-i\sum_k Ht}=\prod_ke^{-iH_kt}$, where $H=\sum_kH_k$ taking $\hbar=1$.

- For non-commuting $H_k$, we have [Trotter-Suzuki](https://en.wikipedia.org/wiki/Lie_product_formula) decomposition formula: $e^{A+B}\approx\left(e^{A/n}e^{B/n}\right)^n.$

  - $U(H,t,n)\equiv(\prod_ke^{-iH_kt/n})^n\approx e^{-i\sum_k H_kt}$.

  - `qml.templates.ApproxTimeEvolution(H, t, n)` implements a circuit using $U(H,t,n)$.

  - ??Example - $\sigma^p_k$ is a Pauli matrix $(\sigma^x,\sigma^y,\sigma^z)$ operating on qubit $k$ (to avoid writing tensor products, e.g., $\ldots\otimes X\otimes\ldots$

    - $H=\sigma^x_0+\sigma^z_1+\frac{1}{2}\sigma^x_0\otimes\sigma^x_1$.

    - $e^{-iH}\approx e^{-i\sigma^x_0}e^{-i\sigma^z_1}e^{-i\frac{1}{2}\sigma^x_0\otimes\sigma^x_1}$.

    - $e^{-i\frac{\pi}{2}H}$ is presented as

      ```
          (1.5708) [X0]
        + (1.5708) [Z1]
        + (0.7854) [X0 X1]
      ```

    - Notes

      - The coefficient here is the exponent factor: $e^{-ic\sigma^p}=R_p(2c)$.
        - For a Pauli matrix $P,c=\frac{\pi}{2}$ and $R_p(\pi)=e^{-i\frac{\pi}{2}\sigma^p}=-iP$.

    - $U(H,1,4)=(e^{-i\sigma^x_0/4}e^{-i\sigma^z_1/4}e^{-i\sigma^x_0\sigma^x_1/8})^4$

      - $c=t/n$ .

    - $e^{-i\sigma^x_0/4}$ as $HR_z(1/2)H$,   Note: $HZH=X$

    - $e^{-i\sigma^z_1/4}$ as $R_z(1/2)$

    - $e^{-i\sigma^x_0\sigma^x_1/8}$ as $H^{\otimes 2}R_{zz}(1/4)H^{\otimes 2}$   Note: $H^{\otimes 2}Z^{\otimes 2}H^{\otimes 2}=(HZH)^{\otimes 2}=X^{\otimes 2}$

    - The circuit looks like:

      ```
         0: ──H──RZ(0.5)──H──H──╭RZ(0.25)──H──
         1: ─────RZ(0.5)─────H──╰RZ(0.25)──H──

            ──H──RZ(0.5)──H──H──╭RZ(0.25)──H──
            ─────RZ(0.5)─────H──╰RZ(0.25)──H─

            ──H──RZ(0.5)──H──H──╭RZ(0.25)──H─
            ─────RZ(0.5)─────H──╰RZ(0.25)──H─

            ──H──RZ(0.5)──H──H──╭RZ(0.25)──H──┤ ⟨Z⟩
            ─────RZ(0.5)─────H──╰RZ(0.25)──H──┤ ⟨Z⟩
      ```

- QAOA

  - Ansatz state - a parameterised "guess" as an initial state $\Ket s=\Ket{-,-,\ldots}$ in this example.
  - Parameter: $(\vec\beta,\vec\gamma)$, where
    - $\beta=(\beta_1,\beta_2,\ldots,\beta_p)$ and $\gamma=(\gamma_1,\gamma_2,\ldots,\gamma_p)$ for $p$ steps
    - $\beta_j\in(0,\pi)$ and $\gamma_j\in(0,2\pi)$
  - Recall: $U(H,t)=e^{-iHt/\hbar}$, which can be reinterpreted as $U_h(\theta)=e^{-i\theta\sigma^h}$.
  - For each vertex $j$, we use $U_{x_j}(\beta)=e^{-i\beta\sigma_j^x}$, and therefore the Hamiltonian is $U_x(\beta)=\prod_jU_{x_j}(\beta)=e^{-i\beta\sum_j\sigma_j^x}$.
  - For each edge $j,k$, we use $U_{zz_{j,k}}(\gamma)=e^{-i\gamma\sigma_j^z\sigma_k^z}$, and therefore the Hamiltonian is $U_{zz}(\gamma)=\prod_{j>k}U_{zz_{j,k}}(\gamma)=e^{-i\gamma\sum_{i>j}\sigma_j^z\sigma_k^z}=e^{-i\gamma H_C}$
  - Parameterised state at depth $p$: $\Ket{\gamma_p,\beta_p}=U_x(\beta_p)U_{zz}(\gamma_p)\ldots U_x(\beta_1)U_{zz}(\gamma_1)\Ket s$
  - From the measurement probability distribution, the value of the cost function $H_C$ can be evaluated (classically)
    - Expectation value: $E(\gamma,\beta)=\Braket{H_C}$.
  - The bitstring of the most probable measurement in depth $p$ with minimum $\Braket{H_C}$ is the QAOA solution.

- Pseudo code

  - Input graph `G`
  - Produce Ising matrix `Jfull` from `G`
  - Functions
    - `driver(beta, n_qubits)`
      - Generate circuit for $U_x(\beta)=e^{-i\beta\sum_j\sigma_j^x}$
      - Each qubit is rotated with `rx()` by $\theta$, hence $\beta=\theta/2$ and $\theta=2\beta$
    - `cost_circuit(gamma, n_qubits, ising, device)`
      - Generate circuit for $U_{zz}(\gamma)=e^{-i\gamma\sum_{i>j}\sigma_j^z\sigma_k^z}$
      - For each non-zero in `ising` rotate with `ZZgate(j, k, gamma)` by $\theta$.
      - As $J_{i,j}\in[0,1],J_{i,j}\gamma=\theta/2$, hence $\theta=2J_{i,j}\gamma$.
    - `circuit(params, device, n_qubits, ising)`
      - Generate circuit $U(\gamma,\beta)=U_x(\beta_p)U_{zz}(\gamma_p)\ldots U_x(\beta_1)U_{zz}(\gamma_1)$, such that $\Ket{\gamma_p,\beta_p}=U(\gamma,\beta)\Ket s$
      - Set up $\Ket s$ to be $\Ket-\ldots$
      - Call `cost_circuit()` and `driver()` for all `gammas` and `betas` extracted from `params` to add to the circuit
    - `objective_functions(params, device, ising, n_qubits, n_shots, tracker, verbose)`
      - Return the expectation value $E(\gamma,\beta)$
      - Run the QAOA `circuit()`
      - Map all result bitstrings $z$ 0 to -1
      - Energies of all bitstrings in the result: $\Braket{H_C}_z=\Braket{z|J|z}$ where $m$ is the result and $J$ is the ising
      - Track the minimum energy and its bitstring $z$
      - Return expectation value: average of all energies
    - `train(device, options, p, ising, n_qubits, n_shots, opt_method, tracker, verbose)`
      - Return the minimum energy, angles and tracker information (called once)
      - Generate `params0` (initial $\gamma$ and $\beta$)
      - Set bounds: $\gamma\in(0,2\pi)$ and $\beta\in(0,\pi)$.
      - `minimize(objective_function, params0, args, options, method, bounds)`
      - Return the results


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
