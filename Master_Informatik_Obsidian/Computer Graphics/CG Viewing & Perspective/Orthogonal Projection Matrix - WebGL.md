[[Orthographic Projection 3D]]

image window defined by $(l = x_{min}, r= x_{max}, b = y_{min}, t = y_{max})$

$n = z_{min}$
$f = z_{max}$


$$M_{crop} = \begin{pmatrix}\frac{2}{r - l} & 0&0&-\frac{r+l}{r-l}\\
0& \frac{2}{t - b}&0&-\frac{t+b}{t-b} \\
0&0& \color{red}{\frac{1}{n-f}} & -\frac{n}{f-n}\\
0&0&0&1
\end{pmatrix}$$
![[Pasted image 20260324132118.png]]