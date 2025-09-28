
Projection matrsix
page 29 formular imortant

#### What happens
p. 32 - every point can be written as a linear ray between camera center & point
23 - Hompgrophy => there esist a linear transformation when turning a point

Backprojection 34 bring point back to the world-point => produce those points 
- C is also on Backprojection ray
- Backproject Planes into lines into space

35 ff
1. Row = 1 coordinate of image point - u = P1Tx => all points in 3D space that map to u = 0 => v axix 
2. Row of projection matrix => v = 0 => contain Camera center & u axix
3. Row = any u, any v & pointa at infinity, if projection ray never intersect image
	1. same parralel direction as camera center => Hauptebene
	2. P31, P32, P33 tell direction where camera is looking => see if other camera is looking in same direction by checking if they have thes coordinates (up to scale) as the same
	3. => **Principle** point know where camera center is located
Depth = distance to principle plane, not the point C
- m = hessian normal from principle plane in last row of projection matrix => have mottom 3 elements as unit lenth, not just the bottom right!!! => better stability

p.44 Epipolar Geometry
- invariance in space - projected to same image , we do not know how close
2 Cameras 
- tip of cone has to be on backprojection line
- => tip also has to be on the projection of that ray => Epipolar line
- lines on a plane 
![[Pasted image 20250924221740.png]]
- camera centers in 3D& 1 World Point => plane
- Epipolar lines = intersection of that plane with the images (image planes)
- <span style="color:rgb(24, 203, 21)">Stereo Baseline B</span> 
- Epipoles = e1 & e0 - number to what image it belongs 

###### Epipolar constraint: 
The epipolar line contains the corresponding image point: $x_1 ^\bot l_1=0$
![[Pasted image 20250924222125.png]]
### <span style="color:rgb(24, 203, 21)">Fundamental Matrix</span>
= The green arrow
Encode all this geometry in matrix
=> how to get line, where x1 is supposed to be
map point to line by multiplying point & matrix

- Transpose of first is the teh one for the opposite direction herleitung

FM maps points to line
=> x1 has to be on the line
right & left nullspaces = epipoles - p.90
=> F matrix has to have rank 2.

=> Summery p. 91 => the important stuff

### Algebreic Estimation of funcamental Matrix
Assume we have teh corresponding points already
- by estimating => not F with rank 2 
- minimize by setting \sigma_3 = 0 
- = 8 Point Algorithms


#### Rectification
- Homography to distort image with keeping the epipolar lines
- = transform thatprinciple planes (lower 3 coordinates of projection matrix are the same)
- ![[Pasted image 20250924223655.png]]
- project other camera center onto image plane

#ComputerVision [[Computer Vision]] [[CV08 - Dense Motion Estimation]]
