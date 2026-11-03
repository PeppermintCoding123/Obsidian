#Question what ieactly is this?
replace $L_e$ by $L_{direct}$ , i.e. for each path vertex compute direct light

= follow each ray via multiple indirect bounces, but at each
bounce, compute the direct lighting from light source surfaces

At each bounce, use light source sampling to get direct illumination
- Light source sampling to project light source onto hemisphere
Sample the BRDF to create direction for collecting indirect light
- Importance sampling of the hemisphere via the BRDF to generate
next direction to collect potential indirect light from next hit point
![[Pasted image 20260926132844.png]]

[[Global Illumination - overview.canvas]]