<script lang="ts">
	import Conter from './Counter.svelte';
	import Mountain from './Mountain.svelte'

	export let name: string;

	let mountains = [
		{ name: '富士山' , summited: false },
		{ name: '北岳' , summited: true }
	]
</script>

<main>
	{name}
	<h1>百名山　登頂管理</h1>
	
	<div class='conteiner'>
		{ #each mountains as mountain }
			<Mountain name = {mountain.name} summited={mountain.summited} />
		{ /each }
	</div>

	<Conter />
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

	.conteiner {
		display: inline-flex;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>