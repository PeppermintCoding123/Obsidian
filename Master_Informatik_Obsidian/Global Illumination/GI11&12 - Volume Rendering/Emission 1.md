$L(x) = \int_0^z T(x)L_e(x)dx + T(z)L_0 \approx (\sum_{i=1}^n T(x)L_e(x_i)) + T(z)L_0$

### Algorithim
τ = 0
L = 0
x\[] = samples along ray with <span style="color:rgb(255, 192, 0)">step size h</span>
for i = 1 to x.length
    τ += h \* μ(x\[i])      // dencity \* step size h
    T = exp (- τ )          // corresponding Transparency
    L += T \* <span style="color:rgb(255, 192, 0)">Le(x[i])</span>     // add <span style="color:rgb(255, 192, 0)">emission</span> of x\[i]
L += exp (- τ ) \* L0   // background radiance

[[Emission]]
[[Global Illumination - overview.canvas]]