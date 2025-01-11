<script>
	import Categories from './Categories.svelte';
	import Suggests from './Suggests.svelte';

	let banner = './icons/banner.png';
	let bannersmall = './icons/bannersmall.png';
	let isBannerVisible = false;
</script>

<div>
	<img class:mobile-hide={!isBannerVisible} src={banner} alt="banner" />
	<img class="bannersmall" src={bannersmall} alt="full" />
	<Categories name="New Hot" />
	<Suggests/>
</div>

<style>
	.mobile-hide {
		display: block;
	}
	.bannersmall {
		display: none;
	}
	div {
		display: flex;
		flex-direction: column;
		justify-content: center;
		padding-left: 3rem;
		padding-top: 3rem;
	}
	@media (max-width: 768px) {
		.mobile-hide {
			display: none;
		}
		div {
			margin: 1rem;
			padding: 0;
		}
		.bannersmall {
			display: block;
		}
	}
</style>
