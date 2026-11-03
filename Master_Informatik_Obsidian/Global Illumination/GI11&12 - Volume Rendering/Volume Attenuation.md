$\mathcal{V}$ = Volume = bounded region in space
$\mu$ = dencitywithin the colume
- stored in voxel grid or procedurally

$e^{- \mu d}$ = attenuated light travelig through constant dencity $\mu$ by distance $d$ 
= probapility of light getting through the distance

$$\tau(x_0,x_1) = \int_{x_0}^{x_1} \mu(x) dx$$
= Optical Thickness
$1-O(x_0, x_1) = T(x_0, x_1) = e^{- \tau(x_0, x_1)}$
#Question if this equation is correct

### Numerical Integration
τ=0
for (x = x0; x < x1; x += d)
	τ += μ(x) * d
return exp(−τ)

[[Global Illumination - overview.canvas]]