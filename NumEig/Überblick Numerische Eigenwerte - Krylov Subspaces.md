#NumEig
#KrylovSubspace
#ArnoldiIteration
#LanczosAlgorithm
#### [[7.2 Krylov subspace]] 
- spezielle Orthogonalisierung
- Solve Problem in smaller space and project back
#### Creating Orthogonal Vectors:
- [[Gram-Schmidt procedure for vectors v1, .... , vm in F^n]]
	- give vectors/ matrix (A)
- [[Figure 7.7 - procedure Arnoldi iteration]] 
	- Gram Schmidt with spesifick extra vektor & cooler strukture of resulting projected Matrix $H_k$
- [[Figure 7.8 - procedure Lanczos iteration]]
	- Arnoldi for SPD
	- - [[New implementations of Lanczos method]]

#### Solve Eigenvalue problem
- known Methods... SVD,...
#TODO test some other methods
- [[The Restarted Arnoldi Method Applied to Iterative Linear System Solvers for the Computation of Rightmost Eigenvalues]]


#### Solve linear System Problem
[[Question - What other linear solvers with Krylov exist]]
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

[[ToDo - Die wichtigsten Fragen - NumEig]]
