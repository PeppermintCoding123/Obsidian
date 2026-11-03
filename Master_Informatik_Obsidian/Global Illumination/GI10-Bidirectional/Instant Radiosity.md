= early example of [[Many Lights Method]]
– generate many light paths
– each vertex of these <span style="color:rgb(238, 0, 255)">paths becomes an indirect light source</span>
– render scene with this <span style="color:rgb(238, 0, 255)">indirect light source</span>
	→ using OpenGL and shadow maps
	→ very efficient
– average all these images

=> <span style="color:rgb(238, 0, 255)">Plane [[Rasterisation]]</span>
render scene from point of light source
=> everything visible = vsible in shadow map
![[Pasted image 20260911115022.png]]

[[Global Illumination - overview.canvas]]