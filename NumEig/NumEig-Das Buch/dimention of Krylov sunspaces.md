NumEigNumerischeEigenwerte #KrylovSubspace 
[[Numerical Methods for Eigenvalue Problems - Steffen Börn, Christian Mehl]]
[[7.2 Krylov subspace]]

always $dim(\mathcal{K}_m(A,x)) \leq m$
but can be very small : 
If $x \ne 0$ is Eigenvector of $A$ => $dim(\mathcal{K}_m(A,x)) = 1$

Theorem 7.5
"
$A\in \mathbb{F}^{\:n\times n}$    and   $x \in \mathbb{F}^{\:n}$ 
=> $\exists l \in \mathbb{N} _0$ :
1. $dim(\mathcal{K}_m(A,x)) = m \quad \forall m \leq l$
2. $\mathcal{K}_l(A,x) = \mathcal{K}_m(A,x) \quad  \wedge \quad \mathcal{K}_m(A,x) = l \quad \forall m \leq l$ 

in particular: $\mathcal{K}_l(A,x)$ is an invariant subspace with respect to A
"

The proof of 7.5
...