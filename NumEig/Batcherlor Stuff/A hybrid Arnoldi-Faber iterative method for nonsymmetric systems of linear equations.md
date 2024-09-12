https://link.springer.com/article/10.1007/BF01388688

Begind with #ArnoldiIteration Arnoldi & then Richardson iterative method based on Faber polynomials
konverges
 is approximately as fast or faster than the hybrid GMRES or restarted versions of the GMRES algorithm
 sensative to amount from Arnoldi

#### 1. Introduction
$Ax=b$ large sparce real nonsymmetric and nonsingular system of linear equasions
start with iterative method & swich to parameter-dependend method
usually
Eigenvalue-Info by modified [[power itteration]] or #ArnoldiIteration 
second phase with Chebyshev iteration, second-order Richardson iteration 
Hybrid [[GMRES]]

Here:
Arnoldi for a few itterations
construct Polygon $\Omega$ contains all eigenvalue estimates 
compute Farber polynomials from $\Omega$ from Schwarz-Christoffel formula 
Farber polynomials of degree $m$ applied to last GMRES iterate as Richardson iteration
Arnoldi/GMRES -> eigenvalue estimates -> polygon -> Faber polynomials -> Richardson iteration

reason: restarting GMRES has too slow convergence
kondition: $z=0 \not\in \Omega$=> $A$ dose not have both negative and positive eigenvalues. 
Faber polynomials are a generalisation of Chebycheff polynomials

#TODO some good papers to discover suff highlited pink
(36) [[CGS, A Fast Lanczos-Type Solver for Nonsymmetric Linear systems]]
(40) [[A comparison of the successive overrelaxation method and semi-iterative methods using Chebyshev polynomials]]
(10) [[A hybrid Chebyshev Krylov subspace algorithm for solving nonsymmetric systems of linear equations]]
(26) [[A hybrid GMRES algorithm for nonsym- metric matrix iterations.]]


#### 2. Outline of the hybrid Arnoldi-Faber method
start with an indepth explanation of [[GMRES]] (really good explanation, when confused)

explain construction $\Omega$
$\Lambda := (\lambda_j)_{j=1}^m$
$\Omega^+$ = complex hull of $\Lambda^+:=\{\lambda_j\in\Lambda:Im(\lambda_j)\geq 0\} \cup \{Re(\lambda_j):\lambda_j\in \Lambda\}$
$\Omega := \{z\in\mathbb{C}:z\in\Omega^* \wedge \overline{z}\in\Omega^+\}$
...
It is not worth my time to read thrue everything here, since it is at a Level where I am not.

#### 5. implemetation details
$A\in\mathbb{R}^{N\times N}$
$l$ = average number elements in row of $A$ => matrix vector multiplication costs $l$ vector operations

$x_{new} = x_{old} + q_{m-1}(A)r_{old}$ (5.1)
use recurrence relations instead of fully computation $\tilde{F}_m(z)$:
$x_1:=1/c_0 r_{old} + x_{old}$
$x_j := -(F_{j-1}(0)r_{j-1} + \sum_{i=0}^{j-2} c_(i)F_{j-1-i}(0)x_{j-1-i} + jc_{j-1}x_{old})/(c\cdot F_j(0))$
...
this requires $F_i(0)$ and right now I wolud rather look at other procects that I can implement.
