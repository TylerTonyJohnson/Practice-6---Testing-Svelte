
<script>
	import LifeGrid from "./components/LifeGrid.svelte"
	export let name;
</script>


<main>
	<h1>Hello {name}!</h1>
	<p>Visit the <a href="https://svelte.dev/tutorial" target="_blank">Svelte tutorial</a> to learn how to build Svelte apps.</p>
	<LifeGrid />
</main>


<style>
	:global(*, *::before, *::after) {
		box-sizing: border-box;
	}

	:global(body::-webkit-scrollbar) {
		display: none;
	}

	

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