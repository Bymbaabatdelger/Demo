<script>
	let img = './icons/Rectangle11.png';
	let fav = './icons/fullHeart.png';
	let minus = './icons/minus-circle.png';
	let back = './icons/backstep.svg';
	let play = './icons/play.svg';
	let forward = './icons/forwardstep.svg';
	let line = './icons/timeline.png';
	let repeat = './icons/repeat_on.png';
    let repeat_off = './icons/repeat_off.svg';
    let repeat_on = './icons/repeat_on.svg';
	let shuffle = './icons/shuffle.svg';
	let volume = './icons/volume-up.svg';
	let meter = './icons/Volumemeter.png';
	let playlist = './icons/Playlist.svg';
	let outlinedFav = './icons/Heart.svg';
    let plus = './icons/plus-circle.png';
    let repeatIcon = repeat;
	let favIcon = fav; 
    let plusIcon = minus
	let isVisible = false;

    function toggleRepeat() {
		repeatIcon = repeatIcon === repeat ? repeat_off || repeat_on :  repeat; 
	}

	function toggleFav() {
		favIcon = favIcon === fav ? outlinedFav : fav; 
	}

    function togglePlus() {
		plusIcon = plusIcon === minus ? plus : minus; 
	}
</script>

<div class:mobile-hide={!isVisible}>
	<div class="container">
		<div class="songName">
			<img class="img" src={img} alt="img" />
			<div class="titles">
				<span class="mmusic">Mmusic</span>
				<span class="song">Таны сонсож буй дуу</span>
			</div>
			<button on:click={toggleFav}>
				<img src={favIcon} alt="fav" class="clickable-icon" />
			</button>
            <button on:click={togglePlus}>
                <img src={plusIcon} alt="minus"  class="clickable-icon" />
            </button>
		</div>
		<div class="line-container">
			<img src={back} alt="back" />
			<img src={play} alt="play" />
			<img src={forward} alt="forward" />
			<span class="time">02:56</span>
			<img src={line} alt="line" />
			<span class="time">03:48</span>
            <button on:click={toggleRepeat}>
                <img src={repeatIcon} alt="repeat"  class="clickable-icon" />
            </button>
			<img class="shuffle" src={shuffle} alt="shuffle" />
		</div>
		<div class="volume-container">
			<span>Д.үг</span>
			<img src={volume} alt="volume" />
			<img src={meter} alt="meter" />
			<img src={playlist} alt="playlist" />
		</div>
	</div>
</div>

<div class="phone-container">
	<div class="songName">
		<img class="img" src={img} alt="img" />
		<div class="titles">
			<span class="song">Нүдэн хээр</span>
			<span class="mmusic">Дуучин Д.Пэрэнлэйлхагва</span>
		</div>
	</div>
	<div class="controller">
		<img src={back} alt="back" />
		<img src={play} alt="play" />
		<img src={forward} alt="forward" />
	</div>
</div>

<style>
	.mobile-hide {
		display: block;
	}
	.container {
		width: 100vw;
		display: flex;
		justify-content: space-between;
		height: 80px;
		background: linear-gradient(to right, #0061ff, #00235b);
		padding-right: 1rem;
	}
	.phone-container {
		display: none;
	}
	.titles {
		display: flex;
		flex-direction: column;
	}
	.songName {
		display: flex;
		align-items: center;
		gap: 10px;
		width: 282px;
		padding: 2px;
	}
	.mmusic {
		color: #fafafa;
		font-size: 12px;
		font-weight: 400;
		font-family: 'Roboto', sans-serif;
	}
	.song {
		color: #ffffff;
		font-size: 14px;
		font-weight: 700;
		font-family: 'Roboto', sans-serif;
	}
	.line-container {
		display: flex;
		align-items: center;
		gap: 10px;
	}
	.volume-container {
		display: flex;
		align-items: center;
		gap: 10px;
	}
	.time {
		color: #a1a1aa;
		font-family: 'Roboto', sans-serif;
		font-size: 14px;
	}
	span {
		color: #d4d4d8;
		font-family: 'Roboto', sans-serif;
		font-size: 14px;
		font-weight: 700;
	}
	button {
		background-color: transparent;
		border: 0;
	}
    .shuffle:hover {
        filter: brightness(0) saturate(100%) invert(1);
    }
	@media (max-width: 768px) {
		.mobile-hide {
			display: none;
		}
		.phone-container {
			display: block;
			width: 100vw;
			display: flex;
			justify-content: space-between;
			align-items: center;
			height: 80px;
			background-color: #664e3d;
			padding-right: 1rem;
		}
		.controller {
			display: flex;
			align-items: center;
			gap: 10px;
		}
	}
</style>
