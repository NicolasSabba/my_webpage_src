<script>
	// Deps
	import Navbar from './components/Navbar.svelte';
	import Footer from './components/Footer.svelte';
	
	// Content
	import Home from './components/Home.svelte'
	import Me from './components/Me.svelte'
	import Projects from './components/Projects.svelte'
	import Showcase from './components/Showcase.svelte'
	import Blog from './components/Blog.svelte'

	// Variables
	let tab = '/';

	const rutas = {
		'/': Home,
		'/#': Home,
		'me' : Me,
		'projects': Projects,
		'blog': Blog,
		'showcase': Showcase,
	}

	if (window.location.href.split('/#/')[1]) {
		tab = window.location.href.split('/#/')[1];
	}

</script>

<style>
	:global(body) {
		min-width: 1100px;
		height: max-content;
		padding: 0px;
		margin: 0px;
		background-color: var(--background-color);
		font-family: Ubuntu;
	}

	:global(:root){
		--background-color: #4D4637;
		--background-shadow-1: #463A22;
		--background-shadow-2: #3A2E12;
		--background-light-1: #877C63;
		--background-light-2: #B3A78C;
		
		--navbar-color: #877C63;
		--navbar-text-shadow: #333333;
		
		--text : #F0C12D;
		--text-dark: #333;
	}

	@media (min-width: 1100px) {
		main {
			max-width: none;
		}
	}
</style>

<svelte:head>
	<title>Nicolas C. Sabbatini V.</title>
	<link rel="stylesheet" type="text/css" href="//fonts.googleapis.com/css?family=Ubuntu" />
	<script src="https://kit.fontawesome.com/fa0aa00198.js" crossorigin="anonymous"></script>
</svelte:head>

<body>
	<Navbar bind:active={tab}/>
	<svelte:component this={rutas[tab]}/>
	<Footer/>
</body>
