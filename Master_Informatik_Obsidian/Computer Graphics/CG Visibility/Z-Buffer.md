For each Pixel store depth & color of closes Object
```c++
setpixel(x, y, depth, color)
	if(zBuffer(x,y) > depth)
		screen(x,y) = color
		zBuffer(x,y) = depth
```
- orderindependant - no pre-sort
$z\in [0, 1]$
Depth = lenth of Projection onto main line