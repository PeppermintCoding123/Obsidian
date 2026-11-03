# Algorithm - [[Illumination Integral - Direct Light]]

function L(x, ωout )
	Lsum = (0,0,0);
	for i = 1 to n
		ω = sampleHemiSphere (i)                                // sample hemisphere
		y = ray(x, ω)                                                          // cast ray
		Lsum += Le (y,- ω) * dot(N(x), ω)                      // take radiance at hit point
	return Lsum * 2 * PI / n;
# [[Direct Illumination Area Light]]
function directSampleHemi(x, ωout )
	Lsum = (0,0,0);
	for i = 1 to n
		ω = sampleHemiSphere (i)
		y = ray(x, ω)
		<span style="color:rgb(255, 192, 0)">if</span>(<span style="color:rgb(255, 192, 0)">y is on light source</span>)
			Lsum += Le (y,- ω) * dot(N(x), ω)
	return Lsum * 2 * PI / n;


[[Global Illumination - overview.canvas]]
[[03 - GI- Direct Illumination]]