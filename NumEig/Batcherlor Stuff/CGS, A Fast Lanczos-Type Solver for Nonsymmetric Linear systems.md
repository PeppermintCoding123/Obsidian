https://epubs.siam.org/doi/abs/10.1137/0910004
Siehe PDF
Conjugate Gradients Squared
#NumEig 

##### Abstract:
#LanczosAlgorithm
Based on polynomial variant of the [[CG - conjugate gradient]] algorithm

#### 1. Introduction
CG is simple for SPD-matricies, but for non-SPD => problems.
Generalisations: Generalised Conjugate Gradients, [[Orthomin]], [[Orthodir]], Bi-Conjugate Gradients, Induced Dimension
Reduction, variants of Petrov-Galerkin approach
Most use preconditioning

CF-type methods : CG has three-term relations for efficiant storage.
for not SPD: use coefficiant matrix: $A^TA$ created by by applying Paige’s bi-diagonalisation algorithm
Other posibilities:
1. maintain minimisation: next search as combo of $r_n$ & $s$ => Orthomin, Orthodir, Generalised Conjugate Gradients.
2. maintain three-term recursion: reinterpret CG => Bi-Conjugate Gradients, Induced Dimension Reduction
3. maintain three-term recursion & abandon CG: not Lanczos-type, but Chebyshev-like methods => Manteuffel-
Chebyshev
4. maintain a three-term recursion: split off symmetric part
Here: 2. Option

#### 2. The polynomial equivalent of the CG method.
The Problem: $A\in\mathbb{C}^{N\times N}$, solve $Ax=b$, $x_0$= initial vector

##### CG algorithm:
$r_0 = b-Ax_0$
$p_{-1} = 0$
$\rho_{-1} = 1$
$n=0$
while $residual>tolerance$ do:
	$\rho_{n}=r_n^Tr_n$
	$\beta_n = \rho_n/\rho_{n-1}$
	$p_n = r_n + \beta_np_{n-1}$
	$\sigma_n = p_n^TAp_n$
	$\alpha_n = \rho_n/\sigma_n$
	$r_{n+1} = r_n - \alpha_n Ap_n$
	$x_{n+1} = x_n + \alpha_np_n$
	n = n+1
residual = $r_n = b-Ax_n$, direction $p_n$
for each step $E_n = r_n^TA^{-1}r_n$ is minimized

Develop:
$r_n = \varphi_n(A)r_0$, $p_n = \psi_n(A)r_0$
with $\varphi_n$ and $\psi_n$ polynomials of deg <= n, and with  $\forall\tau\in \mathbb{R}$
$\psi_n(\tau)=\varphi_n(\tau)+\beta_n\psi_{n-1}(\tau)$
$\varphi_{n+1}(\tau)=\varphi_n(\tau)-\alpha_n\tau\psi_n(\tau)$
$p_n = \varphi_n(A)r_0 + \beta_n\psi_{n-1}(A)r_0 = \psi_n(A)r_0$
$r_{n+1} = \varphi_n(A)r_0- \alpha_nA\psi_n(A)r_0 = \varphi_{n+1}(A)r_0$

symmetric bilinearform of set of real polynomials deg <=N:
$(\varphi,\psi)=[\varphi(A)r_0]^T\psi(A)r_0$

##### polynomial CG algorithem
...
Ab hier nicht tippen, außer wenn wirklich nützlich...

##### Bi-Conjugate Gradients algorithm
... (2.10)

#### 3. Squaring the CG algorithm: The CGS algorithm
explaining why Bi-Conjugate is terrible

##### CGS algorithm (3.3)
$r_0 = b-Ax_0$
$q_0 = p_{-1}=0$
$\rho_{-1} = 1$
$n=0$
while $residual>tolerance$ do:
	$\rho_n = \tilde{r}_0^Tr_n$
	$\beta_n = \rho_n/\rho_{n-1}$
	$u_n = r_n + \beta_nq_n$
	$p_n = u_n + \beta_n(q_n+\beta_np_{n-1})$
	$v_n=Ap_n$
	$\sigma_n = \tilde{r}_0^Tv_n$
	$\alpha_n = \rho_n/\sigma_n$
	$p_{n+1} = u_n-\alpha_nv_n$
	$r_{n+1} = r_n-\alpha_nA(u_n+q_{n+1})$
	$x_{n+1}=x_{n}+\alpha(u_n+q_{n+1})$
	$n = n+1$
$\tilde{r}_n$ just choose $r_n$
#### 4. Convergence and preconditioning
preconditioning may improve stuff
usually same as Bi-Conjugate and simmilar to CG with SPD.
proove stuff....

#TODO Type & Implement


Also See: [[Lanczos-type algorithms for solving systems of linear equations ]] 