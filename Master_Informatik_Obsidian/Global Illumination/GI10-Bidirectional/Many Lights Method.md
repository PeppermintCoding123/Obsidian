= [[Bidirectional Path Tracing]] but <span style="color:rgb(238, 0, 255)">reuse light paths</span>
- precompute light paths 
- => vertices become indirect light sources
- use many of them

=>
#### less variance
- range of values in sample position - less of that means that they are closer together.
#### bias - indirect light concentrated in point sources
stair artefacts in shadows
point light source verry visible if on edge
![[Pasted image 20260911114607.png]]
=>  solution: replace by larger area lights
→ more complex lighting computation

[[Global Illumination - overview.canvas]]