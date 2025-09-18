<script>
	import favicon from '$lib/assets/favicon.svg';
	import DarkButton from '$lib/components/DarkButton.svelte';
	import '$lib/assets/styles.css'

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<a href="#main" class="skip-link">Ga naar content</a>

<header>
	<a href="/"><h2>AS</h2></a>
	<nav>
		<a href="https://github.com/ambersr?tab=repositories">Projecten</a>
		<a href="https://i-love-web-degg.onrender.com/">Portfolio</a>
	</nav>

	<DarkButton href="mailto:amber.schalker@hva.nl">Contact</DarkButton>
</header>

<main id="main">
	{@render children?.()}
</main>

<style>
	main {
        background-color: var(--primary-background);
        padding: 2em;
        width: 100%;
        display: flex;
        flex-direction: column-reverse;
        gap: 2em;
        margin: 1em 0 2em 0;
    }

	@media screen and (min-width: 900px) {
		main {
			 flex-direction: row;
             width: 50em;
             margin: auto;
             gap: 4em;

             p {
                width: 80%;
             }
		}
    }

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
