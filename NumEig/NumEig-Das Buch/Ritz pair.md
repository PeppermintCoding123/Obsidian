#NumEig
[[Numerical Methods for Eigenvalue Problems - Steffen Börn, Christian Mehl]]

#### Defintion 7.2

"Let $A\in \mathbb{F}^{\:n\times n}$ and let $\mathcal{X} \subseteq \mathbb{F}^{\,n}$ be as subspace.
Then a pair $(\mu,\: x)\in \mathbb{F} \times \mathcal{X}$ is called a *Ritz Pair* of A with respect to $\mathcal{X}$ if it satisfies the *Ritz-Galerkin condition*
$$Ax-\mu x \perp \mathcal{X}$$
If $(\mu, x)$ is a Ritz pair, then $\mu$ is called a *Ritz value* and $x$ is called the assosiated *Ritz vector* "

#### The Idear:
$A\in \mathbb{F}^{\,n\times n}$ is matrix and $(\lambda, v) \in \mathbb{F} \times \mathbb{F}^{\, n}$ is an eigenpair of $A$
=> $Av = \lambda v$ , the vector $Av - \lambda v$ = zero vector that is orthogonal to space $\mathbb{F}^{\, n}$ 

replace full space $\mathbb{F}^{\, n}$ with subspace $\mathcal{X} \subseteq \mathbb{F}^{\,n}$
Now look for pairs $(\mu, x) \in \mathbb{F} \times \mathcal{X}$ 
=> $Av - \lambda v \perp \mathcal{X}$ meaning orthogonal to $\mathcal{X}$






