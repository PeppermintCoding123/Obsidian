- subdivide into importance
- compute opacity by energy minimization
- blend along lines

- as post-process - **Decoupled Approach**
#### Triangle strip
- use fragment shader
- ![[Pasted image 20250906123708.png]]

#### Illuminated streamlines
- with Phong's illumination
- ![[Pasted image 20250906123826.png]]

#### Stream ribbons
- additional vector information:
	- $\mathrm{w} = curl(\mathrm{v})$ or $\mathrm{w} = \nabla\mathrm{v} \cdot \mathrm{v}$
- ribbon along streamline
![[Pasted image 20250906124105.png]]

#VectorField #SciVis 