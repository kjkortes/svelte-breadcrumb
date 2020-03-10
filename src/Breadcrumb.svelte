<script>
	export let stepsCount = 5;
	export let activeStep = 1;
	export let activeColor = '#0066f5';
	export let defaultColor = '#999';
	export let circleSize = 12;
	export let linewidth = 30;
	let lineStrokeWidth=2;
	$:currentStep = activeStep - 1;
</script>

<style>
	div{
		display:flex;
	}
</style>

<div>
	{#each new Array(stepsCount) as c,i}
		{#if i < stepsCount - 1 }
			<svg height="{circleSize}" width="{circleSize}">
				<circle cx="50%" cy="50%" r="50%" fill="{((i <= currentStep )?activeColor:defaultColor)}" />
				Sorry, your browser does not support inline SVG.  
			</svg> 
			<svg height="{circleSize}" width="{linewidth}">
				<line x1="0" y1="50%" x2="200" y2="50%" style="stroke:{((i <= currentStep-1 )?activeColor:defaultColor)};stroke-width:{lineStrokeWidth}" />
				Sorry, your browser does not support inline SVG.
			</svg>
		{/if}
		{#if i == stepsCount - 1}
			<svg height="{circleSize}" width="{circleSize}">
				<circle cx="50%" cy="50%" r="50%" fill="{((i <= currentStep )?activeColor:defaultColor)}" />
				Sorry, your browser does not support inline SVG.  
			</svg> 
		{/if}
	{/each}
</div>
