#NumEig 
Laplace is (0,...,0,-4,1,-4,0,...,0)
umgekerte Laplace is (-1,4,-1) in den Haupt & nebendiagonalen.

Toeplitz-Matrix is a correct name, but laplace-matrix is a generel name for Matricies with a specific structure, but not specifically those....

# mit umgekehrter (-1,4,-1):
withought we do have overflows.
This matrix is verry illconditioned, since for 100 itterations we can get e3 and e-150 in the same vectoram
At this point I can not thing´k of anything that would work on thsi


# mit richtig rum:
weil nicht positiv definit haben wir fast geraden verlauf, und one regulator überläufe bei dimension 330, da dann e+305 oder größer.
![[Laplace with regulator.png]]