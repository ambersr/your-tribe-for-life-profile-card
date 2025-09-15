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

<style>
	header {
		display: flex;
		align-items: center;
		justify-content: space-between;
		padding: 1em 0em;
		position: sticky;
		top: 0;
		background-color: var(--secondary-background);

		@media screen and (min-width: 900px) {
            padding: 1em 2em;
        }
	}

	a h2{
		color: var(--third-text);
	}

	nav {
		display: flex;
		gap: 1em;
		
		@media screen and (min-width: 900px) {
         gap: 3em;
     }
	}

	nav a:hover {
		text-decoration: underline;
	}
</style>
