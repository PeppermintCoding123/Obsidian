[[CPaC - Lab2]]
# Given:
– **Multiple cameras**
– **Intrinsics of each camera j**
(focal length, principal point, ...)
– **Extrinsics of each camera j**
(position, orientation)
–** 2D pixel coordinates of a point in each camera**

### Find:
3D location of every observed point w 


# Method
- pinhole Camera Model 
	- => Stralensatz for screw
	- $x = \frac{\phi_xu + \lambda \gamma}{w} + \delta_x$
- Pinhole Camera in Homogeneous Coordinates
	- $\lambda \begin{bmatrix}x \\ y\\ 1\end{bmatrix} = \begin{bmatrix}\phi_x & \gamma & \delta_x & 0\\ 0 & \phi_y & \delta_y & 0\\ 0 & 0 & 1 & 0\end{bmatrix}\begin{bmatrix}u \\ v \\ w \\ 1\end{bmatrix}$
- Geometric interpretation
- Alighning Extrinsic Parameters
	- ![[Pasted image 20251003124331.png]]
- Callibrate Stereo Reconstruction [[Triangulation]]
	- ![[Pasted image 20251003124454.png]]
	1. Guess w
	2. Project w onto image plane
	3. minimize Distance between $x_1$ & $x_2$
	4. compare to $x_1$ & $x_2$
- [[Triangulation]]
	- Solve $Ax= b$ in Least Squares: $\hat{x} = \arg \min _x [x^TA^TAx-2x^T A^Tb+b^Tb]$
	- Derive for x & set 0: $x = (A^TA)^{-1}\cdot A^Tb$
- [[CV07 - Epipolar Geometry]]
- Projection Mapping
- Pixel Corespondences
	- #TODO 
- Binary Pattern & Gray Codes
- Projector Calibration
	- Gray Codes on Checkerdboard & compute Pixel coresspondence Camera => Projector
	- Detect corners in Photos => translate to local Homographies
	- Use local Homography (Matrix that translates points between 2 Plains) for robust results & sub-pixel precision
	- Calibrate projector like a camera

[[CPaC_Overveiw.canvas|CPaC_Overveiw]]