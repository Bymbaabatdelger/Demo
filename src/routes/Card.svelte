<script>
	let { img, name , style } = $props();
</script>

<div>
	<img style="border-radius: {style};" src={img} alt="img" />
	<p>{name}</p>
</div>

<style>
	div {
		display: flex;
		flex-direction: column;
		gap: 10px;
	}
	img {
		height: 200px;
		width: 200px;
	}
	p {
		color: #a1a1aa;
		font-size: 16px;
		font-family: 'Roboto', sans-serif;
	}
</style>
