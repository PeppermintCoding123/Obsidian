= interpolate colors from polygon vertices

using [[Barycentric Coordinates]] of point p
$p = \alpha a + \beta b + \gamma c$

linear interpolation of colors
$col_p = \alpha col_a + \beta col_b + \gamma col_c$

#### Algorithmically
1. linear interpolation along edges
2. then interpolate with [[Scanline Algorithm]] along lines
![[Pasted image 20260324112503.png]]
