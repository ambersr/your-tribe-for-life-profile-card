<script>
	import favicon from '$lib/assets/favicon.svg';
	import DarkButton from '$lib/components/DarkButton.svelte';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<header>
	<a href="/"><h2>AS</h2></a>
	<nav>
		<a href="https://github.com/ambersr?tab=repositories">Projecten</a>
		<a href="https://i-love-web-degg.onrender.com/">Portfolio</a>
	</nav>

	<DarkButton href="mailto:amber.schalker@hva.nl">Contact</DarkButton>
</header>

{@render children?.()}
