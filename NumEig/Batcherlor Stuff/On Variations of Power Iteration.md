See PDF
https://link.springer.com/chapter/10.1007/11550907_24
#NumEig [[power itteration - Praktische Verfahren der Gleichungsauflösung]]

A generall way to implement Power, verry grob

For $C\in\mathbb{R}^{m\times m}$ symmetric matrix with real eigenvalues
$w(0)$ is nonzero vector
$w(t)$ its itterative updates

$\widetilde{w} (t+1) = Cw(t)$
$w(t+1) = \frac{\widetilde{w}(t+1)}{||\widetilde{w}(t+1)||_2}$   (Euklidean norm)
updating rule:
$w(t+1)=Cw(t)[w^T(t)C^2w(t)]^{-1/2}$

=> $w(t)$ converges to the eigenvector of the maximum eigenvalue of $C$.

# Subspace Itteration
is a direct generalisation of power itteration for computing multiple eigenvectors.