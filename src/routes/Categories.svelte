<script>
	import Card from './Card.svelte';
	import { tracks } from './tracks';

	let { name } = $props();
</script>

<div>
	<p>{name}</p>
	<hr />
	<div class="container">
		{#each tracks as track}
			<Card {...track} />
		{/each}
	</div>
</div>

<style>
	.container {
		display: flex;
		justify-content: space-between;
        margin-top: 20px;
	}
	p {
		color: white;
		font-size: 24px;
		font-weight: 700;
		font-family: 'Roboto', sans-serif;
	}
	hr {
		height: 1px;
		background-color: #52525b;
		border: none;
	}
	@media (max-width: 768px) {
      .container {
		overflow: scroll;
		display: flex;
		gap: 10px;
		
	  } 
	}
</style>
