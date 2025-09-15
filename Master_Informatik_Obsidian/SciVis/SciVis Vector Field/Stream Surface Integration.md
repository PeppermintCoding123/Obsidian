<span style="color:rgb(0, 176, 80)">seed line</span>
$s= const$ = streamlines
$t= const$ = <span style="color:rgb(255, 221, 0)">timelines</span>
on Parametric surface $\mathbf{s}(s,t):$ $$\frac{\partial \mathbf{s}(s,t)}{\partial t} = \mathbf{v}(\mathbf{s}(s,t))$$
![[Drawing StreamSurface.excalidraw]]
### Strategies for inserting new vertices:
- between 2 current vertices
- between corresponding vertices at seeding structure & integrate them

### Solution: Small angle problem
= stream lines & time lines intersect at small angle => degenerate
- Error for perpendicularity [[Error Function - Stream Surface Integration]]
- timelines as orthogonal to streamlines => orthogonal front-lies
- => [[Hultquist Algorithm]]

#SciVis #VectorField 
