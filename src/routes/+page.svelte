<script>
    import { onMount } from 'svelte';
    import gsap from 'gsap';
    import DarkButton from '$lib/components/DarkButton.svelte';
    import github from '$lib/assets/github.svg';
    import instagram from '$lib/assets/instagram.svg';
    import mail from '$lib/assets/mail.svg';
    import linkedin from '$lib/assets/linkedin.svg';
    import portret from '$lib/assets/portret-amber.jpg';


    let { data } = $props();
    const person = data.person;

    let draggableElement = 'main'

    onMount(() => {
        if (window.innerWidth > 900) {
            window.addEventListener('mousemove', (e) => {
                const x = (e.clientX / window.innerWidth - 0.5) * 100;
                const y = (e.clientY / window.innerHeight - 0.5) * 100;

                gsap.to(draggableElement, {
                    rotationY: x,
                    rotationX: -y,
                    transformOrigin: 'center center',
                    ease: 'power2.out',
                    duration: 0.5,
                });
            });
        }
    });
</script>

    <div class="left">
        <img src="{portret}" alt="" width="200" height="300">
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
                <a href="{person.custom.socials.instagram}"><img src="{instagram}" alt="Logo Instagram"></a>
                <a href="{person.custom.socials.github}"><img src="{github}" alt="Logo Github"></a>
                <a href="{person.custom.socials.linkedin}"><img src="{linkedin}" alt=""></a>
            </div>
            
        </section>
    </div>

<style>
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