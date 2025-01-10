<script lang="ts">
	import Bell from './Bell.svelte';
	import Flag from './Flag.svelte';
	import Profile from './Profile.svelte';
	let mmusic = './icons/Mmusic.png';
</script>

<nav>
	
	<div class="icon-container">
		<img class="mmusic" src={mmusic} alt="mmusic" />
		<div class="container">
			<Flag />
			<Bell />
			<Profile />
		</div>
	</div>
</nav>

<style>
	
	nav {
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	div {
		margin-left: 20px;
		display: flex;
		gap: 10px;
	}
	.container {
		display: flex;
		align-items: center;
		gap: 10px;
		padding-right: 1.5rem;
	}
	.mmusic {
		display: none;
	}
	@media (max-width: 768px) {
		div {
			display: flex;
		}
		.mmusic {
			display: block;
		}
	}
</style>
