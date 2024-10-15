Deriving CG form Arnoldi
https://en.wikipedia.org/wiki/Derivation_of_the_conjugate_gradient_method

#TODO 
- copy the Wiki formulation
- look if refferances have the same entries
- Write in thesis with correct $i,j$.

## Refferances:
1.  Conjugate Direction Methods [http://user.it.uu.se/~matsh/opt/f8/node5.html](http://user.it.uu.se/~matsh/opt/f8/node5.html)

1. [Hestenes, M. R.](https://en.wikipedia.org/wiki/David_Hestenes "David Hestenes"); [Stiefel, E.](https://en.wikipedia.org/wiki/Eduard_Stiefel "Eduard Stiefel") (December 1952). ["Methods of conjugate gradients for solving linear systems"](http://nvlpubs.nist.gov/nistpubs/jres/049/6/V49.N06.A08.pdf) (PDF). _Journal of Research of the National Bureau of Standards_. **49** (6): 409. [doi](https://en.wikipedia.org/wiki/Doi_(identifier) "Doi (identifier)"):[10.6028/jres.049.044](https://doi.org/10.6028%2Fjres.049.044).
	1. https://nvlpubs.nist.gov/nistpubs/jres/049/6/V49.N06.A08.pdf 
2. Shewchuk, Jonathan Richard. "_[An introduction to the conjugate gradient method without the agonizing pain](https://www.cs.cmu.edu/~quake-papers/painless-conjugate-gradient.pdf)_." (1994)
3. Saad, Y. (2003). "Chapter 6: Krylov Subspace Methods, Part I". [_Iterative methods for sparse linear systems_](https://archive.org/details/iterativemethods0000saad) (2nd ed.). SIAM. [ISBN](https://en.wikipedia.org/wiki/ISBN_(identifier) "ISBN (identifier)") [978-0-89871-534-7](https://en.wikipedia.org/wiki/Special:BookSources/978-0-89871-534-7 "Special:BookSources/978-0-89871-534-7").

based on [[Iterative methods for sparce linear systems]]
## Math
Assume we have Arnoldi with $i\times i$ Hessenberg $H_i$ and solving $y_i = H_i^{-1}(||r_0||_2e_1)$
Assume $A$ is SPD. 
because $A$ is symmetric, $H_i = V_i^TAV_i$ symmetric tridiagonal with $(a_1,...,a_i)$ on diagonal and $(b_2,...,b_i)$ adjacent
=> Lanczos Iteration

Because $A$ is SPD, $H_i$ is SPD. => $\exists$ LU-factorisation of $H_i$ without partial pivoting. $H_i = L_iU_i$
$L_i$ has $(1,...,1)$ on diagonal and $(c_2,....,c_i)$ adjacent left, to form a left lower Matrix.
$U_i$ has $(d_1,...,d_i)$ on diagonal and $(b_2,..., b_i)$ adjacent right, to form a right upper matrix.
With $c_i = b_i / d_{i-1}$ and $d_i = a_1$ if $i=1$ else $d_i = a_i - c_ib_i$ for $i > 1$.

=> $x_i = x_0 + V_i y_i = x_0 + V_i H_i^{-1}(||r_0||_2e_1) = x_0 + V_i U_i^{-1}L_i^{-1}(||r_0||_2e_1) =x_0 + P_i z_i$
with $P_i = V_iU_i^{-1}$,       $z_i = L_i^{-1}(||r_0||_2e_1)$

observe:
$P_i = [P_{i-1}, p_i]$ $z_i = \begin{bmatrix}z_{i-1}\\\zeta _{i}\end{bmatrix}$ 

short reccurrence: $p_i = \frac{1}{d_i}(v_i - b_i p_i)$, $\zeta_i = -c_i \zeta_{i-1}$

=>$x_i = x_0 + P_iz_i = x_0 + P_{i-1}z_{i-1} + \zeta_i p_i = x_{i-1} + \zeta_i p_i$

=> Direct Lanczos (D-Lanczos)

if allow $p_i$ to scale and compensate for the scaling in the constant factor
$x_i = x_{i-1} + \alpha_{i-1}p_{i-1}$,      $r_i = r_{i-1} - \alpha_{i-1} Ap_{i-1}$,        $p_i = r_i + \beta_{i-1}p_{i-1}$

derive orthogonality of $r_i$ proof: for $i \neq j$: $r_i ^Tr_j = 0$
for $i= 0$, $r_0 = ||r_0||_2v_1$
for $i>0$:
$r_i = b-Ax_i = b- A(x_0 + V_iy_i) = r_0 - AV_iy_i 0 r_0 - V_{i+1}\tilde{H}_iy_i = r_0 - V_iH_iy_i - h_{i+1,i}(e_i^Ty_i)v_{i+1}$
$= ||r_0||_2v_1 - V_i(||r_0||_2e_1)-h_{i+1,i}(e_i^Ty_i)v_{i+1} = -h_{i+1,i}(e_i^Ty_i)v_{i+1}$.

conjugacy of $p_i$ proof: for $i \neq j$: $p_i^TAp_j = 0$
$\Longleftarrow$ proof $P_i^TAP_i$ is diagonal
$P_i^TAP_i = U_i^{-T}V_i^TAV_iU_i^{-1} = U_i ^{-T}H_iU_i^{-1} = U_i^{-T}L_iU_iU_i^{-1} = U_i^{-T}L_i$
is symmetric and lower triangular simultaneously therefore diagonal.


(for conjugate Gradient)
derive $\alpha_i$ and $\beta_i$ with respect to $p_i$:
because $r_i$ orthogonality: $r_{i+1}^Tr_i = (r_i-\alpha Ap_i)^Tr_i = 0$
$\Longrightarrow$ $\alpha_i = \frac{r_i^Tr_i}{r_i^TAp_i}$ $= \frac{r_i^T r_i}{(p_i-\beta_{i-1} p_{i-1})^T Ap_i}$ $= \frac{r_i^Tr_i}{p_i^TAp_i}$

because $p_i$ conjugacy: $p_{i+1}^TAp_i = (r_{i+1} + \beta_ip_i)^TAp_i = 0$
$\beta_i = -\frac{r_{i+1}^TAp_i}{p_i^TAp_i} = -\frac{r_{i+1}^T(r_i-r_{i+1})}{\alpha_i p_i^TAp_i}$ $= - \frac{r_{i+1}^Tr_{i+1}}{r_i^T r_i}$ 

[[CG-type algorithms to solve symmetric matrix equations]]


(for conjugate residual)
derive $\alpha_i$ and $\beta_i$ with respect to $p_i$:
because $r_i$ orthogonality: $r_{i+1}^Tr_i = (r_i-\alpha Ap_i)^Tr_i = 0$
$\Longrightarrow$ $\alpha_i = \frac{r_i^Tr_i}{r_i^TAp_i}$  ... $= \frac{r_i^TAr_i}{(Ap_i)^TAp_i}$  

and
$\Longrightarrow$ $\beta = -\frac{r_{i+1}^TAp_i}{p_i^TAp_i}$ ... $= \frac{r_{i+1}Ar_{i+1}}{r_k^TAr_k}$ 




What I have to proof: 
Assume D-Lanczos
If coefficiant matrix is symmetric, and we have A