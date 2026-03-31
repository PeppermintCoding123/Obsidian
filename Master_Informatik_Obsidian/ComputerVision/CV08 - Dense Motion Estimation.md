=> Estimate Optical flow => how something moves - pixels that move & track where they end up in the next image
- Tells what belongs together => what objects
- How move - ridged / non-ridget
- Shape & depth

### Motion Flow vs. Optical Flow
Apparent motion
- perceivable motion

Aperture problem
- dependent on what parts of thing we see
- Barber pole ilusion

Assume
- parallel to image plane
-  ignores parallax effects (Closer Objects move faster)
- towards camera =  radial optical flow

[[Time-dependent Flow - Integral Surface]]
## Error Metrics
Now: Translations between images 
u = displacement vector => how much we move in x & y direction
Minimize difference between $I_1(x+u)$ and $I_0(x)$
- pick a Norm
#### $E_{SSD}(u) = \sum_i [I_1(x_i + u_i)-I_0(x_i)]^2 = \sum_i e_i^2$
- l2 loss - max diffarence =1
- If pixel is far away, then big error
- Differenciable 
- sensative to dead pixels

#### $E_{SAD}(u) = \sum_i |I_1(x_i + u_i)-I_0(x_i)|= \sum_i |e_i|$
- sensitive to small errors
- large errors dominate less

#### $E_{Lp}(u) = \left( \sum_i |I_1(x_i + u_i)-I_0(x_i)| ^p \right)^{1/p} = \sum_i (e_i^p)^{1/p}$
- exponent 1/p removable

#### $E_{SRD}(u) = \sum_i \rho(I_1(x_i + u)-I_0(x_i)) = \sum_i \rho(e_i)$
$\rho(x) = x^p$ Lp-Norm
$p_{GM}(x) = \frac{x^2}{1+x^2 / a ^2}$ Geman-McClure Kernel

- Sum of robust diffarences
- large error = platoe
- Diffarenciable

Windowed
$E_{WSRD}= \sum_i w_0(x_i+u_i) w_1(x_i) \rho(I_1(x_i + u)-I_0(x_i)) = \sum_i w_0(x_i+u_i) w_1(x_i)\rho(e_i)$
normalizeWindow
### Error general
- take into account how big the overlap of the images is
- evaluate only on overlap & punish not overlapping

Bias & Gain
- Diffarent cameras have diffarent properties
- Intensities approximate linearly & add transformation to error
$E_{SSD}(u) = \sum_i (I_1(x_i+u)-\alpha I_0(x) - \beta)^2$

Crosscorrelation
$E_{CC} = \sum_i I_0(x_i)I_1(x_i+ u)$
- produckt - scale in intencity
- Normalise by subtract average intencity

=> Decide error Metric $E(u)$ & search for $u$ by minimise $E(u)$

### Alighn - Esitimation of Translational Movement
- Image pyramid - optimize on low resolution by downsampelling
- Lucas-Kanade method: 
	- search at lowest level - optimize there
	- go 1 level up
	- only search in neighborhoods ...
- => Sub pixel accuracy Optimization problem

#### <span style="color:rgb(166, 0, 255)">Optimization of Translational Movement</span>
- linear interpolation between pixels at low resolution 
- & take derivative (Jacobian) => use differences to answer how much is pixel changing between images
- $J_1(x)\Delta x$ = how much color in $I_1$ changes if we move from $x$ in $\Delta x$ direction

1. Assume found optimum $u$ at previous level
2. From there take small steps $\Delta u$
$$I_1(x_i + u + \Delta u) \approx I_1(x_i + u) + J_1(x_i + u)\Delta u$$

###  <span style="color:rgb(166, 0, 255)">Lucas-Kanade Method</span>
$$E_{LK-SSD}(u+\Delta u) = \sum_i [I_1(x_i+u+\Delta u)-I_0(x_i)] = \sum_i [J_1(xi+u)\Delta u + e_i]^2$$
$e_i = I_1(x_i + u) - I_0(x_i)$
Oprimize jacobian of displacement
- Operation doen per pixel
- => solve optimization problem


$E(\Delta u) = ||A\Delta u - b||^2$
=> find minimum by setting as 0  
$A^T A \Delta u = A ^T b$  => solve for $\Delta u$
- nonlinear because original is only piece wise linear - look at part where linear
-  Reform: 2 Binomische Formel, find minimum by setting derivative to 0 & solve for $\Delta u$
- Optimize until we converge

### Other Motion
- take rotation into account => additional Parameter - phi
- Depending on whyt type of motion => need extra parameters => in $p$ 

$E_{LK-SSD}(p + \Delta p) = \sum_i [J_1(x_i')\Delta p + e_i]^2$
$J_1(x') = \frac{\partial I_1(x')}{\partial x'} \cdot \frac{\partial x'(x)}{\partial p}$
- motion per individual pixel
- but look at patch to know it is correct pixel

### Patch-based Optical Flow
- look at patch in image & identify it in next image - solve that for next
- size of patch is difficult


- displacement on sky (low texture)
	- regularize - assume pixels that are near move in simmilar way - punnish neighbouring pizel if too diffarent movement - regularization with $||\nabla u_i||^2$
$$E_{SSD-OF}(\{u_i\}) = \sum_i [I_1(x_i + u_i)-I_0(x_i)]^2 + \alpha ^2 ||\nabla u_i||^2$$
### Flow Net - solve with Data
![[Pasted image 20250921134938.png]]
simple:
- take 2 images & concatinate them

Corr
- process 1 & 2 image separately in the beginning

=> need ground truth optical flow data
- not apparent motion, but <span style="color:rgb(166, 0, 255)">real motion</span>
- synthetic training data as <span style="color:rgb(166, 0, 255)">ground truth </span> 


Percieve Illusion
- pretnet - predickt how next frame should look like
- apparent motion, when there is no real motion

#ComputerVision [[Computer Vision]] [[CV09 - Stereo Vision]]