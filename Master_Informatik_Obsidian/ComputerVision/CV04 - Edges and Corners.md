# Edges
## How to identify
- scan line & plot function => 1 derivative => where most negative
- ![[Drawing Characterizing edges.excalidraw]]
- Very susceptible to noise => blur by [[Convolution]] with Gaussian & then 1. derivative 
#### $\frac{d}{dx} (f*g)= f*\frac{d}{dx} g$
= Derivative theorem of convolution
- convolve Gaussian & 1 derivative 
- Gaussian with different size kernel => Edges at different scales
#OtherLecture [[Gaussian Blur]]

#### Design Edge-detector
1. <span style="color:rgb(255, 133, 133)">Good detection</span> => find all real edges  & ignore noise & artifacts
2. <span style="color:rgb(255, 133, 133)">Good localisation</span> => close to true edges, return 1 point only

- gradient magnitude correlates where people see edges

## Canny Edge Detector
=> first derivative of Gaussian closely approximates the operator that optimizes the product of signal-to-noise ratio and localization

1. Filter image with <span style="color:rgb(255, 133, 133)">x, y derivatives</span> of Gaussian
2. Find <span style="color:rgb(255, 133, 133)">magnitude and orientation </span>of gradient
	1. $\sqrt{ \partial X_{Gaussian} ^2 + \partial Y_{Gaussian} ^2 }= gradient magnitude$
	2. $\arctan(g_y, g_x) =  \theta$ = Orientation
3. <span style="color:rgb(255, 133, 133)">Non-maximum suppression</span> - Fat to 1 pixel wide edges
	1. If on pixel that is not jet maximum => walk forward & back in direction of gradient
4. <span style="color:rgb(255, 133, 133)">Hysteresis thresholding</span>
	1. 2 thresholds: 
		1. grad mag > high threshold => strong edge
		2. grad mag < low edge => noise
	2. make week edges between strong edges strong
	3. ignore independence

# Corner Detection
## invariant local features
- repeatable points - invariant to transformation - detect same points independently 
- **Descriptor** = the environment

1. <span style="color:rgb(255, 133, 133)">Detection</span> - find set of distinct key points
2. <span style="color:rgb(255, 133, 133)">Descriptor</span> - extract feature descriptor as vector
3. <span style="color:rgb(255, 133, 133)">Matching </span>- distance between feature vectors to find correspondence

## Corner Detection by Auto-correlation
- corner have large change in all directions
### $E(u,v)= \sum_{x,y} w(x, y)[I(x+u, y+v)-I(x, y)]^2$
w = window function (weight)
I(x+u, y+v) = Shifted intensity
I(x, y) = Intensity
![[Pasted image 20250919183936.png]]
=> describe as quadratic shape with high curvature
=> 2. Order Taylor
$E(u,v) \approx_{Taylor} E(0,0)+ [u\; v] \begin{bmatrix} E_u(0,0)\\ E_v(0,0)\end{bmatrix}+ \frac{1}{2}[u\;v]\begin{bmatrix} E_{uu}(0,0) & E_{uv}(0,0)\\ E_{vu}(0,0)& E_{vv}(0,0)\end{bmatrix}]\begin{bmatrix} u\\ v\end{bmatrix}$
Only need Extrema
$E(u,v) \approx_{Taylor} [u\;v]\begin{bmatrix} E_{uu}(0,0) & E_{uv}(0,0)\\ E_{vu}(0,0)& E_{vv}(0,0)\end{bmatrix}]\begin{bmatrix} u\\ v\end{bmatrix}$
$M = \begin{bmatrix} E_{uu}(0,0) & E_{uv}(0,0)\\ E_{vu}(0,0)& E_{vv}(0,0)\end{bmatrix} = \sum_{x, y} w(x,y)\begin{bmatrix} I_x ^2 & I_x I_y\\ I_yI_x& I_y^2\end{bmatrix} = \sum \nabla I (\nabla I)^T$
$I_x$ = Vertical changes 
$I_y$ = horizontal changes
$I_xI_y$= get corners=> where strong horizontal & vertical structures

### $E(u,v) \approx \begin{bmatrix} u& v\end{bmatrix}M\begin{bmatrix} u\\ v\end{bmatrix}$, $M =  \sum_{x, y} w(x,y)\begin{bmatrix} I_x ^2 & I_x I_y\\ I_xI_y& I_y^2\end{bmatrix}$
Interpreting M - second moment Matrix
=> Inverse Eigenvalues of Matrix = Lengths of direction of change
![[Pasted image 20250919192012.png]]- eigenvalue analysis to get inverse scale of matrix
- <span style="color:rgb(255, 133, 133)">small elipse = large change</span>
- <span style="color:rgb(255, 133, 133)">round elipse = large change in all directions = corner</span> (unique in respect to surrounding)

### $C = \det(M)-\alpha \; \text{trace}(M)^2$
= cornerness of given pixel

### Harris Corner Detector
1. Compute image derivatives ($I_x, I_y$)
2. Compute  M components as squares of derivative $M =  \sum_{x, y} w(x,y)\begin{bmatrix} I_x ^2 & I_x I_y\\ I_xI_y& I_y^2\end{bmatrix}$
3. Gaussian filter g() with width σ 
4. Compute cornerness $C = \det(M)-\alpha \, \text{trace}(M)^2$
5. Threshold $C$ to pick high corners
6. Non-Maxima supression to pick peaks

### Properties:
<span style="color:rgb(255, 133, 133)">Invariance: </span>image is transformed and corner locations do not change
- use derivatives => invariance intencity shift
<span style="color:rgb(255, 133, 133)">Covariance:</span> if we have two transformed versions of the same image, features should be detected in corresponding locations
- translation - position changes in accordance with translation
- rotation
- Not  covariant to scaling

# [[Gamma]]
- SRGB - colour intencity not linear
- CRT - color with power function $I ∝ V^\gamma$
- black => larger amount of colours, light => less colors
<span style="color:rgb(255, 133, 133)">linear RGB</span>
- convert 0-255 to 0-1 and take everything to power of 2.2, calculate average & then reapply gamma again
- $x \text{Linear} = x^y \text{sRGB}$

[[CV05 - Features-Cameras-Optics-Perspective]]
CV - [[Computer Vision]] #ComputerVision