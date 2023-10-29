<svelte:options customElement="app-tabs" />

<script>
	import Home from "./t_home.svelte";
	import Services from "./t_services.svelte";
	import Products from "./t_products.svelte";
	import About from "./t_about.svelte";

	let tabs = [
		{ name: "Home", comp: Home },
		{ name: "Services", comp: Services },
		{ name: "Products", comp: Products },
		{ name: "About", comp: About },
	];

	let actual = tabs[0];
</script>

{#each tabs as tab}
	<button
		class:selected={actual.name === tab.name}
		on:click={() => (actual = tab)}
	>
		{tab.name}
	</button>
{/each}
<main>
	<svelte:component this={actual.comp} />
</main>

<style>
	button {
		cursor: pointer;
		padding: 0.5rem 1rem;
		border: 1px solid transparent;
		margin-bottom: -1px;
		background-color: #fff;
		border-bottom-color: #abc;
	}
	button.selected {
		border-top-right-radius: 8px;
		border-top-left-radius: 8px;
		border-top-width: 8px;
		border-color: #b0b #abc #fff;
	}
	main {
		font-size: 2rem;
		padding: 2rem;
		border: 1px solid #abc;
	}
</style>
