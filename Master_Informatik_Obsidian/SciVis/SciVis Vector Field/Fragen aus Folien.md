[[SciVis - overview.canvas|SciVis - overview]] 
# 1
#### Explain all steps of the visualization pipeline!
- Filtering (choose wich data point are ineteresting), 
- Extraction (get interesting features from datapoints), 
- Mapping (assighn to visual system for display), 
- Image Synthesis (generate image)
#### Why do we perform data abstraction?
- transform date to structure withought spacial context (Bahn netz erstellen)
#### Name and explain data types!

#### What is the difference between a link and a grid?
- Link = abstract date, grid = spacial data
#### Given a visualization, identify the items/links/attributes or positions/grid/attributes, respectively!

#### Which different types of attributes do exist?
Nominal, Ordinal, Quantitative
#### Categorize a given attribute!
#### Which types of marks exist?
- points, lines, aread, volumes
#### Which types of channels exist?
- magnitude & Identity
#### Order encodings by their effectiveness!
- page 56
#### Name channels that are appropriate to encode nominal/ordinal/quantitative data!
#### Explain the components of the HSL color space!
- hew (farbwert grün, blau, pink, ...) , saturation (intencit, nicht grautohn), luminance (wießtohn in der Farbe)
#### Name guidelines for use of color!
- not rainbowmap
- nicht grün

# 2
#### What types of grid structures exist?
- cartesian, recular, rectalinear, curved, unstructured 
#### What is the runtime complexity of locating a cell in a regular grid?
- O(1)
#### How do we locate a cell in an unstructured grid?
Use spatial acceleration data structure such as bounding volume hierarchy
- 1. Traverse the tree top-down and test all triangles within the lowest box (speicher zeug) p. 33
- 2. start with inital guess & search the values around you
#### What are advantages of unstructured grids?
- sparce topology more efficiant & can change granuality / accuracy where it is important
#### Given a set of scattered data points. How can their attributes be interpolated efficiently?
- [[Shepard Interpolation]]
#### How is triangle quality assessed?
- Maximizes ratio of incircle to enclosing circle
- Maximizes the smallest angle in all triangles
#### Given some triangle (a, b, c), sketch the barycentric coordinates
$(u, v, w)=(1/2, 1/4, 1/4)$ and $(u, v, w) = (0, 1/3, 3/3)$
#### Why is the update order in data transformation pipelines relevant?
- to aviode repeating node ausführung
#### Name common data formats!
- vtk
- Net cdf

# 3
#### How is the gradient of a scalar field calculated and what does it mean?
= flow direction towards maximum, $\nabla f$ übereinander nach x, y, z ableiten
#### Which vector field could be used to trace isolines?
- gradient field is perpendicular (normal) to the isocontour of the value x_0 at that point
#### How can minima/maxima of scalar fields be distinguished?
- eigenwerte bestimmen & schauen ob < / > oder mit Hauptminoren
#### What are the vertices of a Morse-Smale cell?
- the critical points of a scalar field
#### How can ridges in 2D and 3D scalar fields be defined?
in 2D - Separatricies
- Ridge line consists of all points where minor principal curvature has negative local minimum along its lines of curvature
- Valley line consists of all points where major principal curvature has positive local maximum along its lines of curvature
![[Pasted image 20250912153531.png]]
in 3D
- Ridge line consists of all points where the mean curvature of its isosurface passing through has local maximum - Der teil der Iso-surface, wo die stärkste Krümmung ist
- Valley line consists of all points where the mean curvature of its isosurface passing through has local minimum
- Needs 3rd order derivatives of field

# 4
#### Explain the Maximum Intensity Projection!
- choose the largest value of all the sampled values form martching ray as the new value for that projection
#### What is a 2D transfer function?
- maps scalar values to RGBA or other Colour space
#### What is the difference between pre-classification and post-classification?
pre: Transfer function , then trilinear interpolation
post: first interpolate then use transfer function 
#### Explain back-to-front and front-to-back compositing
- ftb  ray & build as mowing 
- btf shoot till end & calculate starting from the back
#### Is ray marching unbiased?
 - no bacause sample in equal distances, discrete points => might miss values
