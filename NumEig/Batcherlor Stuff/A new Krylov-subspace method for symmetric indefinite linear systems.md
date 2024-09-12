https://www.osti.gov/biblio/10190810
https://www.osti.gov/servlets/purl/10190810

#### Abstract
In komparrison to [[SYMMLQ]] and [[MINERS]] wich require symetric positive definite Matriesies
for solving symmetric indefinite linear systems => combined with arbritary symmetric precondition
special case of quasi-minimal residual method for general non-Hermitian linear systems
converges quicker as [[SYMMLQ]] and [[MINERS]]

#### Intro
in example: Fiite-difference or finite element approximatoion using stabilised discretisation lead to linear system with symmetric matrix
Standard Conjugate Gradient Methods are [[SYMMLQ]] and [[MINERS]]. 
- based on Lanczos prosess for symetric matrices
- preconditioning Matrix should be pdf itself.
Here: new method can be combined with arbritary symmetric preconditioners
Spesial case of [[QMR quasi-minimal residual]] for general non-Hermetian system

#### 2. QMR Method for Non-Hermitian Linear Systems
##### QMR:
$A$ is $N\times N$ nonsingular, non-Hermetian, $x_0$ is $N$-dim arbritary initial guess,
- $r_0 = b-Ax_0$;  $v_1 = r_0 / ||r_0||$;  $||w_1||_2 = 1$ arbitrary
use look-ahead variant of classical Lanczos to generate 2 sequenses of vectors: $(v_j)_{j=1}^n$, $(w_j)_{j=1}^n$ 
that span $\mathcal{K}_n(A,r_0)  = span\{r_0,Ar_0,...,A^{n-1} r_0\}$ and $\mathcal{K}_n(A^T,w_1)  = span\{w_1,A^Tw_1,...,(A^T)^{n-1} w_1\}$ 
they are block-biorthogonal
Generated reccurrence: 
- $AV_n = V_{n+1}T_n$
, hier $T_n$ is $(n+1)\times n$ and is equal to $\overline{H}_n$ in normal? (upper Hessenberg with full rank n)
left Lanczos vectors: 
- $A^TW_n = W_{n+1}\tilde{T}_n$ 
with $\tilde{T}_n$ also $(n+1)\times n$ upper Hesenberg - Where do we get it from? is it the same?
sequance $x_n \in x_0 + \mathcal{K}_n(A,r_0)$ meaning 
- $x_n = x_0 + V_nz_n$
where $z_n \in \mathbb{C}^n$ is free parameter vector as the unique solution of [[lstsq least-squares]]: 
- $||f_n-T_nz_n||_2 = \min_{z\in\mathbb{C}^n} ||f_n-T_nz||_2$ where $f_n := [||r_0||_2; 0; ...0]^T \in \mathbb{R}^{n+1}$
residual vector of $n$th QMR is given by: 
- $b-Ax_n = V_{n+1}(f_n-T_nz_n)$ 
Characterized by minimization on second factor = quasi-minimal residual

Further thoughts:
- possible replace three-term look-ahead with two-term look-ahead Lanczos (see further reading)
- also non-look-ahead two-term QMR with biconjugate Gradient (BCG) -> QMR-from-BCG

*open questions*:
- why do we need left Lanczos vectors?

#### 3. Simplification of the Lanczos Process
QMR simplifies with $P$ nonsingular matrix
$A^TP = PA$
$w_1 = Pv_1/||Pv_1||_2$
=> replace calculations involving $A^T$ with $P$ calculations

#### 4. The Symmetric QMR Algorithm
Let $A\in \mathbb{R}^{N\times N}$ symmetric indefinite coefficient matrix
$M = M^T \in \mathbb{R}^{N\times N}$ arbitrary nonsingular marix: 
$M = M_1 \cdot M_2 = M_2^TM_1^T = M^T$ with 
solve:
$A'x'=b'$ with $A' = M_1^{-1}AM_2^{-1}$, $x' = M_2x$, $b' = M_1^{-1}b$
set $M_1 = I$ for right and $M_2 = I$ for left preconditioning
Set $P:=M_1^TM_2^-1$ satisfies $A^TP = PA$

##### Algorithm 1. Symmetric QMR without look-ahead
Choose $x_0 \in \mathbb{R}^N$, $M_1$, $M_2$:
$r_0 = b-Ax_0$
$t= M_1^{-1}r_0$
$\tau_0 = ||t||_2$
$q_0 = M_2^{-1}t$
$\vartheta_0 = 0$
$\rho_0 = r_0^Tq_0$
For $n = 1,2,...$ do:
	$t=Aq_{n-1}$
	$\sigma_{n-1} = q_{n-1}^Tt$
	if $\sigma_{n-1} = 0$ : 
		Stop
	$\alpha_{n-1} = \rho_{n-1} / \sigma_{n-1}$
	$r_n = r_{n-1}-\alpha_{n-1}t$

	$t = M_1^{-1}r_n$
	$\vartheta_n = ||t||_2/\tau_{n-1}$
	$c_n = 1/\sqrt{1+\vartheta_n^2}$
	$\tau_n = t_{n-1}\vartheta_n c_n$
	$d_n = c_n^2\vartheta_{n-1}^2d_{n-1}+c_n^2\alpha_{n-1}q_{n-1}$
	$x_n = x_{n-1}+d_n$
	if $x_n$ konverged:
		Stop
	if $\rho_{n-1} = 0$:
		Stop
	$u_n = M_2^{-1}t$
	$\rho_n = r_n^Tu_n$
	$\beta_n = \rho_n/\rho_{n-1}$
	$q_n = u_n + \beta_nq_{n-1}$
	
$r_n$ is BCG residual, not the residual of $x_n,A,b$.

*Schlussgedanken:*
- Algorithmus basiert auf Lanczos mit der Art wie man $d_n$ berechnet 
- ich checke nicht wofür man die Linke seite braucht?
- Wie Wähle ich $M$?