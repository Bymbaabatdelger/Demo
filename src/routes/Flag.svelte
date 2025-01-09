<script>
	let flag = './icons/flag.png';
	let play = './icons/play.png';
</script>

<div class="mobile-hide">
	<div class="flag-image">
		<img src={flag} alt="flag" />
		<div class="text-container">
			<p>Монгол улсын төрийн дуулал</p>
			<div class="play-container">
				<img class="play-image" src={play} alt="play" />
			</div>
		</div>
	</div>
</div>

<style>
	.mobile-hide {
		display: block;
	}

	p {
		color: white;
		font-size: 14px;
		font-family: 'Roboto', sans-serif;
		font-weight: 600;
		margin: 0;
	}

	.play-container {
		height: 38px;
		width: 38px;
		background-color: #6b7280;
		border-radius: 50%;
		position: relative;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.play-image {
		width: 20px;
		height: 20px;
	}

	.flag-image {
		position: relative;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.text-container {
		position: absolute;
		display: flex;
		align-items: center;
		gap: 60px;
	}
	@media (max-width: 768px) {
		.mobile-hide {
			display: none;
		}
	}
</style>
