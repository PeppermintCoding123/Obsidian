Given : planar polygon with $m$ vertices $p_1, ..., p_m$ on 1 plane with normal $n$
##### 1.Ray Polygon intersection
Ray: $e + td$
polygon: $p = e + \frac{s-n\times e}{n\times d} d$

##### 2. Test if $p$ lies in polygon
- project polygon and $p$ onto coordinate plane with largest projection
- do 2D inside-out test

###### [[Inside-Outside test]]
- generate point in arbritary direction
- count intersection with polxgon boundary
	- Even: outside
	- Odd: inside
	- If hit vertex, use other ray
![[Pasted image 20260402164552.png]]

[[Object Intersection - Ray]]
[[Computer Graphics - overview.canvas]]