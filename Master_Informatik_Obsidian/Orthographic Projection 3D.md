= project onto Image plane in z-direction & crop window
$\begin{pmatrix}x\\ y\\ z\end{pmatrix}\rightarrow \begin{pmatrix}x \\ y\\0\end{pmatrix}$  

$$M = M_{crop}M_{ortho}$$
$$M_{crop} = \begin{pmatrix}\frac{2}{x_{max} - x_{min}} & 0&0&-\frac{x_{max}+x_{min}}{x_{max}-x_{min}}\\
0& \frac{2}{y_{max} - y_{min}}&0&-\frac{y_{max}+y_{min}}{y_{max}-y_{min}} \\
0&0& \frac{1}{z_{max} - z_{min}} & -\frac{z_{min}}{z_{max}-z_{min}}\\
0&0&0&1
\end{pmatrix}$$
$$M_{ortho} = \begin{pmatrix}1&0&0&0\\0&1&0&0\\0&0&1&0\\0&0&0&1\end{pmatrix}$$
$z_{min}$ = [[near]] plane
$z_{max}$ = [[far]] plane
Here: between $[0,1]$

![[Pasted image 20260214175756.png]]