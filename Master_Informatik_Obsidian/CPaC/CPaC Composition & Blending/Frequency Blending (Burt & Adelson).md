1. FFT: $FFT_A$ , $FFT_B$
2. Decompose Fourier image into octaves
	![[Drawing 2025-08-16 15.04.42.excalidraw.restored]]
	octave band = double frequency range of previous one
	=> $FFT_A = F_A¹ + F_A² + ...$ 
3. [[Feathering]] of corresponding octaves $F_C^i = F_A^i + F_B^i$
4. Inverse FFT
5. Fether $F_C¹, F_C², ...$


[[Alpha-Channel]] [[Feathering]] #CompositionAndBlending