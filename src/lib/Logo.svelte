<script>
	export let strokeColor = "white";
	export let fillColor = "transparent";
</script>

<div>
	<svg
		class="first"
		viewBox="0 0 72 65"
		fill="none"
		style="z-index: 100;"
		xmlns="http://www.w3.org/2000/svg"
	>
		<path
			d="M14.251 50.5831C0.15446 45.0535 -4.17872 24.3354 14.251 11.5747C14.565 7.43376 15.0676 6.80903 16.0141 5.95482L24.7099 3.20529C31.8308 1.38493 60.4211 1.27786 62.2415 5.34689C70.915 19.1067 73.8597 45.2343 61.1707 61.4569C53.9993 63.9136 42.1663 62.6343 37.0494 56.9577M14.251 50.5831C18.3481 51.8899 21.975 50.7927 24.177 49.6725M14.251 50.5831C10.8249 58.8765 19.6026 61.9343 37.0494 56.9577M37.0494 56.9577V47.5233"
			stroke={strokeColor}
			stroke-width="4"
			stroke-linecap="round"
			stroke-linejoin="round"
		/>
		<circle cx="51.6583" cy="45.4725" r="1.91708" fill={strokeColor} />
	</svg>

	<svg
		class="second"
		viewBox="0 0 72 65"
		fill="none"
		style="z-index: 200;"
		xmlns="http://www.w3.org/2000/svg"
	>
		<path
			d="M37.0494 47.5233C25.7761 44.0853 19.5398 31.5327 28.8942 18.0208L36.5697 12.8238L45.5243 47.5233C42.5859 48.1737 40.6215 48.1667 37.0494 47.5233Z"
			fill={fillColor}
		/>
		<path
			d="M28.8942 18.0208C19.5398 31.5327 25.7761 44.0853 37.0494 47.5233C40.6215 48.1667 42.5859 48.1737 45.5243 47.5233M28.8942 18.0208L24.177 13.9432M28.8942 18.0208L36.5697 12.8238"
			stroke={strokeColor}
			stroke-width="4"
			stroke-linecap="round"
			stroke-linejoin="round"
		/>
	</svg>
</div>

<style>
	div {
		position: relative;

		width: 100%;
		height: 100%;
	}

	svg.first {
		position: absolute;
		z-index: 200;
	}

	svg.second {
		position: absolute;
		z-index: 100;
	}
</style>
