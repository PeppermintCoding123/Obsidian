https://www.youtube.com/watch?v=YeS4gvu4EhI
#NumEig 

choose $b$ arbitrarily
$q_1 = b/||b||_2$, $q_2,...,q_k$ be known
for $k$ = 1,2,3,... do
	$q_k =Aq_{k-1}$
	for $j$ = 1,2,...,m do
		$h_{j,k-1} = q_j^tq_k$
		$q_k=q_k-h_{j,k-1}q_j$
	end 
	$h_{k+1,k} = ||q_k||_2$
	$q_{k+1} = q_k/h_{k+1,k} = 1$
end

$H_k$ is the projection of $A$ onto Krylov space.
[[Figure 7.7 - procedure Arnoldi iteration]]

```
import numpy as np  
from numpy import linalg as LA # import linear aögebra  
from numpy.linalg import inv  
  
  
def arnoldi_iteration(A, b, n: int):  
"""Computes a basis of the (n+1)-Krylov subspace of A: the space spanned by {a,Ab,...,A^nb}.  
  
Arguments:  
A: mxm array  
b: initial vector {lenth m}  
n: dimention of Krylov subspace, must be >= 1  
  
Returns:  
Q: mx(n+1) array, the colums are an orthogonal basis of the Krylov subspace.  
h: (n+1)xn array, A on basis Q. It is upper Hessenberg"""  
  
print("A", A)  
m = A.shape[0]  
h = np.zeros((n + 1, n))  
Q = np.zeros((m, n + 1))  
q = b / np.linalg.norm(b) # Normalize the input vector  
print("q", q)  
Q[:, 0] = q.transpose() # Use it as the first Krylov vector  
  
for k in range(n):  
print("-------------------")  
print("k", k)  
v = np.dot(A, q) # Generate a new candidate vector  
print("v", v)  
for j in range(k + 1): # Subtract the projection on previous vectors  
h[j, k] = np.dot(Q[:, j].conj(), v)  
print("h[j,k]", h[j, k])  
print("Q[:,j]", Q[:, j])  
temp = v.transpose() - h[j, k] * Q[:, j]  
v = temp.transpose()  
print("v", v)  
h[k + 1, k] = np.linalg.norm(v)  
eps = 1e-12 # if v is shorter than this threshold it is the zero vector  
if h[k + 1, k] > eps: # Add the produced vector to thr list, unless the zero vector is produced  
q = v / h[k + 1, k]  
print("q", q)  
Q[:, k + 1] = q.transpose()  
else: # If zero, stop iterating.  
return Q, h  
return Q, h  
  
if __name__ == "__main__":  
A = np.array([[1, 1, 1, 3, 1], [1, 4, 1, 3, 1], [2, 1, 1, 3, 1], [2, 2, 1, 3, 4], [1, 2, 1, 4, 1]])  
b = np.array([[1], [2], [3], [1], [2]])  
Q, h = arnoldi_iteration(A, b, 3)  
print("Q", Q)  
print("h", h)  
Hk = np.dot(np.dot(Q.transpose(), A),Q)  
print("Hk", Hk)  
  
uh, vh = LA.eig(Hk)  
print("uh", uh)  
print("vh", vh)  
  
u, v = LA.eig(A)  
print("u", u)  
print("v", v)
```

Unbekannte Befehle:
.conj() - conjugiert?
numpy.linalg.inv  - infinity?

=> [[GMRES]] to solve $Ax=b$, to find a vector $x_k$ that minimizes $||b-Ax_k||$ (Ab 7:20 im Video)

#### Extentions
[[Figure 7.8 - procedure Lanczos iteration]]
Lanczos for Symmetric matricies
no j loop and quicker v


 [[CG - conjugate gradient]]
for symetric positive definite matricies - positive real eigenvalues
understand the connection between Krylov and [[CG - conjugate gradient]]

[[Preconditioning]]
find neareby problem, that can solve the problem much faster
$P^{-1}Ax=P^{-1}b$ instead of $Ax=b$
- Jacobi: $P$ = diagonal matrix
- Gaus-Scheidel: $P$ = triangular matrix
- Incomplete LU\LR: $P$ = $L_0U_0$
- Multigrid Method: $P$ = same difference matrix as $A$ but on a coarser grid


Kaczmaz Iteration
exponentially fast convergence - just one row of the system
stocastic gradient decent methods
