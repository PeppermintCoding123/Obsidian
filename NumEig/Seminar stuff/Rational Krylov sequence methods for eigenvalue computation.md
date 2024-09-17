https://www.sciencedirect.com/science/article/pii/0024379584902210
#### Intro
- [[Krylov Subspace]]
- "$K^j$ is space of polynomials of the matrix acting at the starting vector" 
#### Krylov Method
 compute $x_{j+1}= Ax_j$ with  $j = 1,2,...$
 $X_j = [x_1,x_2,...,x_j]$
 Assumption: Vectors become linearly dependant at $p \leq n$ 
- $x_{p+1} = Ax_p = x_1c_1 + ... + x_pc_p = X_pc$ 
 $AX_p = [Ax_1, ..., Ax_p] = [x_2,.., X_pc] = X_p F_{pp}$ 
 $F_{pp}=\begin{bmatrix}0 & 0 & ... & c_1 \\ 1 & 0 & ... & c_2 \\ 0 & 1 & ... & c_3 \\ 0 & 0 & ... & c_p \end{bmatrix}$ is Forbenius Matrix of order $p \times p$
 Eigenvalues of $F$ are subset of Eigenvalues of $A$ 
 $F$ Charactaristic polynomial:
- $XF_{pp}(\lambda) = \lambda ^p - c_p \lambda ^{p-1} - c_{p-1} \lambda ^{p-2} - ... - c_1$  
- not possible to determine p precicely numerically
- but a residual: $r_{p+1} = Ax_p - X_p c$ 
- differance: $r_{p+1}e^T_p = \begin{bmatrix}0 & 0 & ... & p_1 \\ \vdots & \vdots &  & \vdots \\ 0 & 0 & ... & p_n \end{bmatrix}$ 
- such that $AX_p - X_p F_{pp} = r_{p+1}e^T_p$ 
- => Eigenvalues of F are approximations of Eigenvalues of A

 - $(\mu, s)$ = Eigenpair of F: $Fs=s\mu$ , $\mu$ approx Eigenvalue
	 - $y = X_ps$
	 - $y$ approx Eigenvector of A
	 - residual: $Ay-y\mu = AX_ps-X_pF_s = (AX_p - X_pF)s = r_{p+1}e^T_ps = r_{p+1}s(p)$
- determine $c_i$ such that $\min_{r_{p+1}}$ 
	- as least squares problem solution: $r_{p+1} = Ax_p - X_p c$ 
	- => $X_p ^H r_{p+1} = 0$ 
	- residual is orthogonal to the subspace spanned by $X_p$


Ritz-Pair is entirely determined by $span(X_p)$ and direction of $r_{p+1}$ => Choose different Basis
 - Arnoldi [[Figure 7.7 - procedure Arnoldi iteration]]
	- apply orthogonalization prosess at every step j
	- => Hesseberg matrix $H_{pp}$ instead of $F_{pp}$ : $H_{pp}=\begin{bmatrix}h_{11} & h_{12} & ... & h_{1p} \\ h_{21} & h_{22} & ... & h_{2p}\\ 0 & h_{32} & ... & h_{3p} \\ \vdots & \vdots & & \vdots \\ 0 & 0 & ... & h_{pp} \end{bmatrix}$ 
- [[Figure 7.8 - procedure Lanczos iteration]]
		- If A symmetric:
		- $H_{pp} = X_p^HAX_p$ , $H_{pp}^H = X_p^HA^HX_p = H_{pp}$ 

#### Polynomials of A
every vector in Krylov written as Polynomial:
- $y \in K^j(A,x_1) = {x_1,...,x_j}$ 
- $y = X_jc = \eta (A)x_1$ 
- $\eta(\lambda) = c_j\lambda^{j-1} + c_{j-1}\lambda^{j-2} + ... + c1$ 

#### Actual Practical stuff
Implement Methods of Krylov
(3) [[The spectral transformation Lanczos method for the numerical solution of large sparse generalized symmetric eigenvalue problems,]]
(10) [[Lanczos versus subspace iteration for solution of eigenvalue problems]]
(18) [[The advantages of inverted operators in Rayleigh-Ritz approximations]]

(12) [[Rayleigh quotient iteration - B. N. Parlett, The Symmetric Eigenualue Problem, Prentice-Hall, Englewood Cliffs, N.J., 1980.]]
- Further on Lanczos


