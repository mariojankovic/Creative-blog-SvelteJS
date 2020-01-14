<script>
	import Home from './Components/Home/Home.svelte';
	import About from './Components/About/About.svelte';
	import Blog from './Components/Blog/Blog.svelte';
	import MediaArt from './Components/MediaArt/MediaArt.svelte';
	import Poetry from './Components/Poetry/Poetry.svelte';

	let index = 0;
	const components = [
		Home,
		Blog,
		MediaArt,
		About,
		Poetry
	];
	function handleSwitch(event){
		console.log('fired')
		index = event.detail.index;
	} 
</script>

<main>
	<h1>A Creatives Blog</h1>
	<svelte:component this={components[index]} on:switchMainComponent={handleSwitch} />
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		font-size: 4.5em;
		font-weight: 100;
		letter-spacing: 1px
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>