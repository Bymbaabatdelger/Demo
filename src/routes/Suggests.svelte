<script>
	import Song from './Song.svelte';
	import { sec, songs } from './songs';
</script>

<div>
	<div class="title-container">
		<p class="suggest">Санал болгох</p>
		<p class="all">Бүгд</p>
	</div>
	<hr />
	<div class="container">
		{#each songs as song}
			<Song {...song} />
		{/each}
	</div>
	<div class="sec">
		{#each sec as song}
			<Song {...song} />
		{/each}
	</div>
</div>

<style>
	.container {
		display: flex;
		justify-content: space-between;
		flex-wrap: wrap;
		gap: 24px;
		margin-top: 20px;
		margin-bottom: 40px;
	}
	hr {
		height: 1px;
		background-color: #52525b;
		border: none;
		width: 100%;
	}
	.title-container {
		display: flex;
		justify-content: space-between;
		align-items: center;
	}
	.suggest {
		color: #fff;
		font-size: 24px;
		font-family: 'Roboto', sans-serif;
	}
	p {
		color: #fff;
		font-weight: 700;
		font-size: 16px;
		font-family: 'Roboto', sans-serif;
	}
	.sec {
		display: none;
	}
	@media (max-width: 768px) {
		div {
			margin: 1rem;
			padding: 0;
		}
		.all {
			display: none;
		}
		.container {
			display: none;
		}
		.sec {
			display: block;
			display: flex;
			flex-direction: column;
			gap: 20px;
			margin: auto;
		}
	}
</style>
