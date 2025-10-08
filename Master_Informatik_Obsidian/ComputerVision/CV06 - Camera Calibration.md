### <span style="color:rgb(166, 0, 255)">linear Transformation</span>
$p' = T(p) =  \begin{bmatrix}x' \\ y'\end{bmatrix} = T \begin{bmatrix}x \\ y\end{bmatrix}$

#### <span style="color:rgb(166, 0, 255)">Scaling</span>
- multiply each component by scalar
$\begin{bmatrix}x' \\ y'\end{bmatrix} = \begin{bmatrix}s_x & 0 \\0& s_y\end{bmatrix}\begin{bmatrix}x \\ y\end{bmatrix}$
#### <span style="color:rgb(166, 0, 255)">2D Rotation</span>
$\begin{bmatrix}x' \\ y'\end{bmatrix} = \begin{bmatrix}\cos \theta & -\sin \theta \\\sin \theta& \cos \theta\end{bmatrix}\begin{bmatrix}x \\ y\end{bmatrix}$
#### <span style="color:rgb(166, 0, 255)">Shear</span>
$\begin{bmatrix}x' \\ y'\end{bmatrix} = \begin{bmatrix}1 & \alpha_x \\ \alpha_y& 1\end{bmatrix}\begin{bmatrix}x \\ y\end{bmatrix}$

### <span style="color:rgb(166, 0, 255)">Affine Transformations</span>
Linear transformations & ...
#### <span style="color:rgb(166, 0, 255)">Translation</span>
$\begin{bmatrix}x' \\ y'\\ 1\end{bmatrix} = \begin{bmatrix}a & b & c\\ d& e & f \\ 0 & 0& 1\end{bmatrix}\begin{bmatrix}x \\ y \\ 1\end{bmatrix}$

### <span style="color:rgb(166, 0, 255)">Protective / Perspective Transformations</span>
$\begin{bmatrix}x' \\ y'\\ 1\end{bmatrix} = \begin{bmatrix}a & b & c\\ d& e & f \\ g & h& 1\end{bmatrix}\begin{bmatrix}x \\ y \\ 1\end{bmatrix}$
- need 4 points for 8 degrees of freedom in 2D
- Homography = die 3x3 matrix


All closed after composition => stay in group of type, when apply multiple

![[Drawing CameraProjection.excalidraw]]
### How to <span style="color:rgb(166, 0, 255)">calibrate</span> camera?
#### $K[R\; t]= M = 3 \times 4Matrix$
- regression problem
- Have points that are easily identifiable & know their geometry in 3D World

#### Fitting Line - <span style="color:rgb(166, 0, 255)">regression problem</span>
- <span style="color:rgb(166, 0, 255)">least Squares</span> line fitting => minimize distance between our points & line
- Matrix equasion => closed form solution (Demore-penrose ) - no iterative stuff, just apply

#### <span style="color:rgb(166, 0, 255)">Total</span> least squares
- changed regression Problem & solution
$x ^T A^TAx \quad s.t. \; x^T x = 1$ 
or minimize $\frac{x ^T A^TAx}{x^T x}$ 
=> <span style="color:rgb(166, 0, 255)">Eigenvector</span> corresponding to <span style="color:rgb(166, 0, 255)">smallest </span>eigenvalue $\lambda_1 =min\;eig(A^T A)$

LSTSQ =>
Problems - sensitive to outliers
Rather iterative

#### Calibrating Camera
- Camera calibration with patches at known position

How many points needed?
- 11GOF 1 eq per unknown => 5 1/2 points => 6 points
- Least squares, because overdetermined system

##### What is least squares doing?
- Given 3D point evidence, find best M which minimizes error between estimate (p’) and known corresponding 2D points (p).

 Camera calibration Umformungen 
- => get fancy matrices 
-  fix $m34$ as 1 because extra value when 11 DOF

1. (X, Y, Z) projection under candidate M
$$\begin{bmatrix}su \\ sv\\ s\end{bmatrix} = \begin{bmatrix}m_{11} & m_{12} & m_{13} & m_{14}\\ m_{21}& m_{22} & m_{23} & m_{24}\\
m_{31}& m_{32}& m_{33}& m_{34}\end{bmatrix}\begin{bmatrix}X \\ Y \\ Z\\ 1\end{bmatrix}$$
2. 2 Equasions per 3D point
	$u = ... \quad v = ...$
3. <span style="color:rgb(166, 0, 255)">M coefficiants</span>

Method 1:
1. $Ax=b$ form Solve for M’s entries using linear least squares
$$\begin{bmatrix}X_1 & Y_1 & Z_1 & 1& 0 & 0 & 0 & 0 & -u_1 X_1 & -u_1 Y_1 & -u_1 Z_1\\
0 & 0 & 0 & 0 & X_1 & Y_1 & Z_1 & 1&-v_1 X_1 & -v_1 Y_1 & -v_1 Z_1\\
&&&&&&\vdots\\
X_n & Y_n & Z_n & 1& 0 & 0 & 0 & 0 & -u_n X_n & -u_n Y_n & -u_n Z_n\\
0 & 0 & 0 & 0 & X_n & Y_n & Z_n & 1&-v_n X_n & -v_n Y_n & -v_n Z_n\\\end{bmatrix}\begin{bmatrix}m_{11} \\ m_{12} \\ m_{13} \\ m_{14}\\ m_{21}\\ m_{22} \\ m_{23} \\ m_{24}\\
m_{31}\\ m_{32}\\ m_{33}\\ m_{34}\end{bmatrix} = \begin{bmatrix}u_1\\ v_1 \\ \cdots \\ u_n \\ v_n\end{bmatrix}$$

- then the python 
	- Take last wrow of Vh because already transposed => contains parameters
```
M = np.linalg.lstsq(A,b)[0];
M = np.append(M,1)
M = np.reshape(M, (3,4))
```

Method 2:
$$\begin{bmatrix}X_1 & Y_1 & Z_1 & 1& 0 & 0 & 0 & 0 & -u_1 X_1 & -u_1 Y_1 & -u_1 Z_1\\
0 & 0 & 0 & 0 & X_1 & Y_1 & Z_1 & 1&-v_1 X_1 & -v_1 Y_1 & -v_1 Z_1\\
&&&&&&\vdots\\
X_n & Y_n & Z_n & 1& 0 & 0 & 0 & 0 & -u_n X_n & -u_n Y_n & -u_n Z_n\\
0 & 0 & 0 & 0 & X_n & Y_n & Z_n & 1&-v_n X_n & -v_n Y_n & -v_n Z_n\\\end{bmatrix}\begin{bmatrix}m_{11} \\ m_{12} \\ m_{13} \\ m_{14}\\ m_{21}\\ m_{22} \\ m_{23} \\ m_{24}\\
m_{31}\\ m_{32}\\ m_{33}\\ m_{34}\end{bmatrix} = \begin{bmatrix}0\\ 0 \\ \cdots \\ 0 \\ 0\end{bmatrix}$$

```
U, S, Vh = np.linalg.svd(a)
M = Vh[-1,:]
M = np.reshape(M, (3,4))
```

#### Calibration with linear method
Advantages
- Easy to formulate and solve
- Provides initialization for non-linear methods
Disadvantages
- Doesn’t directly give you camera parameters
- Doesn’t model radial distortion
- Can’t impose constraints, such as known focal length
=> use non-linear Methods

getting K, R, t
- Use RQ factorization of M


Recover camera center = actual location of camera in world space
- from extrinsic => C = Camera center
$C = -R^{-1}t$

- This all per single image calibration

CV - [[Computer Vision]] #ComputerVision
[[CV07 - Epipolar Geometry]]