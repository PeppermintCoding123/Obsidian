[[Perspective Projection 3D]]
$$M_{frustum} = \begin{pmatrix}\frac{2n}{r - l} & 0&\frac{r+l}{r-l} & 0\\
0& \frac{2n}{t - b}&\frac{t+b}{t-b} & 0\\
0&0& -\frac{n}{f-n} & -\frac{fn}{f-n}\\
0&0&-1&0
\end{pmatrix}$$

![[Pasted image 20260324140027.png]]

[[Computer Graphics - overview.canvas]]
[[CG Viewing & Perspective]]