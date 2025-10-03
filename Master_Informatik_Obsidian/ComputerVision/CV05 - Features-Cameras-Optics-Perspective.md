# 05.1 - Feature Matching
## Feature 
- invariance => transformation dose not change corner
- covariance => if transform 2 versions of image => features detected in corresponding locations
- Harris . invariant to affine intencity change, Covariance to rotation, translation, but not to scaling
=> look at patch size

## Detection
### laplacian scale
= 2 derivative of Gaussian => inverted maxican Hat
- Filter image with different scale
- for each feature look at it in larger & smaller scale
	- If local maxima in its region => identified its scale
- Large kernels

### Cascading of Gaussian kernel properties
- convolve with 2 Gaussian, instead of 2. Derivative
![[Pasted image 20250920163516.png]]
1. Blur image with σ Gaussian kernel
2. Blur image with kσ Gaussian kernel
3. Subtract 2. from 1.

## Descriptors
- histogram - invariant to rotation

### SIFT (Invariant Feature Transform)
1. Compute local histograms of oriented gradients
2. Find Difference of Gaussian scale-space extrema (for target scale) (Build pyramid & find local maxima)
3. Post-processing (position interpolation, Discard low-contrast points, Eliminate points along edge)
4. Orientation estimation
	1. Compute Histogram
	2. Select dominant $\theta$
	3. Normalize to fixed orientation
	4. ![[Pasted image 20250920162508.png]]
5. Descriptor extraction
	1. Image gradients in 8 bin histogram
	2. 128 dim feature vector
	3. scale magnitudes by Gaussian before adding
	4. ![[Pasted image 20250920162522.png]]


Ideal descriptor: Robust and Distinctive & Compact and Efficient

## Matching
## feature Matching
1. compute distance in feature space
2. Match point to lowest distance
3. ignore anything higher than threshold

##### Problems:
- threshold hard to pick
- Non-distinct / repetitive

#### Nearest Neighbor Distance Ratio
$\frac{NN1}{NN2} \approx 1$ =>  matches too close
$\frac{NN1}{NN2} \approx 0$ => matches distinct enough
- sort by ratio
- ratio threshold depend on application

# 05.2 Camera & Optics
- problem which happens when removing 2. Dimension -> length estimation, closeness

### Projected geometry
![[Pasted image 20250920174627.png]]
- length & area are lost
- foreshortening - length & Area
- Angles

### Homogeneous Coordinates $(x, y, w)$
w = distance projector to surface
=> now transform extra dimension with matrices
#### Converting to Homogeneous coordinates
=> adding 1 for w:
$$(x, y) \Rightarrow \begin{bmatrix}x \\ y\\ 1\end{bmatrix}, \quad (x, y, z) \Rightarrow \begin{bmatrix}x\\ y\\ z \\1\end{bmatrix}$$
#### Converting from Homogeneous to Cartesian
divide by $w$
$$\begin{bmatrix}x \\ y\\ w\end{bmatrix} \Rightarrow (\frac{x}{w}, \frac{y}{w}), \quad  \begin{bmatrix}x\\ y\\ z \\ w\end{bmatrix} \Rightarrow (\frac{x}{w}, \frac{y}{w}, \frac{z}{w})$$
#### Properties
- Scale invariance
- Duality between lines & points
- Intersect paralell lines

### $\mathbf{x} = \mathbf{K}[\mathbf{R\; t}]\mathbf{X}$
= Camera Projection matrix
x: Image Coordinates: (u,v,1)
K: Intrinsic Matrix (3x3)
R: Rotation (3x3)
t: Translation (3x1)
X: World Coordinates: (X,Y,Z,1)
$[\mathbf{R\; t}]$ = Extrinsic Matrix
=>
#### $w \begin{bmatrix}u \\ v\\ 1\end{bmatrix} = \begin{bmatrix}f_x & s & {u}_0 \\ 0 & f_y & {v}_0 \\ 0 & 0 & 1\end{bmatrix}\begin{bmatrix}r_{11} & r_{12} & r_{13} & t_x \\ r_{21} & r_{22} & r_{23} & t_y \\ r_{31} & r_{32} & r_{33} & t_z\end{bmatrix}\begin{bmatrix}x \\ y \\ z \\ 1\end{bmatrix}$
![[Intrinsic Camera Properties]]

![[Extrinsic Camera Properties]]

##### Perspective Projection
Orthographic projection
- Distance between Camera optical plane & image plane = infinite => parallel projection (x, y, z views)
$$w \begin{bmatrix}u \\ v\\ 1\end{bmatrix} = \begin{bmatrix}1 & 0 & 0 & 0 \\ 0 & 1 &0 & 0\\ 0 & 0 & 0 & 1\end{bmatrix}\begin{bmatrix}x \\ y \\ z \\ 1\end{bmatrix}$$
##### Scaled ortographic projection
- Object dimensions are small compared to distance to camera
$$w \begin{bmatrix}u \\ v\\ 1\end{bmatrix} = \begin{bmatrix}f & 0 & 0 & 0 \\ 0 & f &0 & 0\\ 0 & 0 & 0 & s\end{bmatrix}\begin{bmatrix}x \\ y \\ z \\ 1\end{bmatrix}$$
# 05.3 SVD
## $A=U \Sigma V ^T$
A = m x n => m to bottom (rows) & n to right (columns)
U = m x n
$\Sigma$ = n x n
$V$ = n x n
$U^T U = V V^T = I$

$A \cdot V= U \Sigma$

Solving $Ax = b$ => $x = V \Sigma ^{-1} U ^T b$


CV - [[Computer Vision]] #ComputerVision 
[[CV06 - Camera Calibration]]