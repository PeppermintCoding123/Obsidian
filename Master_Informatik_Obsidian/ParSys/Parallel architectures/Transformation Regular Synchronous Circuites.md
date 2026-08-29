$$\begin{pmatrix}C' \\ D'\end{pmatrix} = \begin{pmatrix}E & 0 \\ \Gamma & \Lambda\end{pmatrix} \begin{pmatrix}C \\ D\end{pmatrix} 
\Longleftrightarrow
C' = C \wedge
D' = \Gamma \cdot C + \Lambda \cdot D
$$
$C' = C \in \mathbb{Z}^{|V| \times |A|}$ => keep functionality / not add or remove edges
$\Gamma = (\gamma(1) \cdots \gamma(|V|))\in \mathbb{Z}^{(m+1) \times |V|}$ = retiming transformation in the m-dimensional graph
$\mathcal{I}_i ' = \{I'| I' = \Lambda I + \gamma(i), I\in \mathcal{I}_i\}$
$\Lambda$ = Linear (multiplicative) transformation

![[Pasted image 20260707091634.png]]
If transformation restricted to registers
$$\begin{pmatrix}C' \\ \overline{V}' \\ d'\end{pmatrix} = \begin{pmatrix}E & 0 & 0\\0& E& 0\\ \gamma & \pi & c\end{pmatrix} \begin{pmatrix}C \\ \overline{V} \\ d\end{pmatrix}$$
$\overline{V}$ = spacial direction = interconnect / Space
$d$ = time direction
$D = \begin{pmatrix}\overline{V} \\ d\end{pmatrix}$


[[Regular Synchronous curcuit]]