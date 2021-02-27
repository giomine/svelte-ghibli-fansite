<script>
	import { Router, Route } from "svelte-navigator";
	import Home from "./Home.svelte";
	import Films from "./Films.svelte";
	import Characters from "./Characters.svelte";
</script>

<Router>
<main>
		<Route path="/">
			<Home />
		</Route>
		<Route path="/films">
			<Films />
		</Route>
		<Route path="/characters">
			<Characters />
		</Route>

</main>
</Router>

<style>
	main{
		text-align: center;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>