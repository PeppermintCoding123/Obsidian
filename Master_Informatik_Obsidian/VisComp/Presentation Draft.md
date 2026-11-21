
# Intro - 2 min

# Previous Work & Goal - 3 min
- small & tangible parameter set
- simulate transition of clouds (fog to stratocumulus to cumulus)
- simulate development of Supercells
- simulation in accordance of terrain
- real time weather nowcasting

# The Model - 15 min
- more important to understand individual processees than the full algorithm. 
- rather wnat to look at figures & develope an understanding of parameters in that way, instead of just goingg through list.

## Intro to how we separate the model - 1 min
## Heat & Humidity - 2 min
[[Fig.4 SSCDitN]] Buoyancy $B$ & humidity $\phi$
[[Fig.20 SSCDitN]] E, $\phi$, $\gamma_{heat}$, $\gamma_{vapour}$ & [[Fig.10 SSCDitN]]

## advection $q_{vs},q_v,q_c,q_r$ - 4 min
=> Kesslers scheme [[Fig.6 SSCDitN]] (transition between states)
=> wather continuity [[(23) SSCDitN]],[[(24) SSCDitN]], [[(25) SSCDitN]], 

& When do clouds form?
[[(16) SSCDitN]] $q_{vs}$ vapour saturation ratio

& numerics of boundaries [[5.1 Numerical Integration]]

## Temperature $T$, $\theta$, Energy / Thermodynamics - 2 min
[[(21) SSCDitN]] => entwickeln wei wir diese Formel kreigen

### Irgendwann die Graphik verwänden zum besser verstehen der Parameter? - wenn zeit & sinvoll

[[Fig.5 SSCDitN]] Dencity $\rho$, ~~Vapor fraction, advection $q_{vs}, q_v$, Temperature $T$

=> use as transition to fluid dynamics

## $u$ forces & fluid dynamics - 3 min
=> Wind (add-ons)
[[(20) SSCDitN]]
[[4.3 Fluid Dynamics]]
- wind Fields [[5.3 Wind Fields]], voracity confinement force $f_\omega$ [[5.1 Numerical Integration]]
[[Fig.17 SSCDitN]] => temporal evolution

## Add terrain - 1 min
[[(26) SSCDitN]], [[(25) SSCDitN]]

# Results / why is this good / what we can do with it - 2 min
# future research / what can we do further / other - 3 min

# slot -  1 min

=> 26 min (Dann rede ich langsamer): minimum 27min, maximum 30 min

