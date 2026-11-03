# Initial
// compute Le + ∫ FLe + ∫ F∫ FLe + ∫ F∫ F∫ FLe + ⋯ up to N
Color <span style="color:rgb(255, 221, 0)">L( N,x,wout )</span> {
  Color c = Le( x,wout);
  if (N > 1) { // stop recursion if N\=\=0
    for i = 1 to n { // for n samples
    w,<span style="color:rgb(146, 208, 80)">pdf</span> = sampleDirection (x,wout)
    y = ray( x,w)
    c += <span style="color:rgb(255, 221, 0)">L(N - 1,y, - w)</span> / n / <span style="color:rgb(146, 208, 80)">pdf</span>;
    }
   }
   return c
}

# Separate direct & Indirect Light
// computes ∫ FLe 
<span style="color:rgb(0, 176, 240)">Color direct( x,wout) </span>
// compute ∫ FLe + ∫ F∫ FLe + ∫ F∫ F∫ FLe + ⋯ up to N
// we use L n = ∫ FLe + ∫ FL n − 1 = direct + ∫ FL n − 1

Color <span style="color:rgb(255, 221, 0)">L( N,x,wout )</span> {
	Color c = Le( x,wout) + <span style="color:rgb(0, 176, 240)">direct( x,wout);</span>
	if (N > 1) {
		for i = 1 to n {
			w,<span style="color:rgb(146, 208, 80)">pdf</span> = sampleDirection (x,wout)
			y = ray( x,w)
			c += <span style="color:rgb(255, 221, 0)">L(N - 1,y, - w)</span> / n / <span style="color:rgb(146, 208, 80)">pdf;</span>
		}
	}
	return c
}

# Pathtracing of length N
Color pathTracing (N,x,wout ) {
	<span style="color:rgb(0, 176, 240)">x[] = generatePath (x,wout,N );</span> // n paths
	Color c = 0;
	Facc = 1;
	for i = 1 to N
		c += <span style="color:rgb(255, 221, 0)">Le(x[ i])</span> * <span style="color:rgb(146, 208, 80)">Facc</span> ;
		<span style="color:rgb(146, 208, 80)">Facc </span>\*= F(x\[ i]))
	return c;
}

 Facc = what is left / how mutch it contributes - pdf & 1/N?

# Add direct sampling & importance sampling
Color pathTracing (N,x,wout ) {
	x\[],<span style="color:rgb(146, 208, 80)">p[]</span> = generatePath (x,wout,N - 1);
	Color c = 0;
	Facc = 1
	for i = 1 to N- 1
		c += <span style="color:rgb(255, 221, 0)">direct(x[ i])</span>\*Facc
		 Facc \*= F(x\[ i]) / <span style="color:rgb(146, 208, 80)">p[ i]</span>;
		if ( <span style="color:rgb(0, 176, 240)">Facc == 0</span>)
			<span style="color:rgb(0, 176, 240)">break</span>;
	return c;
}

p\[] = importance sampling PDF

# Use Russion Roulette
Color pathTracing (x,wout) {
	Color c = 0;
	Facc = 1
	while(true) {
		 c += <span style="color:rgb(255, 221, 0)">direct( x,wout)</span>\*Facc
		<span style="color:rgb(0, 176, 240)">p = wiselyChosenPRussianRoulette</span>(x, wout)
		if (<span style="color:rgb(0, 176, 240)">random() > p</span>)
			break
		win,<span style="color:rgb(146, 208, 80)">pdf</span> = sampleDirection (x,wout)
		Facc \*= F(x)/(<span style="color:rgb(0, 176, 240)">p</span>\*<span style="color:rgb(146, 208, 80)">pdf</span>)
		y = ray( x,win )
		x = y; 
		wout = - win
	}
	return c;
}

F(x)/(<span style="color:rgb(0, 176, 240)">p</span>\*<span style="color:rgb(146, 208, 80)">pdf</span>) = 1 over time

[[Global Illumination - overview.canvas]]