point on image plane:
$$e + w + xu + yv$$

aspect: with / height
image plane: $(x, y) \in [-x_m, x_m]\times[-y_m, y_m]$
$y_m = tan(\frac{fovy}{2}), \quad x_m = aspect \; y_m$
map integer pixel coordinates $(i,j)$ to window:
$n_x$ = number of pixels in $x$-direction
$x = \left (\frac{i + 0.5}{n_x} \times 2 - 1\right)x_m, \quad  y = \left (\frac{j + 0.5}{n_y} \times 2 - 1\right)y_m$

$$
\color{Peach} x = \left (\frac{i + 0.5}{n_x} \cdot 2 - 1\right)\cdot aspect \cdot \tan(\frac{fovy}{2})
$$
$$\color{Peach} y = \left (\frac{j + 0.5}{n_y} \cdot 2 - 1\right)\cdot \tan(\frac{fovy}{2})$$
$$\color{Peach}  d = \frac{w + xu + yv}{||w + xu + yv||}$$
![[Pasted image 20260402154931.png]]

[[Eye Ray]]
[[Object Intersection - Ray]]
[[Computer Graphics - overview.canvas]]