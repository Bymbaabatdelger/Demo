<script>
	let bell = './icons/bell.svg';
    let fullbell = './icons/bell.svg';
    let isBellVisible= false;
</script>

<div class:mobile-hide={!isBellVisible}>
    <div class="bell-container mobile-hide">
        <img class="bell-image" src={bell} alt="bell" />
    </div>
</div>
<img class="fullbell " src={fullbell} alt="full"/>


<style>
    .mobile-hide {
		display: block;
	}
	.bell-container {
		height: 38px;
		width: 38px;
		background-color: #262626;
		border-radius: 50%;
		position: relative;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.bell-image {
		width: 20px;
		height: 20px;
	}
    .fullbell{
        display: none;
    }
    @media (max-width: 768px) {
        div {
			display: flex;
		}

		div.mobile-hide {
			display: none;
		}
        .fullbell {
            display: block;
        }
	}
</style>
