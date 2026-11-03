- Large Memory requirements - streaming
- Loading textures takes the longest Time
# => Ray frot traversal
- compute all intersections of eye rays (first ray front, traversal phase)
- shade all hit points (shading phase, generates new secondary rays)
-  continue iteration with new secondary rays

- rays in 1 bucket ahve simmilar starting point & only see part of cene in memory
- Hit points sorted by FaceID & TextureID => load textures 1x and shade all corresponding hit points
![[Pasted image 20260911094518.png]]

[[Global Illumination - overview.canvas]]