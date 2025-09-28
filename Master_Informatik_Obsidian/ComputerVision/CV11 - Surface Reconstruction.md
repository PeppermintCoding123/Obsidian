- located points in space into 3D surface

# CV 11- Surface reconstruction 1/2
- Range map = Depth map
- range = depth
- multiple range maps
1. Find out how range maps fit together
	- partial overlap
	- 
2. given the point-cloud hwo can we make it into 1 closed surface?

## Alignment = Registration

### Coarse Alighnment
- give 3 Points & computer dose rest
- ![[Pasted image 20250924144153.png]]
#### LSTSQ
Minimise sum of squared distances of corresponding points
<span style="color:rgb(112, 155, 255)"><b>Procrustes</b></span>
= calculate mean of all points & bring these 2 Points to correspondence


### Fine Alignment
- gitterry map of who is in front = **Depth-fighting**

#### <span style="color:rgb(112, 155, 255)">Iterative Closest Points (ICP) </span>
1. Nearest Point are on other curve $(p_i, q_i)$
	- fast nearest nieghbour .> aproximative neares nehghbour
2. then Procrustes
$min_{r,t} \sum_i ||p_i - (Rq_i+t)||^2$
![[Pasted image 20250924144940.png]]

#### for what points?
##### uniformly random? 
-  samples don't cover important geometric features
##### Normal space sampling
- sample that normal are uniformly distributed
-  Get normal: approx k-nearest neighbour, then fit plane on them & get the normal from that
-  ![[Pasted image 20250924145744.png]]
##### Closest point on tangent plane of closest point
-  planar approximation => better correspondences
-  ![[Pasted image 20250924150009.png]]
##### Outliers
- point-correspondencies
- distances between point-pairs & throw away half
- weighted for those in extreme curvature/ extrema ...
- ![[Pasted image 20250924150525.png]]

##### partial range scans
- large regions without correspondance 
- ignore points that are too far away
- ![[Pasted image 20250924150654.png]]

# CV 11 - Surface Reconstruction 2/2
- throw away what point stems from what scan it is from
- Keep normals !!! - on what side of object is the object

### 3D mesh
- locally / piece wise linear surface - model as triangle
- courser / less dense than original
- approximate but not interpolate (avoid outliers & too many triangles)

### Implicit functions
- like $f(x,y) = x^2 + y^2 -r ^2$
- find 0-set for edge
#### Surrface Representation with Iso-line = 0
- martching squares
- marching cubes - 15 configurations

=> turn into triangle mesch & use marching cubes to get inside & outside

## How to get implicit function from point cloud?

### Hoppe
When evaluating signed distance function at p:
1.  find closest Point q with normal n
2. =>compute distance to tangent plane of q:
	- $f(p) = (q-p)\cdot n$
- evaluate on uniform grid
- run marching cubes
- ![[Pasted image 20250924154209.png]]
![[Pasted image 20250924160248.png]]
![[Pasted image 20250924160257.png]]
### Unity Implicit
- weighted by weight to the other points as well
- distance $d_i = (x_i-p)\cdot n$
$$f(p) = \frac{\sum_i w(||x_i-p||d_i)}{\sum_i w(||x_i-p||)}$$

### Variants
- only partial reconstruction (without a back)
- Voxel volume
	- Paint pieces of a sighned distance function into the volume - for the other values we do not know
	- average when next volume is added
- Kinekt Fusion
	- take camera & walk around object on 1 PC run ICP
	- Integrate onto joined voxel volume