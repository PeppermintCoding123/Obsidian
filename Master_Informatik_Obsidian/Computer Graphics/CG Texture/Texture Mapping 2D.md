- Texture Image size $(n_x, n_y)$
- assighn every vertex $(x, y, z)$ to a texture coordingate $(s,t)$ or $(u,v)$ on object
- interpolate texture coordinate within triangle

# For Rasterized Triangles
- not linear interolation
- use perspectively correct interpolation
![[Pasted image 20260214140117.png]]

# Equasions:
in World-Space
$$\begin{pmatrix}x\\ z\end{pmatrix} = \begin{pmatrix}x_1\\ z_1\end{pmatrix} + s\begin{pmatrix}x_1 -x_1\\ z_2-z_1\end{pmatrix}$$
in Image Space
$$x' = \frac{x_1}{z_1} + s'(\frac{x_2}{z_2}-\frac{x_1}{z_2})$$
$$s = \frac{s'z_1}{s'z_1+(1-s')z_2}$$
![[Pasted image 20260214142900.png]]

Also for arbitrary Arbutuses $A$ along line:
$$A(s) = A_1 + s(A_2-A_1)= \frac{\frac{A_1}{z_1}+s'\left(\frac{A_2}{z_2} - \frac{A_1}{z_1}\right)}{\frac{1}{z_1}+s'\left(\frac{1}{z_2} - \frac{1}{z_1}\right)}$$
![[Pasted image 20260214143619.png]]
