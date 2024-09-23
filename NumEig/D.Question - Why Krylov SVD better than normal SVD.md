[[numpy.linalg.SVD]]
#NumEig #KrylovSubspace 

=> Der Fehler: Ich hatte vergessen die Werte in S zu Quadrieren

Acttion Plan: 
1. Implement an alternative to SVD for solving eigenvalue approximations
	1. QR Algorithm
	2. Lanczos someting
2. Go search in source code for a reason....

Posibilities:
1. I use np.random.rand(n,n) to generate the matrix, meaning they all have values in range(0,1). 
	- If I scale this by 100 and then mabey the orthogonalisation is not so close to the (1,...,1) vector used in Gram-Schmidt
2. The Orthogonalization Stretches the space in the direction of the biggest Eigenvector
	- If I look at the error for the last Eigenpair, the result is different...
	- Also, I should get a simmilar result for QR and any other used method.
