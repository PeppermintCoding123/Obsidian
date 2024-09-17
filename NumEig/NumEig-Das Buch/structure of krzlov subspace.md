#NumEig #KrylovSubspace 
[[Numerical Methods for Eigenvalue Problems - Steffen Börn, Christian Mehl]]
[[7.2 Krylov subspace]]

Idear:
for Polynomial $p(t)=\beta_l t^l + ... + \beta_1 t^1 + \beta_0$    with $\beta_i \in \mathbb{F}$ define polynomial Map: $p: \mathbb{F}^{\:n \times n} \rightarrow \mathbb{F}^{\:n \times n}$ 
$p(A)=\beta_l A^l + ... + \beta_1 A^1 + \beta_0 I_n$
Vectorspace all polynomials over $\mathbb{F}$ : $\mathbb{F}[t]$
subspace of all polynomials of degree not exceding m: $\mathbb{F}_m[t]$ 

- polynomial Map (Ringhomomorphismus zum Vektorraum ... https://mathworld.wolfram.com/PolynomialMap.html)


Lemma 7.7
"
$A\in \mathbb{F}^{\:n\times n}$    and   $x \in \mathbb{F}^{\:n}$ 
=>  $\mathcal{K}_m(A,x) = \{p(A)x \; | p \in \mathbb{F}_{\:m-1}[t]\}$
"

proof ---


=> Block
Let $A\in \mathbb{F}^{\:n\times n}$    and   $x \in \mathbb{F}^{\:n}  \backslash \{0\}$ and $l$ be as in Therom 7.5. [[dimention of Krylov sunspaces]] 
=> $\exists \beta_i \in \mathbb{F}  \forall i \in \{1,...,l-1\}$ :      $A^lx= -\beta_0 x - ... - \beta_1 A^{l-1}x$
where $\beta_i = \frac{ai}{al}$

$\Longleftrightarrow p(A)x = 0$    and $p(t) = t^l +\beta_{l-1} t^{l-1} + ... + \beta_1 t^1 + \beta_0$ 

p = unique monic polynomial of minimal degree satisfying $p(A)x = 0$

monic polynomial= leading coeffitiant = 1
