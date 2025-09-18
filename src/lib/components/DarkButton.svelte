<script>
    export let href = "";
</script>

<!-- Knop -->
<a href={href}>
  <slot/>
</a>

<style>
    a {
        padding: .6em 1em;
        border: 1px solid var(--secondary-text);
        background-color: var(--secondary-background);
        color: var(--third-text);
        transition: .2s ease-in-out;
    }

    a:hover {
        background-color: var(--primary-background);
        color: var(--secondary-text);
        transition: .2s ease-in-out;
    }
</style>