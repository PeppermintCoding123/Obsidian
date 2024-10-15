https://www.mat.uc.pt/~alma/aulas/CV_PhD/Books/Krylov.pdf

#NumEig #TODO [[GMRES]] [[CR - Relaxationsmethoden bester Strategie zur losung linearer Gleichungssystems,]] [[CG - conjugate gradient]] #ArnoldiIteration 

#TODO: Schreibe die Herleitung für beide Kapitel in EIgene Worte auf.
# 3.1.2 CR from CG
$A$ is Hermetian positive definite. $\Longrightarrow$ $\exists \sqrt{A}$ with Cholesky factorisation: $A = LL^H$ and SVD: $A = LL^H = (U\Sigma V^H)(V \Sigma U^H) = U \Sigma^2 U^H = (U\Sigma U^H)(U \Sigma U^H) = A^{1/2}A^{1/2}$.
Show that for $A$ = Hermetian positive definite, then obtain CR from CG with: $A\tilde{x} = A^{1/2}b$,  $\tilde{x} = A^{1/2}x$
from CG new phrasing:
$\tilde{p}_n = \tilde{r}_n + \beta_{n-1} \tilde{p}_{n-1}$
$\alpha_n = \frac{\langle\tilde{r}_n, \tilde{r}_n\rangle }{\langle \tilde{p}_n, A\tilde{p}_n\rangle}$
$\tilde{x}_{n+1} = \tilde{x}_n + \alpha_n\tilde{p}_n$
$\tilde{r}_{n+1} = \tilde{r}_n - \alpha_nA\tilde{p}_n$
$\beta_n = \frac{\langle\tilde{r}_{n+1}, \tilde{r}_{n+1}\rangle}{\langle \tilde{r}_n, \tilde{r}_n\rangle}$
residual vector of origional system: $Ax = b$: $r_n = b-Ax_n$ 
residual of this system: $\tilde{r}_n  = A^{1/2}b - A \tilde{x}_n = A^{1/2}(b-Ax_n) = A^{1/2}r_n$
Set $\tilde{r}_n = A^{1/2}r_n$,   $\tilde{p}_n = A^{1/2}p_n$,    $\tilde{x}_n = A^{1/2}x_n$ into algorithm above:

CR method:
Input: $x_0 \in \mathbb{C}, \beta_{-1} = 0, p_{-1} = 0, r_0 = b-Ax_0$
output $x_n$
for $n = 0,1,2,...$ until convergence:
	$p_n = r_n + \beta_{n-1}p_{n-1}$
	$Ap_n = Ar_n + \beta_{n-1} Ap_{n-1}$ 
	$\alpha_n = \frac{\langle r_n, Ar_n\rangle}{\langle Ap_n, Ap_n \rangle}$
	$x_{n+1} = x_n + \alpha_np_n$
	$r_{n+1} = r_n + \alpha_nAp_n$
	$\beta_n = \frac{\langle r_{n+1}, Ar_{n+1}\rangle}{\langle r_n, Ar_n\rangle}$
end

if $\langle r_n, Ar_n \rangle = 0$ CR breaks down if Hermetian matrix is indefinite.

by induction show for CR: $\langle r_i, Ar_j\rangle = 0 \forall i\neq j$  and $\langle Ap_i, Ap_j\rangle = 0 \forall i\neq j$  
in comparrison to CG: $\langle r_i, r_j\rangle = 0 \forall i\neq j$ and $\langle p_i, Ap_j\rangle = 0 \forall i\neq j$ (proposition 3.1)

CR findes approximate solutions such that $x_n = x_0 + z_n, \quad z_n \in \mathcal{K}_n(A,r_0)$
with $z_n$ determied by $r_n \perp A\mathcal{K}_n(A,r_0) := \mathcal{K}_n(A,Ar_0)$ $\Longleftrightarrow$ $x_n = x_0 + V_ny_n, y_n \in \mathbb{C}^n$



or 
	(((3.2.1)
	COCG method (note: $\langle \overline{a},b \rangle = a^Tb$)
	Input: $x_0 \in \mathbb{C}, \beta_{-1} = 0, p_{-1} = 0, r_0 = b-Ax_0$
	Output: $x_n$
	for $n = 0,1,2,...$ until convergence:
		$p_n = r_n + \beta_{n-1}p_{n-1}$
		$\alpha_n = \frac{\langle \overline{r}_n, Ar_n\rangle}{\langle \overline{p}_n, Ap_n \rangle}$
		$x_{n+1} = x_n + \alpha_n p_n$
		$r_{n+1} = r_n + \alpha_nAp_n$
		$\beta_n = \frac{\langle overline{r}_{n+1}, r_{n+1}\rangle}{\langle \overline{r}_n, r_n\rangle}$
	end
	
	residual vector satisfies: $r_p \perp \overline{\mathcal{K}_n(A,r_0)}:= \mathcal{K}_n(\overline{A}, \overline{r}_0)$ ))

# 3.2.2 COCR
by restricting the derivation of the COCR method for complex symmetric linear systems to that for real symmetric ones we can derive CR with GMRES

The above COCG method can be derived by CR with $\langle a, b \rangle = \langle \overline{a}, b \rangle$
COCR is the same as CR if $A$  is real symmetric.


Not worth the effort to understand this, exept if tenbrink explicetly states its neccacary.