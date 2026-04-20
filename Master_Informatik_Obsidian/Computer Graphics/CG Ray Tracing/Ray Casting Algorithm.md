```c++
for each pixel p in image plane
	generate eye ray (e,d) through pixel p
	tmin = infinity; omin = null;
	for each scene object o
		t = intersect ray (e,d) with object 
		if ray intersects object and t < tmin
			tmin = t;
			omin = o;
	if omin != null
		compute lighting at hit point on object omin set p to this color
		set color
	else
		set p to background color
```

[[Computer Graphics - overview.canvas]]