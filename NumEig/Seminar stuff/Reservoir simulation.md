http://www.ipt.ntnu.no/~curtis/courses/Reservoir-Recovery/2018-TPG4150/Handouts/Simulation/2009-SPE-Simulation-Chapter-Coats-etal(optional).pdf

[[7.2 Krylov subspace]]
Page 7:
The Idear:
- spanned by vectors p(A)b - polynomial that approximates $A^{-1}b$ 
- common methords for construction is [[Orthomin]] and [[GMRES]]
	- methords: minimize residule norm over all vectors in $span(x, Ax, A^2x, ... , A^{m-1}x)$ 
	- give same results
- [[Preconditioning]]
	- transform matrix to be easier to solve
	- $M$ approximates $A$
	- Solve preconditioned System: $AM^{-1}y=b$, where $x = M^{-1}y$
	- 