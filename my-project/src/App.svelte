<script>
	let name = 'My First Svelte App';
	let beltcolor = 'Black Belt'

	const handleClick = () =>{
		beltcolor = 'Orange Belt'
	}
</script>

<main>
	<h1>{name}</h1>
	<p>{beltcolor}</p>
	<buttton on:click={handleClick}>Change Belt Color</buttton>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>