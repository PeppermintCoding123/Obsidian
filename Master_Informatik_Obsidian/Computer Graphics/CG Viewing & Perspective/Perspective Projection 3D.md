#### Process or projection a point
$\begin{pmatrix}x\\ y\\ z\end{pmatrix} \rightarrow \begin{pmatrix}x\\ y\\ z\\ 1\end{pmatrix} \underrightarrow{\cdot M}\begin{pmatrix}x\\ y\\ z\\ z\end{pmatrix} \underrightarrow{: z} \begin{pmatrix}x/z \\ y/z\\ 1\end{pmatrix}$

$$M_{perspective} = \begin{pmatrix}1&0&0&0\\0&1&0&0\\0&0&1&-1\\0&0&1&0\end{pmatrix}$$
$$M_{crop} = \begin{pmatrix}\frac{2}{x_{max} - x_{min}} & 0&0&-\frac{x_{max}+x_{min}}{x_{max}-x_{min}}\\
0& \frac{2}{y_{max} - y_{min}}&0&-\frac{y_{max}+y_{min}}{y_{max}-y_{min}} \\
0&0& 1 & 0\\
0&0&0&1
\end{pmatrix}$$
$$M = M_{crop}M_{perspective}$$
mapping $[x_{min}, x_{max}]\times [y_{min},y_{max}] \rightarrow [-1, 1]^2$
- nonlinear z-depth
- infinite view frustum to a box
![[Pasted image 20260324124055.png]]
## Depth Normalization
$$M_{c} = \begin{pmatrix}1&0&0&0\\0&1&0&0\\0&0&-\frac{1}{f-n}&-\frac{n}{f-n}\\0&0&1&0\end{pmatrix}$$


[[Computer Graphics - overview.canvas]]
[[CG Viewing & Perspective]]