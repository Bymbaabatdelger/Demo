<script>
let profile = './icons/profile.png';
let down = './icons/chevron-down.png';
</script>
<div>
   <div class="profile-container">
    <img class="profile" src={profile} alt="profile"/>
    <p class="mobile-hide">Хэрэглэгч</p>
   </div>
    <img class="down mobile-hide" src={down} alt="down"/>
</div>
<style>
    .profile {
        height: 38px;
        width: 38px;
    }
    .down {
        height: 20px;
        width: 20px;
    }
    p{
        color: white;
        font-size: 14px;
        font-family: 'Roboto', sans-serif;
        font-weight: 700;
    }
    div {
        display: flex;
        align-items: center;
        background-color: #27272A;
        border-radius: 35px;
        gap: 40px;
        padding-inline: 2px;
    }
    .profile-container {
        display: flex;
        gap: 10px;
    }
    .mobile-hide {
		display: block;
	}
    @media (max-width: 768px) {
		.mobile-hide {
			display: none;
		}
        div{
            background-color: transparent;
        }
	}
</style>