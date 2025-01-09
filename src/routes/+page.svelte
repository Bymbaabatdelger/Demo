<script>
	import Content from './Content.svelte';
	import Menu from './Menu.svelte';
	import Navbar from './Navbar.svelte';

	let home = './icons/home.svg';
	let search = './icons/search.svg';
	let mmusic = './icons/Mmusic.png';
	let recent = './icons/Recent.svg';
	let favourite = './icons/Heart.svg';
	let plus = './icons/plus-circle.svg';
	let list = './icons/Rectangle8.png';
	let nice = './icons/Rectangle9.png';
	let hamburger = './icons/Frame.png';

	let isSidebarVisible = false;

	const mainMenus = [
		{ name: 'Нүүр', icon: home },
		{ name: 'Хайх', icon: search }
	];

	const myLibraryMenus = [
		{ name: 'Сүүлд сонссон', icon: recent },
		{ name: 'Дуртай', icon: favourite },
		{ name: 'Микс үүсгэх', icon: plus }
	];

	const playlists = [
		{ name: 'Муугүй лист', icon: list },
		{ name: 'Гоё дуунууд', icon: nice }
	];

	function toggleSidebar() {
		isSidebarVisible = !isSidebarVisible;
	}
</script>

<button class="hamburger" on:click={toggleSidebar} aria-label="Toggle menu"><img src={hamburger} alt="menu"/></button>

<aside class:mobile-hide={!isSidebarVisible} aria-labelledby="main-menu">
	<nav>
		<img src={mmusic} alt="Mmusic Logo" />
		<div class="container">
			{#each mainMenus as menu}
				<Menu name={menu.name} icon={menu.icon} />
			{/each}
		</div>
	</nav>
	<p id="main-menu">Миний сан</p>
	<div class="container">
		{#each myLibraryMenus as menu}
			<Menu name={menu.name} icon={menu.icon} />
		{/each}
	</div>
	<hr />
	<div class="container">
		{#each playlists as playlist}
			<Menu name={playlist.name} icon={playlist.icon} />
		{/each}
	</div>
</aside>

<main>
	<Navbar />
	<Content />
</main>

<style>
	aside {
		width: 220px;
		height: 100vh;
		background-color: #27272a;
		position: fixed;
		left: 0;
		top: 0;
		padding: 1rem;
		display: flex;
		flex-direction: column;
		z-index: 999;
	}

	aside img {
		margin-bottom: 40px;
	}

	p {
		color: #525252;
		font-size: 16px;
	}

	.container {
		display: flex;
		flex-direction: column;
		gap: 4px;
	}

	hr {
		width: 100%;
		height: 1px;
		background-color: #52525b;
		border: none;
		margin: 1rem 0;
	}

	.container :global(.menu:hover) {
		background-color: #38383f;
		border-radius: 4px;
		cursor: pointer;
	}

	main {
		margin-left: 220px;
		padding: 1rem;
		background-color: #18181b;
		min-height: 100vh;
	}
	@media (max-width: 768px) {
		.hamburger {
			display: block;
		}

		aside {
			display: flex;
		}

		aside.mobile-hide {
			display: none;
		}

		main {
			margin-left: 0;
		}
	}
</style>
