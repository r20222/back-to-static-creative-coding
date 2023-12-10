<script>
	// Variabelen waaraan ik de x en y waarde wil gaan meegeven van de cursor op het scherm
	let mouseX = 0;
  	let mouseY = 0;

	// Deze functie houd actueel de x en y waarde van de muis op het scherm bij
	function handleMouseMove(event) {
		mouseX = event.clientX;
		mouseY = event.clientY + window.scrollY;

		// De onderstaande code werkt de CSS custom properties van mouseX en mouseY bij
		document.documentElement.style.setProperty('--mouseX', `${mouseX}px`);
		document.documentElement.style.setProperty('--mouseY', `${mouseY - 190}px`);
	}
</script>

<!-- dit zet de functie handleMouseMove in gang wanneer de muis beweegt -->
<svelte:window on:mousemove={handleMouseMove} />

<svg width="500" height="200">
    <path d="M10 80 Q 95 10 180 80 T 350 80"  />
    <path d="M20 90 Q 95 20 180 90 T 360 90"  />
    <path d="M30 100 Q 95 30 180 100 T 370 100"  />
</svg>

<style>
        /* Cursor animatie */
	path {
	stroke-dasharray: 150 5;
	stroke-dashoffset: 1000;
	animation: dash 15s linear alternate infinite;
	}
	path:nth-child(1){
		stroke:#629267 ;
		stroke-width: 6 ;
		fill:transparent;
	}
	path:nth-child(2){
		stroke:#DC9813; 
		stroke-width:6;
		fill:transparent;
	}
	path:nth-child(3){
		stroke:#A8371B;
		stroke-width:6;
		fill:transparent;
	}
	svg{
		position: absolute;
		z-index: 1000;
		transform: translate(var(--mouseX), var(--mouseY));
	}
	@keyframes dash {
        from {
            stroke-dashoffset: 1000;
        }
        to {
            stroke-dashoffset: 0;
        }
	}
	@media (prefers-reduced-motion) {
		path {
			stroke-dasharray: 150 5;
			stroke-dashoffset: 1000;
			animation: none;
		}
	}
</style>