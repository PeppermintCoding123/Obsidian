#NumEig #TODO 
 [[Überblick Numerische Eigenwerte - Krylov Subspaces]]

#### Solve linear System Problem
[[D.Question - What other linear solvers with Krylov exist]]
##### Symmetric Systems
-  [[CG - conjugate gradient]]
	- SPD
- CR - Conjugate residual [[Variational iterative methods for nonsymmetric systems of linear equations]]
	- SPD
- [[MINRES - Solution of Sparse Indefinite Systems of Linear Equations]] 
	- Symmetric but indefinite
##### Nonsymmetric Systems
- minimize
-  [[GMRES]]
	- randome matrix
- [[GCR - generalized conjugate residual method]]
	- positive real $A$ / the symmetric part of $A$ is real
- [[Orthomin]] 
	- the symmetric part of $A$ is real

Still open:
- [[A hybrid Arnoldi-Faber iterative method for nonsymmetric systems of linear equations]]
	- verry complicated
	- #TODO Implement
-  [[A new Krylov-subspace method for symmetric indefinite linear systems]]
	- Arnoldi based
	- #TODO Implement
- [[CGS, A Fast Lanczos-Type Solver for Nonsymmetric Linear systems]]
	- Lanczos Based
	- #TODO Implement
Unsorted
#TODO read & Implement other methods
- [[Generalized conjugate-gradient acceleration of nonsymmetrizable iterative methods]] 
- [[SYMMLQ]] - SPD
-  [[A hybrid Chebyshev Krylov subspace algorithm for solving nonsymmetric systems of linear equations]]
- [[A hybrid GMRES algorithm for nonsymmetric matrix iterations.]]
- [[Arnoldi-based model reduction for fractional order linear systems]]


- [[Krylov Subspace Methods for Solving Large Unsymmetric Linear Systems]] 
	- #TODO: finish reading 
	- simmilar to CG
	- #TODO: Implement


#### Still Relevant
[[Motivations and realizations of Krylov subspace methods for large sparse linear systems]]
[[Rational Krylov sequence methods for eigenvalue computation]]
- read if you want to understand the Polynomial version
- This is a theory-paper that will help a lot with the writing, epesially abought Lanczos & Arnoldi
- See for more Eigenvalue Problem versions



Evalusation:
![[A__H_GCR_K-Orthomin_k-GCR-CR-CG-Krylovlstsq-lstsq_2.png]]
![[A__H_GCR_K-Orthomin_k-GCR-CR-CG-Krylovlstsq-lstsq_2_close-up.png]]

![[A_MINRES-GMRES-Krylovlstsq-lstsq_30.png]]

Speed:

![[S__H_Krylovcholesky-CG-MINRES-GMRES-Krylovlstsq-lstsq_2.png]]
![[S__H_GCR_K-Orthomin_k-GCR-CR-CG-Krylovlstsq-lstsq_2.png]]