# Abstract Algebra

Ref: [Quantum Physics with Konstantin Lakic](https://youtu.be/kqnMgQzjLmQ) Playlist No. 1-5

## [Groups, Fields and Vector Spaces](https://youtu.be/dj25YjbBWvc) #1

- Group $(G,\bullet)$
- Axioms
  - Closure: $\forall a,b\in G,(a\bullet b)\in G$.
  - Associativity: $\forall a,b,c\in G,(a\bullet b)\bullet c=a\bullet(b\bullet c)$.
  - Identity element: $\exist e\in G:\forall a\in G,a\bullet e=a=e\bullet a$.
  - Inverse element: $\forall a\in G,\exists b\in G:a\bullet b=e=b\bullet a$.
- Consequences
  - Uniqueness of identity element
    - If both $e$ and $f$ are identity elements, then $e=e\bullet f=f$.
  - Uniqueness of inverse element
    - If both $b$ and $c$ are inverse element of $a$, then $b=b\bullet e=b\bullet(a\bullet c)=(b\bullet a)\bullet c=e\bullet c=c$.
  - Identity element is self-inverse but non-identity elements can be self-inverse too.
    - Example: In modular arithmetic $(\mathbb Z/2\mathbb Z,+)$, $0$ is the identity element, but both elements $0$ and $1$ are self-inverse. $0+0\equiv0\mod 2$ and $1+1\equiv0\mod 2$.
- Examples: $(\mathbb Z,+),(\mathbb R,+),(\mathbb C,+),(\mathbb R\backslash\{0\},\times),(\mathbb C\backslash\{0\},\times)$ 
- Abelian Group
  - Commutativity: $\forall a,b\in G,a\bullet b=b\bullet a$.



## [Field Axioms in Abstract Algebra](https://youtu.be/ThyUKo0HMfw) #2

- Field $(F,+,\times)$
- Axioms
  - $(F,+)$ is an Abelian group; identity element denoted by $0$ and inverse of $a$ denoted by $-a$.
  - $(F\backslash\{0\},\times)$ are an Abelian group; identity element denoted by $1$ and inverse of $a$ denoted by $a^{-1}$.
  - Distributivity: $\forall a,b,c\in F,a\times(b+c)=a\times b+a\times c$.
- Consequences
  - Right distributivity: $(a+b)\times c=c\times(a+b)=c\times a+c\times b=a\times c+b\times c$.
  - $\forall a\in F,a\times 0=0$.
    - Let us define $a-b\equiv a+(-b)$.
    - $a\times 0=a\times(1-1)=a\times 1-a\times 1=a-a=0$.
- Examples: $(\mathbb R,+,\times),(\mathbb C,+,\times)$.



## [Circle Group in Complex Plane, Isomorphisms](https://youtu.be/c6xRecA-WP8) #3

- Example: $S^1\equiv\{z\in\mathbb C:|z|=1\}$.
- Group homomorphisms
- Group $(G,\cdot)$ and $(H,*)$, function $\varphi:G\rightarrow H:\forall a,b\in G,\varphi(a\cdot b)=\varphi(a)*\varphi(b)$.
  - Examples: Groups $(\Theta,+)$ and $(S^1,\cdot)$, with $\varphi(\theta)=e^{i\theta}$, where $S^1\equiv\{z\in\mathbb C:|z|=1\}$.
    - $\forall\theta_1,\theta_2\in\Theta,\varphi(\theta_1+\theta_2)=e^{i(\theta_1+\theta_2)}=e^{i\theta_1}\cdot e^{i\theta_2}$.
- A group isomorphism is a homomorphism that has an inverse homomorphism.
  - Examples: Modular Arithmetic $(\mathbb Z/4\mathbb Z,+)$ and $(\{1,i,-1,-i\},\times)$.



## [Vector Space Axioms](https://youtu.be/B3swka6eiIQ)

- Vector space $V$ with scalar field $(F,+,\cdot)$
- $V$ is an Abelian group; identity element denoted by $\mathbf 0$.
- Closure with scalar multiplication: $\forall\mathbf v\in V,\forall\alpha\in F,\alpha\mathbf v\in V$.
  - Scalar multiplication is implied when a scalar is followed by a vector.
- Associativity with scalar multiplication: $\forall\mathbf v\in V,\forall\alpha,\beta\in F,\alpha(\beta\mathbf v)=(\alpha\beta)\mathbf v$.
  - Scalar operator $\cdot$ is implied when a scalar is followed by a scalar.
- Multiplication by scalar identity: $\forall\mathbf v\in V,1\mathbf v=\mathbf v$.
  - $1$ is the identity element of $F$.
- Distributivity with scalar sum: $\forall\mathbf v,\forall\alpha,\beta\in F,(\alpha+\beta)\mathbf v=\alpha\mathbf v+\beta\mathbf v$.
- Distributivity with vector sum: $\forall\mathbf u,\mathbf v\in V,\forall\alpha\in F,\alpha(\mathbf u+\mathbf v)=\alpha\mathbf u+\alpha\mathbf v$.



## [Inner Product Space Axioms, Hilbert Space, Bra-Ket](https://youtu.be/o0br2HAcEuY)

This is an attempt to define an inner product space without resorting to using the concept of "real numbers", "complex numbers", and "positive-definiteness" (which implies measurement). Would be ideal that such concepts are consequences of the definition instead of its essence.

However, ChatGPT gave this response:

```
Q:
Is there an inner product space that does not involve real number or complex number?

A:
In the standard mathematical framework, inner product spaces are defined over either the real numbers or the complex numbers. These two number systems provide the necessary properties and operations required for defining inner products, such as addition, scalar multiplication, and the existence of conjugates.

However, it's worth noting that there are alternative mathematical frameworks or extensions where other number systems are used. For example, in certain branches of abstract algebra, there are structures known as "inner product modules" or "Hilbert modules" that generalize the concept of inner product spaces to different algebraic settings. These structures may involve elements from more general algebraic structures, such as rings or fields other than the real numbers or complex numbers.

So, while the traditional notion of an inner product space relies on real or complex numbers, there are mathematical extensions and generalizations that explore inner product-like structures in different algebraic contexts.
```

Preparation:

- [Normed vector space](https://en.wikipedia.org/wiki/Normed_vector_space)

  - 

- [Quotient space](https://en.wikipedia.org/wiki/Quotient_space_(linear_algebra))

  - $N$ is a subspace of vector space $V$ over scalar field $F$.

  - $v,w\in V,n\in N$.

  - $v\sim w$ means $v-w\in N$.

  - Equivalence class (coset) of $[v]=\{v+n:n\in N\}$.

    - $[v]$ is *not* a subspace of $V$ as it does *not* have an identity element.

  - Quotient space $Q$ contains all equivalence classes.

    - $Q$ is represented by $V/N$.

    - Definition

      - $\alpha[v]\equiv[\alpha v]$.
      - $[v]+[w]\equiv[v+w].$

    - Group $(Q,+)$

      - Closure: $\forall v,w\in Q,[v]+[w]=[v+w]\in Q$.

      - Associativity: $\forall u,v,w\in Q,([u]+[v])+[w]=([u+v])+[w]$

        $=[(u+v)+w]=[u+(v+w)]=[u]+([v+w])=[u]+([v]+[w])$.

      - Identity element: $[v]+[0]=[v+0]=[v]=[0+v]=[0]+[v]$.

      - Inverse element: $[v]+[-v]=[v-v]=[0]$.

    - Alternative view:

      - A quotient space can be viewed as parallel "plane" to the null space of $N$ with respect to the inner product.

In order to continue the discussion, we need to add the following axiomatic proposition:

- Both $(V,+,\times)$ and $(F,+,\cdot)$ are [normed vector space](https://en.wikipedia.org/wiki/Normed_vector_space)
  - Norm: $x\mapsto\lVert x\rVert$
- $R$ is an ordered field:
  - Field $(R,+\times)$ 
  - Less-than relation $\lt$ 
    - $\forall a,b\in R$, exactly one holds: $a\lt b,a=b,b\lt a$.
    - Transitivity: $a\lt b\and b\lt c\Rightarrow a\lt c$.
    - If $a\lt b$, then $a+c\lt b+c$.
    - If $a\lt b$ and $c\ne 0$, then $a\times c\lt b\times c$.
    - Short-hands:
      - $a\le b$ means $a\lt b\or a=b$.
      - $a\gt b$ means $b\lt a$.
      - $a\ge b$ means $a\gt b\or a=b$.
- The scalar field $F$ is an $R^n$, where $R$ is an ordered field.
  - $c\in F$ can be represented as $c=(c_1,c_2,\ldots,c_n)$ where $c_k\in R$.

Following the previous discussion of $V$ and $F$.

- Axioms
  - Inner product: $\Braket{v|w}:V\rightarrow F$
    - $\Braket{u|\alpha w}=\alpha\Braket{u|w}$.
    - $\Braket{u|v+w}=\Braket{u|v}+\Braket{u|w}$.
  - Norm of vector: $\lVert v\rVert^2\equiv\Braket{v|v}(\in F)$.
  - ??Norm of scalar: ...
  - ??Conjugate (of scalar): $\forall\alpha\in F,\exists\beta\in F:\alpha\beta=|\alpha|^2$.
    - $\alpha^*$ represents the conjugate of $\alpha$.
    - Example: In $(\mathbb C,\times),\alpha=a+ib,\beta=a-ib,\alpha\beta=a^2+b^2=|\alpha|^2$, where $a,b\in\mathbb R$.
  - Conjugate symmetry: $\Braket{v|w}=\Braket{w|v}^*$.
    - Note: "Real" means $\alpha^*=\alpha$.
    - $\Braket{v|v}=\Braket{v|v}$ so it is "real" and so is $|v|=\sqrt{\Braket{v|v}}$.
  - ??Positive-definiteness:
    - $\Braket{v|\mathbf0}=\Braket{\mathbf0|v}=0$.
    - For $v\ne\mathbf0$.
      - $\Braket{v|v}\gt0$ (as a definition of larger than)
      - The additive inverse $-\Braket{v|v}\lt0$ (as a definition of smaller than)
- Consequences
  - $\Braket{\alpha u|w}=\alpha^*\Braket{u|w}$.
    - $\Braket{\alpha u|w}=\Braket{w|\alpha u}^*=(\alpha\Braket{w|u})^*$.
  - $(\alpha\beta)^*=\alpha^*\beta^*$.
    - ...
  - Linearity:
    - Left: $\Braket{u|\alpha v+\beta w}=\alpha\Braket{u|v}+\beta\Braket{u|w}$.
    - Right: $\Braket{\alpha v+\beta w|u}=\alpha^*\Braket{v|u}+\beta^*\Braket{w|u}$
  - $(\alpha^*)^*=\alpha$.
    - $\alpha\Braket{u|w}=\Braket{u|\alpha w}=\Braket{\alpha w|u}^*=(\alpha^*\Braket{w|u})^*=(\alpha^*)^*\Braket{u|w}$.
    - ??Multiply $(\Braket{u|w})^{-1}$ on both sides.





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

