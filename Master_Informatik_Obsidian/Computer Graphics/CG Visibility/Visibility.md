
[[Occlusion - Painter's Algorithm]]
[[Z-Buffer]]
[[Polygon Offset]]
[[Back Face Culling]]

### Transparency
##### Approach a) (correct)
- sort objects back to front (**no Z-Buffer**)
##### Approach b) (correct)
- render opaque objects with z-buffer
- “freeze” z-buffer (set to read-only)
- sort transparent objects & render back to front
##### Approach c) (faster, but not always correct)
- render opaque objects
- “freeze” z-buffer
- render transparent objects without sorting
##### [[Depth Peeling]]

Aliasing
- [[SSAA - Super Sample Anti-Aliasing]]
- [[Alpha-Based Antialiazing]]