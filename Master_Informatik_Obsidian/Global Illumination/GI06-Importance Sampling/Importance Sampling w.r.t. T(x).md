![[Pasted image 20260912184319.png]]

## Algorithm
τ = 0
x\[] = samples along ray with step size h
ξ = random ()
for i = 1 to x.length
    τ += <span style="color:rgb(255, 149, 0)">h * μ(x[i])</span>
    if <span style="color:rgb(255, 149, 0)">τ > - ln(1 - ξ )</span>
        scatter ray

// ray was not stattered, use background [[Attenuation]] by $e^{-\tau}$

[[Global Illumination - overview.canvas]]
[[Importance Sampling]]
[[Transmittance Estimation]]