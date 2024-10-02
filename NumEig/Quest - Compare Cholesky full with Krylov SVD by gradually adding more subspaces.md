#NumEig 
Cholesky ist nicht für Eigenwerte, aber:
$A\cdot x = \lambda \cdot x \Leftrightarrow A\cdot x = \lambda E \cdot x \Leftrightarrow (\lambda E - A) \cdot x = 0$

https://de.wikipedia.org/wiki/Cholesky-Zerlegung

Bestimme Determinante:
$det(A)= \prod_{i=1}^n G_{ii}^2$
Cholesky:
$A = LDL^T$ = $LD^{1/2} (D^{1/2})^T L^T$ = $LD^{1/2} (LD^{1/2} )^T = GG^T$ 


=> wie hängt die Gaußsche Normalengleichung  $A^TA\hat{x}=A^Tb$ mit den Eigenpaaren zusammen?