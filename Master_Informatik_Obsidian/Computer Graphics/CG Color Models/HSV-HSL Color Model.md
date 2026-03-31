![[Pasted image 20260212105740.png]]
[[Drawing HSVModel 2026-02-12.excalidraw]]
![[Pasted image 20260212110529.png]]
### [[RGB Color Model]] => [[HSV-HSL Color Model]]


$$V = \max(R,G, B)$$
$$S = \frac{\max - \min}{\max}$$
$$H = \left\{ \begin{matrix}

60 \frac{G-B}{\max-\min} & if \; \max\{R, G, B\} = R\\
60 \frac{B-R}{\max-\min} + 120& if \; \max\{R, G, B\} = G \\
60 \frac{R-G}{\max-\min} + 240 & if \; \max\{R, G, B\} = B
\end{matrix}
\right.$$

for HSL:
$$L = \frac{\max+\min}{2}$$

with: 
$\max = \max(R, G, B)$
$\min = \min(R, G, B)$

### [[HSV-HSL Color Model]] => [[RGB Color Model]]

$$\color{SkyBlue} C = V \cdot S$$
$$\color{OrangeRed} X = \textcolor{SkyBlue}C \times (1-|\frac{H}{60°} \; mod 2 -1|)$$
$$m = V - C$$
$$(R', G', B') = \left\{ \begin{matrix}
(\textcolor{SkyBlue}C, \textcolor{OrangeRed}X, 0) & \leftarrow  0°\leq H < 60° \\
(\textcolor{OrangeRed}X, \textcolor{SkyBlue}C, 0) & \leftarrow 60°\leq H < 120° \\
(0, \textcolor{SkyBlue}C, \textcolor{OrangeRed}X) & \leftarrow 120°\leq H < 180° \\
(0, \textcolor{OrangeRed}X, \textcolor{SkyBlue}C) & \leftarrow 180°\leq H < 240° \\
(\textcolor{OrangeRed}X, 0, \textcolor{SkyBlue}C) & \leftarrow 240°\leq H < 300° \\
(\textcolor{SkyBlue}C, 0, \textcolor{OrangeRed}X) & \leftarrow  300°\leq H < 360° 
\end{matrix}\right.$$
$$(R, G, B) = ((R' + m)\cdot 255, (G'+m)\cdot 255, (B'+m)\cdot 255)$$

[[Computer Graphics - overview.canvas]]