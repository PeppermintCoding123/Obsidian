= Physically-based BRDF ,model
$$f_r = \frac{DGF}{\pi \cos(\theta_i) \cos(\theta_o)}$$
#### $D$ = Distribution of microscopic normal directions = routhness
$$D = \frac{e{-[(\tan\beta)/m]^2}}{4m^2 \cos^4 \beta}$$
![[Drawing 2025-09-28 Beckmann distribution.excalidraw]]
m = roughness
#### $G$ = Geometric - self-shadowing
$$G = min\left \{ 1, \frac{2(n\cdot h)(n\cdot v)}{(v\cdot h)}, \frac{2(n\cdot h)(n\cdot l)}{(v\cdot h)}\right \}$$
= What proportion of Bounce off surface Ratio rof radiance & irradiance
![[Pasted image 20250928163128.png]]
#### $F$ = Frenel term
= Reflection from an ideal smooth surface  
=> most surfaces reflect more strongly near grazing angles
![[Pasted image 20250928164021.png]]
### Micro Facet Theory
- in microscopic scale, many mirrors reflect in diffarent directions

#Radiometry [[CPaC_Overveiw.canvas|CPaC_Overveiw]]