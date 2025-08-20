1. Build **Laplacian Pyramid** for $L_A, L_B$ (Images with averaging filter => shrink space)
	![[Pasted image 20250816154742.png]]
2. Build **Gaussian Pyramid** $GR$ for selected Region $R$
	= Multiple scaled versions of image
3. Combine $L_A$ & $L_B$ using $GR$ as alpha weights
	$$(L_S = GR * L_A + (1-GR)*L_B)_{(I, j)}$$
4. Collapse $L_S$ for final blend
	![[Pasted image 20250816160051.png]]

Das hier ist basically eine erweiterung von [[Frequency Blending (Burt & Adelson)]]
[[Alpha-Channel]] [[Feathering]] #CompositionAndBlending