= applying Box filter at different Levels & adding this
Level 0 = 1x1
Level 1 = 2x2
Level 2 = 4x4
...

Texel (texture pixel) size may not be smaller than pixel
at rendering time: 
- determine p = ratio between pixel and texture size
- Mipmaplevel: $L = \log_1p+L_{bias}$
- $L_{bias}$ chosen for blur, dependant on texture
![[Pasted image 20260214161512.png]]
[[trilinear interpolation]]
= interpolate between 3 levels of MIP-Map = trilinear


# Pixel Footprint
= choose footpfint, that covers 1 Pixel
![[Pasted image 20260214161751.png]]

![[Pasted image 20260404145407.png]]

# Anisotropic Filtering
= Pixel Footprint for strange shapes
![[Pasted image 20260214161841.png]]

[[Computer Graphics - overview.canvas]]
[[Image-Filtering]]