#### What is the free flight distance?
- distance between sampling points of monte carlo sample points
#### How can the free flight distance be used to estimate transmittance?
- higher distance => lower transmittance
- $T(d) = e^{-\sigma _t \dot d}$ 
# 5
#### Explain and apply the marching squares algorithm to a random 3x3 scalar grid for a given isovalue.
- Wo isosurfaces go & [[Marching Squares]]
#### How can we resolve ambiguities in marching squares?
- Midpoint, asymptomatic
#### Name and explain extensions of the marching cubes algorithm!
- Adaptive refinement
- Connected component anaylsis
#### Isosurface reconstruction gives noisy results and contains many small objects. How can the result be cleaned up?
- connected component analysis
#### What are the nodes and edges in a contour tree?
- leaf node represents the creation or deletion of a component
- interior node represents the joining and/or splitting of two or more components
- edge represents a component in the level set for all values between the values at each end of the edge - alles zwischen crictical points 
#### How is the contour tree computed?
- join, split, & merge tree algorithm
#### What is the difference between the join tree and split tree construction algorithm?
- none, just start from small number (Join tree) or big numbers (split tree)
#### Can the split tree be computed by running the join tree algorithm after simply flipping the sign of the scalar field?
- jes
#### What can the contour tree be used for?
- [[Persistence]] based topological denoising
- Flexible Isosurfaces
#### Does the contour tree construction algorithm work for any dimension?
- [[Contour Tree Algorithm]]  jes, as long as we have a propper metric
#### What is persistence?
- abstand von localen minima oder maxima zu ihrem jeweiligen saddle 
#### How does topological denoising work?
- compute persistance & only keep the extrema with the largest persistence. "collapse edge with the smallest persistence & flatten field"

# 6
#### What are divergence and curl?
[[Divergence]] = expansion or contraction in small area around a given point
[[Curl]] = twists
#### What is the meaning of the Poincaré index?
 [[Poincaré-index]] = number of counterclocwise rotation when moving in a counterclocwise direction around closed loop
#### Be ready to compute Jacobian, divergence, curl and Laplace of a given scalar/vector field! (see exercises)
#### How can sinks/saddles/sources in vector fields be distinguished?
- Eigenvalues of Jacobian
#### Can saddles in 2D/3D vector fields be swirling? Why?
- 2D: no, because Imaginary part needs 3 to be swirling, but not possible in 2D
- 3D: yes - attracting saddle focus & repelling saddle focus
#### Be ready to extract and classify critical points in analytic vector fields!

#### How can we extract critical points numerically?
- Vectorfield = 0
- Newton um nullstellen zu finden
- Bezier curve 

# 7
#### Given a linear vector field v = $(x − y, 2x + x)^ T$ and a seed point $x_0 =( 0,1 )^T$ . Calculate the end point after integration duration $\tau = 2$ analytically!
Streamlineintegration page 39 formel mit D, E 
#### Use a numerical integrator and see if you get the same result!
RK oder Euler
#### Write the equations down for Euler, RK2 and RK4!
[[Forward Euler integration]] [[RK2]] [[RK4]]
#### Explain the differences of: Euler, RK2, RK4, adaptive RK(3)
- euler = dümmste richtung von Vectorfeld, nicht sehr rechneintensiv
- RK 2 aus 2 iterationsschritten zusammenbauen
- RK 4 ist genauer 
- Adaptive ist um stepsize an zu passen um genauer dahin zu kommen
#### RK2 is twice as expensive as Euler. Is it worth it compared to using Euler with halve the step size?
- jes
#### Why is streamline selection in 3D harder than in 2D?
- way more options
- way more bad options that do not show the correct structures or display stuff badly with overlapping, occlusion, ...

# 8
#### Explain the Line Integral Convolution algorithm!
random texture & smooth along lines on direction with forward & backward. avweradge is value for that point
#### What happens if the domain is closed and [[LIC]] is computed for infinitely long streamlines?
either form a closed loop or gives the average of all values in the closed domain.
#### How can we extend LIC to show orientation?
[[Oriented LIC]] anisotropic convolution curve
#### How can particle advection be enabled on large fluid flows that do not fit into memory at once?
split domain - use [[Drawing RingBuffering.excalidraw]] Ring Buffering,
#### Explain the finite-time Lyapunov exponent!
describes repelling and attracting structures around a certain point over a specific time
[[FTLE]]
- ln weil streamlines exponentially separieren
- sqrt for spectral norm 
- 1/tau for normalisierung
#### How can we compute FTLE?
[[FTLE]]
#### Which types of Lagrangian Coherent Structures exist?
- Hyperbolic
- eliptic
- parabolic - sheers

# 9
#### How many stream lines pass through one point in the domain?
1
#### How many stream surfaces pass through one point in the domain?
infinity much
#### How are front lines adaptively refined?
inserting or deleting vertecies on frontline that are too far appart or too close
#### When can insertion at the seed curve become impractical?
in time dependant vector fields / when the vector field changes
#### Which properties make a good stream surface?
small flow alighnment error
having a seed-curve that dose not diverge too much & dose not contract too much
#### Why is streak surface integration more expensive than path surface integration?
because every vertex of the mesh must be integrated at every time step
adaptive modification of entire mesh p. 96
#### Why is the smoke surface rendering approach more efficient than the point-based and triangle-based approach?
the large same surfaces are transparent => no need to have that many points / information on those surfaces.

