= remove backfacing triangles

### Version 1
- normal to each face, pointing outward
- render if $v \cdot n > 0$
	- $v$ = face to eye
	- $n$ = normal of plane

![[Pasted image 20260324164611.png]]
### Version 2
1. given points $a, b, c$
2. Lift to 3D: $a \rightarrow (a_1, a_2, 0), ...$
3. $p = b-a$, $q = c-a$
4. abc counterclockwise $\Leftrightarrow (p\times q)[3] > 0$

![[Pasted image 20260324165558.png]]