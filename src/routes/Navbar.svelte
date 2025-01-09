<script lang="ts">
	import Bell from './Bell.svelte';
	import Flag from './Flag.svelte';
	import Profile from './Profile.svelte';
	let left = './icons/chevron-left.svg';
	let right = './icons/chevron-right.svg';
	let mmusic = './icons/Mmusic.png';
	let isIconVisible= false;
</script>

<nav>
	<div class:mobile-hide={!isIconVisible}>
		<img src={left} alt="left" />
		<img src={right} alt="right" />
	</div>
	<img class="mmusic" src={mmusic} alt="mmusic"/>
	<div class="container">
		<Flag />
		<Bell />
		<Profile />
	</div>
</nav>

<style>
	  .mobile-hide {
		display: block;
	}
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

	img:hover {
		filter: brightness(0) saturate(100%) invert(1);
	}
	.container {
		display: flex;
		align-items: center;
		gap: 10px;
	}
	.mmusic{
		display: none;
	}
    @media (max-width: 768px) {
        div {
			display: flex;
		}

		div.mobile-hide {
			display: none;
		}
        .mmusic {
            display: block;
        }
	}
</style>
