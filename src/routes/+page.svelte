<script>
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

<style>
    main {
        background-color: var(--primary-background);
        padding: 2em;
        width: 100%;
        display: flex;
        flex-direction: column-reverse;
        gap: 2em;
        margin: 1em 0 2em 0;

        @media screen and (min-width: 900px) {
            flex-direction: row;
             width: 50em;
             margin: auto;
             gap: 4em;

             p {
                width: 80%;
             }
        }
    }

    .left {
        display: flex;
        flex-direction: column;
        gap: 1em;
        position: relative;
        align-items: center;
    }

    .left img {
        width: 100%;
        height: auto;
        object-fit: cover;
        object-position: 0% 10%;

         @media screen and (min-width: 900px) {
            width: auto;
        }
    }

    .left section {
        background-color: var(--secondary-background);
        display: flex;
        align-items: center;
        position: absolute;
        bottom: 1em;
        padding: .5em .5em .5em 1em;
        gap: 1em;
    }

    .left h3 {
        color: var(--third-text);
        margin: 0 0 -.2em 0;
    }
    
    .right {
        display: flex;
        flex-direction: column;
        gap: 1.5em;

         @media screen and (min-width: 900px) {
            justify-content: space-between;
        }
    }

    .socials {
        display: flex;
        flex-direction: column;
        flex-wrap: wrap;
    }

    .share {
        display: flex;
        gap: .5em;
    }

    .right a {
        background-color: var(--secondary-background);
        padding: .5em;
        display: flex;
        align-items: center;
    }
</style>