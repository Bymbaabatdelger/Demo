<script>
	let { img, name } = $props();
</script>

<div>
	<img src={img} alt="img" />
	<p>{name}</p>
</div>

<style>
	div {
		display: flex;
		flex-direction: column;
		gap: 10px;
	}
	p {
		color: #a1a1aa;
		font-size: 16px;
		font-family: 'Roboto', sans-serif;
	}
</style>
