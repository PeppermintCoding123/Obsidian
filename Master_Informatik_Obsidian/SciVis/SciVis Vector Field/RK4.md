= [[Runge Kutta]] fourth order
$$\mathrm{x}_i+1 = \mathrm{x}_i + h(\frac{\mathrm{k}_1}{6} + \frac{\mathrm{k}_2}{3}+\frac{\mathrm{k}_3}{3} + \frac{\mathrm{k}_4}{6})$$
$$\mathrm{k}_1 = \mathrm{v}(\mathrm{x}_i), \quad
\mathrm{k}_2 = \mathrm{v}(\mathrm{x}_i + \frac{h}{2}\mathrm{k}_1), \quad
\mathrm{k}_3 = \mathrm{v}(\mathrm{x}_i + \frac{h}{2}\mathrm{k}_2), \quad 
\mathrm{k}_4 = \mathrm{v}(\mathrm{x}_i + h\mathrm{k}_3)$$
