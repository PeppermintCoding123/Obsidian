https://www.sciencedirect.com/science/article/pii/S0377042715000370
- comparring diffarent methords
#### 1 Introduction
combination of direct method lower-upper triangular and the orthogonal-triangular factorizations and itterative methods with matrix-splitting or krylov-subspaces

#### 2 direct Methods
Gram rule:
$A_j = [a_1,...,a_{j-1},b,a_{j+1}, a_n]$ for $j \in (1,...,n)$ 
the jth element $x_*^{[j]}$ of the solution $x_*$ is given by:
$$x_*^{[j]} = \frac{det(A_j)}{det(A)}$$
cost = $\mathcal{O} (n^2n!)$ 
for special Matricies better Times and diffarent formulations with LU and  Cholesky factorization 
#### 3 Itterative Methods
construct:
$x_1 \in span (b), x_2 \in span(b, Ab), ... , x_k \in span(b, Ab, ..., A^{k-1}b)$  with $\lim_{k \rightarrow + \infty} x_k = x_*$ 

linear subspace, the kth [[7.2 Krylov subspace]] : $K_k(A,b) = span(b, Ab, ..., A^{k-1}b)$ 

##### i) why do we use a Krylov subspace to construct an iterative method?
-  [Richardson extrapolation](https://www.sciencedirect.com/topics/mathematics/richardson-extrapolation "Learn more about Richardson extrapolation from ScienceDirect's AI-generated Topic Pages") iteration
-  through the minimum-degree polynomial of A
	- Really good explanation

##### ii) how good an approximate solution is contained in a Krylov subspace?
- symetric
- diagonalizable
- nonsymmetric and non-diagonalizable - further reading
- "how a good approximation from the Krylov subspace can be computed with a moderate amount of work and storage"
	- compute Orthonormal basis for krylov, with Gram Schmidt or Arnoldi
#NumEigNumerischeEigenwerte 

#TODO das in Warum gute Approx inkorperieren