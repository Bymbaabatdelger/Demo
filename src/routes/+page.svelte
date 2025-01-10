<script lang="ts">
	import Navbar from './Navbar.svelte';
	import Menu from './Menu.svelte';
	import Content from './Content.svelte';
	import Playing from './Playing.svelte';

	let left = './icons/chevron-left.svg';
	let right = './icons/chevron-right.svg';
	let hamburger = './icons/Frame.svg';
	let isSidebarVisible = false;

	function toggleSidebar() {
		isSidebarVisible = !isSidebarVisible;
	}
</script>

<div class="hero">
	<aside
		class:mobile-hide={isSidebarVisible}
		aria-labelledby="main-menu">
		<nav>
			<img src="./icons/Mmusic.png" alt="Mmusic Logo" />
			<div class="container">
				{#each [{ name: 'Нүүр', icon: './icons/home.svg' }, { name: 'Хайх', icon: './icons/search.svg' }] as menu}
					<Menu name={menu.name} icon={menu.icon} />
				{/each}
			</div>
		</nav>
		<p id="main-menu">Миний сан</p>
		<div class="container">
			{#each [{ name: 'Сүүлд сонссон', icon: './icons/Recent.svg' }, { name: 'Дуртай', icon: './icons/Heart.svg' }, { name: 'Микс үүсгэх', icon: './icons/plus-circle.svg' }] as menu}
				<Menu name={menu.name} icon={menu.icon} />
			{/each}
		</div>
		<hr />
		<div class="container">
			{#each [{ name: 'Муугүй лист', icon: './icons/Rectangle8.png' }, { name: 'Гоё дуунууд', icon: './icons/Rectangle9.png' }] as menu}
				<Menu name={menu.name} icon={menu.icon} />
			{/each}
		</div>
	</aside>

	<main>
		<div class="navbar-container">
			<button class="hamburger" on:click={toggleSidebar} aria-label="Toggle menu">
				<img src={hamburger} alt="menu" />
			</button>
			<div class="lefticon mobile-hide">
				<img class="left" src={left} alt="left" />
				<img class="left" src={right} alt="right" />
			</div>
			<Navbar />
		</div>
		<Content />
	</main>

	<div class="playing-container">
		<Playing />
	</div>
</div>

<style>
	.lefticon {
		padding-left: 2rem;
	}
	.mobile-hide {
		display: none;
	}

	.left:hover {
		filter: brightness(0) saturate(100%) invert(1);
	}
	.hero {
		display: flex;
		flex-direction: column;
		width: 100vw;
		height: 100vh;
	}

	aside {
		width: 220px;
		background-color: #27272a;
		position: fixed;
		left: 0;
		top: 0;
		height: 100%;
		padding: 1rem;
		transform: translateX(-100%);
		transition: transform 0.3s ease-in-out;
		z-index: 999;
	}

	aside.mobile-hide {
		transform: translateX(0);
	}

	main {
		flex: 1;
		padding: 1rem;
		background-color: #18181b;
		overflow-y: auto;
		margin-bottom: 80px; 
	}

	.navbar-container {
		width: 100%;
		display: flex;
		align-items: center;
		justify-content: space-between;
		padding: 0.5rem;
		position: sticky;
		top: 0;
		z-index: 1000;
	}

	.hamburger {
		background: none;
		border: none;
		cursor: pointer;
		z-index: 1001;
		display: block;
	}

	p {
		color: #525252;
		font-size: 16px;
		font-family: 'Roboto', sans-serif;
	}

	hr {
		width: 100%;
		height: 1px;
		background-color: #52525b;
		border: none;
		margin: 1rem 0;
	}

	.playing-container {
		position: fixed;
		bottom: 0;
		width: 100%;
		height: 80px; 
		z-index: 1000;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	@media (min-width: 769px) {
		.hero {
			flex-direction: row;
		}

		main {
			padding-left: 220px;
		}

		.hamburger {
			display: none;
		}

		aside {
			transform: translateX(0);
		}
		.mobile-hide {
			display: block;
		}
	}
</style>
