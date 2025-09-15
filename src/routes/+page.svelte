<script>
    let { data } = $props(); // rune die data doorgeeft tussen page.server.js en page.svelte ("magische property")
    import DarkButton from '$lib/components/DarkButton.svelte';

    let { data } = $props();
    const person = data.person;

</script>

<main>
    <div class="left">
        <img src="/images/portret-amber.jpg" alt="" width="200" height="300">
        <section>
            <h3>Contact opnemen</h3>
            <DarkButton href="mailto:amber.schalker@hva.nl">Contact</DarkButton>
        </section>
    </div>

    <div class="right">
        <section class="info">
            <h1>{person.name}</h1>
            <p>{person.bio}</p>
        </section>

        <section class="socials">
            <h2>My socials</h2>
            <div class="share">
                <a href="{person.custom.socials.instagram}"><img src="/images/instagram.svg" alt="Logo Instagram"></a>
                <a href="{person.custom.socials.github}"><img src="/images/github.svg" alt="Logo Github"></a>
                <a href="{person.custom.socials.linkedin}"><img src="/images/linkedin.svg" alt="Logo LinkedIn"></a>
            </div>
            
        </section>
    </div>
    
</main>
