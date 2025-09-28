Goal: estimate Depth of points on low contras Structures
- setup with camera & projector

# Active Image aquisition
1. add Projector => generate Patterns to find correspondences
2. Replace camera with projector

- only find points in 1 image, since we already know where it is in the projector-image
- ![[Pasted image 20250922150707.png]]

#### Single point projection
#### Line
- depth for all points on line - correspondence 
- illuminated with known parts
- structured light = main source of illumination
- shape distorts pattern
- camera captures distorted part

#### Triangulation with light Plane
![[Pasted image 20250922152303.png]]
$Ax + By+ Cz + D = 0$ = Light Plane
$x = x'zf, \quad y = y'z/f$ = projected points
$$z = \frac{-Df}{Ax'+By'+Cf}$$

### Binary Coding Idea
$(2^n -1)$ stripes in n images
-> identify points in time space

### not destroy colour
#### Kinect Infra red
- send infra red light
- Windwo based normalized cross-correlation

#### Kinect Time of Flight - TOF
- send light & measure when it arrives 
- ![[Pasted image 20250922154253.png]]

### LiDAR
- most done with Stereo reconstruction & a art doen with lidar for depth
#ComputerVision [[Computer Vision]] [[CV11 - Surface Reconstruction]]