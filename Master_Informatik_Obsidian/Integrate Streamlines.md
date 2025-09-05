# Analytical in Linear Vector Field
$\mathrm{v(x)= J \cdot x}$
spectral decomposition of [[Jacobian Matrix Vector Field]] $\mathrm{J = E\cdot D \cdot E^{-1}}$

[[EW]]
$det(J-\lambda I) = 0$
Ordnung $\lambda_1 \leq \lambda_2$

[[EV]]:
$$\mathrm{E} =\begin{pmatrix}|&|\\
v_1 & v_2\\ |&|\end{pmatrix}$$
mit  $(\mathrm{J} - \lambda I)v = 0$


streamline of $\mathrm{v}$ starting at $x_0$:
$$c(t)= \mathrm{E} \cdot \begin{pmatrix}e^{\lambda_1 t} & 0 & 0 \\
0 & e^{\lambda_2 t}& 0 \\
0 & 0& e^{\lambda_2 t}\end{pmatrix} 
\cdot \mathrm{E}^{-1} \cdot x_0$$
