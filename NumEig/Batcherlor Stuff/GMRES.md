Saad, Y. and Schultz, M.H.: "GMRES: A Generalized Minimal Residual Algorithm for Solving Nonsymmetric Linear Systems," SIAM Journal on Scientific and Statistical Computing ( 1986) 856.
https://cs.yale.edu/publications/techreports/tr254.pdf

#ArnoldiIteration
#NumEig

= generalisation of [[MINRES - Solution of Sparse Indefinite Systems of Linear Equations]] for solving nonsymmetric linear systems based on #ArnoldiIteration
simmilar to [[GCR - generalized conjugate residual method]], [[Orthodir]] 
when $A$= positive real- produces $x_k$ sequence
when $A$= not positive real GCR breaks down and ORTHODIR is numerically less stable than GCR

GMRES dose not break down even for indefinite symmetric parts unless already covered

## 2 Arnoldi's Method
### Algorithm 1: Arnoldi
Start: Choose an initial vector $v_1$ with $||v_1||=1$
Iterate: for $j = 1,2,...$ do:
	$h_{i,j}=(Av_j,v_i), i=1,2,...,j$
	$\hat{v}_{j+1}=Av_j-\sum_{i=1}^j h_{i,j}v_i$
	$h_{j+1,j}=||\hat{v}_{j+1}||$
	$v_{j+1}=\hat{v}_{j+1}/ h_{j+1,j}$ 

Ususally with modified Gram-Schmidt or Galerkin

### Algorithm 2: Full Orthogonalization Method [[Iterative methods for sparce linear systems]]
Start: Choose $x_0$ and compute $r_0= f-Ax_0$ and $||v_1||=r_0/||r_0||$
Iterate: for $j = 1,2,...$ do:
	$h_{i,j}=(Av_j,v_i), i=1,2,...,j$
	$\hat{v}_{j+1}=Av_j-\sum_{i=1}^j h_{i,j}v_i$
	$h_{j+1,j}=||\hat{v}_{j+1}||$
	$v_{j+1}=\hat{v}_{j+1}/ h_{j+1,j}$ 
Approximate Solution: $x_k = x_0 + V_ky_k$ where  $y_k = H^{-1}_k||r_0||e_1$
- problem: expensive as calculation continues.
	- either restart orthogonalisation every m steps
	- or truncate $l_2$-orthogonalisation - only orthogonal to previous $l$ vectors (IOM(l))

## Generalized Minimal Residual (GMRES)
After Arnoldi:
- $l_2$-orthonormal system $V_{k+1}$ and $(k+1)\times k$ Matrix $\overline{H}_k$ only non-zero entries are $h_{i,j}$, $\overline{H}_k$ is the same as $H_k$ exept $h_{k+1,k}$ in the $k+1,k$ position.
- $AV_k = V_{k+1}\overline{H}_k$
now solve least squares...
### Algorithem 3: GMRES
Start: Choose $x_0$ and compute $r_0= f-Ax_0$ and $||v_1||=r_0/||r_0||$
Iterate: for $j = 1,2,...$ do:
	$h_{i,j}=(Av_j,v_i), i=1,2,...,j$
	$\hat{v}_{j+1}=Av_j-\sum_{i=1}^j h_{i,j}v_i$
	$h_{j+1,j}=||\hat{v}_{j+1}||$
	$v_{j+1}=\hat{v}_{j+1}/ h_{j+1,j}$ 
Approximate Solution: $x_k = x_0 + V_ky_k$ where $y_k$ minimizes $J(y)= ||\beta e_1 - \overline{H}_k y||$

mit $\beta = ||r_0||$, $e_1 =$ Einheitsvector der größe $k+1$, $V_k$ dind ie ersten $k$ Vektoren des Orthonormalsystems von arnoldi, $\overline{H}_k$ ist die $(k+1)\times k$-matrix von arnoldi

Laut Herleitung: $J(y)= ||\beta e_1 - \overline{H}_k y|| = ||V_{k+1}[\beta e_1 - \overline{H}_k y]|| = ||\beta v_1 - AV_k y|| = ||\beta v_1 - V_k^*H_kV_k y||$

See also [[Motivations and realizations of Krylov subspace methods for large sparse linear systems]] Section 3


(10) [[MINRES - Solution of Sparse Indefinite Systems of Linear Equations]]  Solution of Sparse Indefinite Systems of Linear Equations, [C. C. Paige](https://epubs.siam.org/doi/abs/10.1137/0712047#con1) and [M. A. Saunders](https://epubs.siam.org/doi/abs/10.1137/0712047#con2)
- using Lanczos basis to compute residual Norm of Krylov Subspace
(9) [[Generalized conjugate-gradient acceleration of nonsymmetrizable iterative methods]]
(5) [[Variational iterative methods for nonsymmetric systems of linear equations]] 
	(16) has extention on this