Given: $\alpha$-values that correspond to coverage of pixel
#### gl.blendFunc(gl.SRC_ALPHA_SATURATE, gl.ONE)
- initial $\alpha = 0$
- render **front to back**
- $\alpha$-channel contains **accumulated capacities**
	- once $\alpha = 0$ no further triangles are added
