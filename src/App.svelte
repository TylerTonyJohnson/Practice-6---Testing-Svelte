
<script>
import { get } from "svelte/store";

	import LifeGrid from "./components/LifeGrid.svelte"
	export let name;

	const getData = async () => {
		console.log("Processing...");
		const request = await fetch("");
		const data = await request.json();
		return data;
	}

	const sendRequest = () => {
		getData().then(data => {
			console.log(data);
			document.getElementById("total-cases").innerText = data.confirmed.value;
		})
	}


</script>


<main>
	<h1>Hello {name}!</h1>
	<p>Visit the <a href="https://svelte.dev/tutorial" target="_blank">Svelte tutorial</a> to learn how to build Svelte apps.</p>
	<button on:click={sendRequest}>SEND</button>
	<div id="container">
		<h3>Total Covid Cases</h3>
		<h2 id="total-cases">0</h2>
	</div>
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