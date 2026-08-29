$$\begin{matrix}& & \color{deeppink}\text{edges}\color{black}
\\
C & =  \color{deeppink}\text{nodes} & \color{black}\begin{pmatrix}.& .& . \\ .&.&.\end{pmatrix}\end{matrix}$$
use <span style="color:rgb(255, 0, 102)">-1</span> if the edge<span style="color:rgb(255, 0, 102)"> starts</span> in that node & use <span style="color:rgb(255, 0, 102)">+1</span> if the edge <span style="color:rgb(255, 0, 102)">ends </span>in that node
$$\begin{matrix}& & \color{deeppink}\text{edges as in C}\color{black}
\\
D & =  &\begin{pmatrix}.& .& . \\ .&.&.\end{pmatrix}\end{matrix}$$
just add the edge Vectors belonging to the specific edge

$$D  =  \begin{pmatrix}\overline{V} \\ d\end{pmatrix}$$
only works if time direction is the last one. 
$\overline{V}$ = dependencies in spacial direction
$d$ = dependencies in time direction