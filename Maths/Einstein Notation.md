# Einstein Notation

Ref: https://en.wikipedia.org/wiki/Einstein_notation

Here we use $E$ to mean an expression.

- Same index cannot appear more than twice.
- Omit the summation mark
  - $y=\sum_iE_i~~\rightarrow~~y=E_i$
- Subscripts and superscripts
  - Superscripts represent vectors (column)
  - Subscripts represent covectors (row)
  - $v=v^ie_i=[e_1~~e_2~~\ldots~~e_n]\begin{bmatrix}v_1\\v_2\\\vdots\\v_n\end{bmatrix}$.
  - $w=w_ie^i=[w_1~~w_2~~\ldots~~w_n]\begin{bmatrix}e_1\\e_2\\\vdots\\e_n\end{bmatrix}$.
- ??Order of index appearance
  - When we have both superscripts and subscripts, inner products is implied (regardless of order of appearance).
  - When we have only subscripts, outer products is implied (order is significant).
    - $v\otimes w^T=[v_iw_j]~~\rightarrow~~v^i\otimes w_j=v_iw_j$.
- Matrices $A_{ij}$
  - Vector $u^i=A^i_{~j}v_j$.
    - Row $i$ of column vector $u$ is the sum of row $i$ and column $j$ of $A$ times column $j$ of $v$.
    - $i$ is the "vertical" index (row index).
    - $j$ is the "horizontal" index (column index).
    - Notice the space before $j$ in $A^i_{~j}$ .
  - Multiplication
    - $C_{ij}=(AB)_{ij}~~\rightarrow~~C^i_{~k}=A^i_{~j}B^j_{~k}$.
  - Trace
    - $\Tr A=A^i_{~i}$.
- Braket
  - $\Ket\psi=\psi^i$.
  - $\Bra\psi=\psi_i$ .
  - $\Braket{\psi|\phi}=\psi_j\phi^i$.
  - ??If $M=\Ket\phi\Bra\psi$, then $M^i_{~j}=\phi_i\psi_j$.

