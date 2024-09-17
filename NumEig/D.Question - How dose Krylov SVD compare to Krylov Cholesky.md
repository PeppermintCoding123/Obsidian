#NumEig 
[[Krylov Subspace]]

lstsq and Cholesky in Krylov space have abought the same accuracy.
lstsq is slightly faster than Cholesky at solving in the subspace. 
however Cholesky seems to be minimally better (e^-6 size better)
The issue is that When transforming into a smaller space, the resulting matrix looses some propperties, so it seems that Cholesky often dose not work any more, since the resulting Matrix is not SPD.
see [[Question - What matrix-properties are retained by transformation into smaller space?]]



For this implement a Krylov with Cholesky insted of SVD
Used this reafference: 
https://en.wikipedia.org/wiki/Cholesky_decomposition
Also in your numerik 1 Script
=> Cholesky oficually only works on SPD-Matricies

And this for code: https://docs.scipy.org/doc/scipy/reference/generated/scipy.linalg.solve_triangular.html

I have finally fixed the lstsq code. 
I need to implement the Cholesky version.
I need to fix Gram-Schmidt process #TODO
- Try Wiki code for this: https://en.wikipedia.org/wiki/Gram%E2%80%93Schmidt_process
- The error was a neccaary transposition
