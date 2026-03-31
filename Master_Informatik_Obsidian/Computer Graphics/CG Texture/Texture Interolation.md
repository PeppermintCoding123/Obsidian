= how to handle coordinates in between pixel positions?

[[Nearest Neighbor Interpolation]]
$$c(s, t) = c_{\lfloor sn_x\rfloor, \lfloor tn_y\rfloor}$$
![[Pasted image 20260214153625.png]]
[[Bilinear Interpolation]]
$s' = sn_x - \lfloor sn_x\rfloor; t' = tn_y - \lfloor tny\rfloor$
$$c(s,t) = (1-s')(1-t')c_{i, j} + s'(1-t')c_{i+1, j}+(1-s')t'c_{i, j+1}+s't'c_{i+1, j+1}$$
![[Pasted image 20260214154958.png]]

=> texture minification

[[Computer Graphics - overview.canvas]]
[[Texture Mapping 2D]]