https://epubs.siam.org/doi/abs/10.1137/0712047
[C. C. Paige](https://epubs.siam.org/doi/abs/10.1137/0712047#con1) and [M. A. Saunders](https://epubs.siam.org/doi/abs/10.1137/0712047#con2)
see PDF
#NumEig 

For $A$ = symmetric but indefinite.
based on Lanczos.

#### 1. Introduction
best konwn [[CG - conjugate gradient]] (2)
- breaks down for $A$ indefinite symmetric matrix

#### 2. General theory
Same as [[7.4 Arnoldi iteration]]
Notation: 
$V_k$ span $\mathcal{R}(A)$ (the subspace)

#### 3. The Lanczos vectors.
(description of Lanczos) [[7.5 Symmetric Lanczos algorithm]]
Notation: 
$T_k = V_k^TAV_k$, $V_k^Tb = \beta_1e_1$

#### 4. Derivation of the conjugate gradients method from the Lanczos process.
(method of conjugat gradient developed)
for $A$ = pos def => $T_k = V_k^TAV_k$ is also pos def => Cholesky factorisation:
$T_k = L_kD_kL_k^T$   with $D_k$ = diagonal with positive elements. $L_k$ is unit lower bidiagonal (developed)
$y_k$ changes fully with each inkrease of $k$. 
=>
$p_k = L_k^Ty_k$, $C_k = V_kL_k^{-1}$ =>
$L_kD_kp_k = \beta_1 e_1$, $x_k^c = C_kp_k$

columns of $C_k$ by solving: $L_kC_k^T=V_k^T$
rows of $C_k$: $x_k^c=C_kp_k$
$C_k$ columns are $A$-conjugate since:  $C_k^TAC_k = L_k^{-1}T_kL_k^{-T} = D_k$ 

(3)
this methos is mathematically equivallent to [[CG - conjugate gradient]]
just unneccacary normalisation and 

#### 5. [[SYMMLQ]] - An algorithm for indefinite symmetric systems.
(This dose not really minimize, but keeps the orthogonal versions of before? https://netlib.org/linalg/html_templates/node25.html)
if $A$ indefinite => $T_k = V_k^TAV_k$, not always existent. => need stable method

$T_k = \overline{L}_kQ_k$, $Q_k^TQ_k = I$    -> $\overline{L}_k$ = is lover triangular, differs from $\overline{L}_{k+1}$ only in the $k,k$ element ($Q_k$ ist das neue element.)
def:
$\overline{W}_k = [w_1,...,w_{k-1},\overline{w}_k] = V_kQ_k^T$
$\overline{z}_k = (\zeta_1,...,zeta_{k-1},\overline{zeta}_k)^T = Q_ky_k$
=> 
$\overline{L}_k\overline{z}_k = \beta_1e_1$
$x_k^c = \overline{W}_k\overline{z}_k$
gives mathematically same solution as conjugate Gradient, but factorisation is numerically stable even for indefinite $T_k$

Get $T_k = \overline{L}_kQ_k$ with:
$T_kQ_{1,2}\dots Q_{k-1,k} = T_kQ_k^T = \overline{L}_k$

....
basically do a small change in the way $L_k$ is constructed in comparison to $\overline{L}_k$ that results in better conditioning and stable functions
=> $x_k^c$ and $x_k^L$ are bouth calculated in each itteration and then the algorithm desides which hase smaller residual...


#### 6. MINRES - minimal residual method
This is just how it is derived, not how to implement it...
$V_k^TA^2V_k = T_k^2 + \beta_{k+1}^2e_ke_k^T$
$V_k^TAb = \beta_1V_k^TAv_1 = \beta_1V_k^TAv_1 = \beta T_ke_1$
$T_k^2+\beta_{k+1}^2e_ke_k^T = \overline{L}_k\overline{L}_k^T+\beta_{k+1}^2e_ke_k^T = L_kL_k^T$
$L_kL_k^Tu_k = \beta_1\overline{L}_kQ_ke_1$
$\overline{L}_k = L_kD_k$
$D_k = diag(1,1,...,1,c_k)$
$L_k^Tu_k = \beta_1D_kQ_ke_1 = (\tau_1,..,\tau_k)^T = t_k$
$\tau_1 = \beta_1c_1$
$\tau_i = \beta_1s_1s_2 \dots s_{i-1}c_i \quad \forall i = 2,\dots,k$
$M_k = [m_1,...,m_k] = V_kL_k^{-T}$
$x_k^M = V_ku_k = V_kL_k^{-T}L_k^Tu_k = M_kt_k$






----
I dont like the way they write their Algorithms, so I searched for a typed out version:
https://en.wikipedia.org/wiki/Minimal_residual_method

First you choose $x_0\in\mathbb{R}^n$  arbitrary and compute
$r_{0} =b-Ax_{0}$
$p_{0} =r_{0}$
$s_{0}=Ap_{0}$
Then we iterate for $k=1,2,\dots$  in the following steps:
	 Compute $x_{k},r_{k}$ through
    $\alpha _{k-1}={\frac {\langle r_{k-1},s_{k-1}\rangle }{\langle s_{k-1},s_{k-1}\rangle }}$
    $x_{k}=x_{k-1}+\alpha _{k-1}p_{k-1}$
	 $r_{k}=r_{k-1}-\alpha _{k-1}s_{k-1}$
     if $\|r_{k}\|$ is smaller than a specified tolerance, the algorithm is interrupted with the approximate solution $x_{k}$
     Otherwise, a new descent direction $p_{k}$ is calculated through
     $p_{k}\leftarrow s_{k-1}$
    $s_{k}\leftarrow As_{k-1}$ 
- for $l=1,2$ (the step $l=2$ is not carried out in the first iteration step) calculate:
	$\beta _{k,l}={\frac {\langle s_{k},s_{k-l}\rangle }{\langle s_{k-l},s_{k-l}\rangle }}$
	$p_{k}\leftarrow p_{k}-\beta _{k,l}p_{k-l}$
	$s_{k}\leftarrow s_{k}-\beta _{k,l}s_{k-l}$
---
