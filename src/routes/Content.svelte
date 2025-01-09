<script>
	import Categories from './Categories.svelte';

	let banner = './icons/banner.png';
</script>

<div>
	<img class="mobile-hide" src={banner} alt="banner" />
	<Categories name="New Hot" />
</div>

<style>
	.mobile-hide {
		display: block;
	}
	div {
		display: flex;
		flex-direction: column;
		justify-content: center;
		margin-top: 30px;
		margin-left: 30px;
	}
	@media (max-width: 768px) {
		.mobile-hide {
			display: none;
		}
	}
</style>