# 10

#### Name the parts of a topological skeleton! Explain each part!
[[Critical Points - Topology]]
[[Boundary switch points - Topology]] - tangential zum ende 
[[Attatchment/ Detatchment points at non-slip boundaries - Toplogy]]- saddel at edge of domain wit a $v = 0$
[[Separatrisies]]- devides areas into same direction of flow
[[Isolated closed streamlines]] - dose not go to critical point
#### How many critical points can we have in a linear/bilinear vector field? How can we extract the critical points?
linear vectorfield =  3 dim => 3, 2dim =>2
bilinear vectorfield = 


= 0 setzen for vector fields
#### How can we extract isolated closed streamlines?
[[Isolated closed streamlines - Steady 2D Topology]]
oder mit [[Poincaré-index]] auch in 3D
#### Explain Hopf and Fold [[Bifurcation]]!
Hopf - focus to center to focus
Fold - collapsing of source, sink or saddle
#### How is the feature flow field defined? [[FFF]]
define f such that critical lines of s are streamlines of f als als grad v times gradient von v
=> find critical point in v with streamlineintegration in f
#### What is the feature flow field in a steady flow?
 = spatial distribution of fluid velocityies thooughout system with property that velocities remain constant over time at every fixed point in space

#### Is the feature flow field divergence-free?
yes
#### Can a streamline connect two saddles?
yes in unsteady flow, no in steady flow
#### Can we have critical points in time-dependent flows?
neither s or p can have critical points, but v can have critical points
##### How many critical points can we have in a linear/trilinear vector field?

#### How can we extract the critical points?
= 0 for steady time
else set 0 & get gleichung die von t abhängt
#### How many dimension(s) can a separatrix have in 3D?
2 Dim for stream surfaces
#### How can we compute saddle connectors in 3D?
the intersector between the 2 stream-suffaces of foci 
![[Pasted image 20250911164548.png]]
#### When can we use streamline-oriented topology?
(finding out topology when doing something with streamlines)
- for instantanious fields page 96
- 3D Unsteady Topology => per time slice

# 11
#### What is a vortex according to Lugt?
- any mass of fluid moving around a common axis
#### What is Galilean Invariance and why is it important?
- If move refferance frame on all points at same speed, then newtons lawas are invariant under this equal-speed translation
- sachen die unter Galileo translation unverändert bleiben:
  - Jacobian $J$
  - Subtract feature flow field v − f 
  - Acceleration a = J(v − f) 
#### Describe vorticity, helicity, λ2 and Q!
vorticity = $|curl(\mathbf{v})| = |\nabla \times \mathbf{v}| \geq \omega_{thresh}$ = wie schnell sich zeug dreht
helicity = $|(\nabla \times \mathbf{v})\cdot \mathbf{v}|\geq h_{thresh}$ = how much a vector field twists around direction of propagation
$\lambda2$ = $\mathbf{\Omega}^2 + \mathbf{S}^2 = - \frac{1}{\rho} \mathbf{H}(p)$  - criterion to decide if we have a vortex with the help of pressure
Q-criterion: $Q = \frac{1}{2} (||\mathbf{Q}||^2 - ||\mathbf{S}||^2)> 0$ => if teh change of vector field is > 0

all above are Galilean invariant
#### Which vortex measures/extractors are Galilean invariant?
- λ2 , Q, vorticity, Okubo-Weiss → all based on J
#### Explain the reduced velocity criterion!
$\mathbf{w}_2 = \lambda \mathbf{w}_1$ , mit $\mathbf{w}_1 = \mathbf{v}$ und $\mathbf{w}_2 = (\nabla \mathbf{v})\mathbf{v}$ = schauen wann vectorfeld unddas vom Jacobi verzärten vectorfeld gleich sind 
#### How can it be rephrased into parallel vectors notation?
$\mathbf{v}|| \mathbf{Jv}$
#### How can we extract parallel vectors?
sichen nullstellen von $\mathbf{s} = \mathbf{w}_1 \times \mathbf{w}_2 = (0,0,0)^T$ 
für jede komponente von s die isosurface = 0 und schaue wo die sich treffen (mit newton oder wo anders)
#### What is a streamline core / pathline core?
pathline code mabey?
![[Pasted image 20250911154528.png]]
#### How can we extract pathline cores?
