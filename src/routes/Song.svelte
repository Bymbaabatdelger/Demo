<script>
	let { img, songName, color } = $props();
</script>

<div class="container">
	<img src={img} alt="img" />
	<div style="background-color: {color};" class="songName-container">
		<p>{songName}</p>
	</div>
</div>

<style>
	.container {
		display: flex;
		border-radius: 15px;
	}
	.songName-container {
		display: flex;
		align-items: center;
		justify-content: center;
		margin: auto;
		width: 250px;
		height: 100px;
		border-top-right-radius: 15px;
		border-bottom-right-radius: 15px;
	}
	p {
		color: #fff;
		font-size: 16px;
		font-family: 'Roboto', sans-serif;
	}
</style>
