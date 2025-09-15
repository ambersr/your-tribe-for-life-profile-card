<script>
    let { data } = $props(); // rune die data doorgeeft tussen page.server.js en page.svelte ("magische property")
    import DarkButton from '$lib/components/DarkButton.svelte';

    const person = data.person; 

</script>

<h1>{person.name}</h1>
<p>{person.bio}</p>
<a href="{person.custom.socials.instagram}">Instagram</a>
<a href="{person.custom.socials.github}">github</a>
<a href="{person.custom.socials.linkedin}">linkedin</a>            <DarkButton href="mailto:amber.schalker@hva.nl">Contact</DarkButton>
