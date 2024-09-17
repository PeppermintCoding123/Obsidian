https://www.ams.org/journals/mcom/1981-37-155/S0025-5718-1981-0616364-6/S0025-5718-1981-0616364-6.pdf

#NumEig 
methods generalizing [[CG - conjugate gradient]] to unsymmetric systems = extentions on #ArnoldiIteration for solving Eigenvalue Problems

#### Introduction
some: 
- solve $A^HAx=A^Hb$ normal equasion or some other preconditioning
	- sensitive to $A^HA$ conditioning, wich is worse than $A$
- [[Chebyshef Itteration]] not the same drawback, but need computation of Eigenvalues of A
- [[CG - conjugate gradient]] solve symmetric linear systems
	- projection process onto Krylov subspace with $r_0$ = initial residual vector
- (5) generalisation by splitting $A$ into symmetric and skrew-symetric parts
here:
- generalize CG as projection process
- 2. theoretical Krylov
- 3. Arnoldi-like Methods
- 4. convergence 5. numerics

#### 2. The Krylov Subspace Methods-Theoretical Aspects
repeating Krylov & Arnoldi
$Ax^{(m)}-b \bot v_j$  $\forall j = 1,...,m$
$x^{(m)} = V_m \cdot y^{(m)}$
$V_m^HAV_m\cdot y^{(m)}-V_m^Hb = 0$ with $V_m^H =  \overline{V}_m^T$

Let $\pi_m$ = Orthogonal Projection onto Krylov space
$\pi_m(Ax^{(m)}-b)=0$
note: $x^{(m)}$ is solution: $Ax^{(m)}-b=0$ and $b\in\mathcal{K}_m:x^{(m)}b = b$
Error: $||(I-\pi_m)x^*||$ between exact solution and Krylov subspace

Diffarent way of defining Error, because bad for unsymmetric matricies (Proposition 2.1)
...

##### 2.2 Krylov Subspace Methods
initial residual: $r_0 = b-Ax_0$
$x = x_0+z$ ->$Az-r_0 = 0$ (Lösungs $z$)
A Krylov subspace method = any method that approximates $z^{(m)}$ by applying a projection process to $Az-r_0 = 0$ onto the Krylov subspase $\mathcal{K}_m$.
$z^{(m)}= V_my^{(m)}$ 
$x^{(m)} = x_0 +z^{(m)}$
$V_m^HAV_my^{(m)}-V_m^Hr_0 = 0$

#### 3. Practical Methods
##### adaptation of Arnoldi's method - Algorithm3.1
$r_0 = b-Ax_0$
$v_1 = r_0 /||r_0||$
for k until m:
	$h_{ik} = (Av_k,v_i)$
	$w = Av_k - \sum_{i=1}^k h_{ik}v_i$
	$h_{k+1,k} = ||w||$
	$v_{k+1} = w/h_{k+1,k}$

obvious: $V_m^Hr_0 = \beta V_m^Hv_1 = \beta e_1$  with $\beta = ||r_0||$
Hessenbergmatrix: $H_m = V_m^HAV_m$
$H_my^{(m)}= \beta e_1$
$x^{(m)} = x_0 +z^{(m)}$
$z^{(m)}=\beta V_m H_m^{-1}e_1$
$||b-Ax^{(m)}|| = h_{m+1,m}|e_m^Hy^{(m)}|$
$AV_m = V_mH_m+h_{m+1,m}v_{m+1}e_m^H$

practical implement: 
generate $V_k$ &$H_k$  for $k = 1,...,m,...$ to estimate $h_{m+1,m}|e_m^Hy^{(m)}|$ and stop when small enought.


##### 3.2. Iterative Arnoldi Method.
restart the algorithm with $x_0$ replaced by $x^{(m)}$.
description...

Hessenberg becomes Tridiagonal 
...
#TODO Page 7...
espessially 
##### Algorithm 3.4
