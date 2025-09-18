<script>
    // Import onMount en GSAP
    import { onMount } from 'svelte';
    import gsap from 'gsap';

    // Import component
    import DarkButton from '$lib/components/DarkButton.svelte';

    // Import afbeeldingen
    import github from '$lib/assets/github.svg';
    import instagram from '$lib/assets/instagram.svg';
    import mail from '$lib/assets/mail.svg';
    import linkedin from '$lib/assets/linkedin.svg';
    import portret from '$lib/assets/portret-amber.jpg';


    let { data } = $props();

    // Person data ophalen
    const person = data.person;

    // Hier start de tilt animatie
    let draggableElement = 'main'

    // Wanneer de pagina geladen is wordt de tilt animatie uitgevoerd
    onMount(() => {
        // Alleen op schermbreedte vanaf 900px
        if (window.innerWidth > 900) {
            // Bij hover over de main 
            window.addEventListener('mousemove', (animation) => {
                const x = (animation.clientX / window.innerWidth - 0.5) * 100;
                const y = (animation.clientY / window.innerHeight - 0.5) * 100;

                // Tilt effect met GSAP
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
    <!-- Responsive mugshot -->
    <picture>
        <source 
            srcset="
                {portret}?format=avif&width=50 50w,
                {portret}?format=avif&width=100 100w,
                {portret}?format=avif&width=200 200w
            "
            sizes="
                (max-width: 600px) 50px,
                (max-width: 1200px) 100px,
                200px
            "
            type="image/avif"
        />
        <source 
            srcset="
                {portret}?format=webp&width=50 50w,
                {portret}?format=webp&width=100 100w,
                {portret}?format=webp&width=200 200w
            "
            sizes="
                (max-width: 600px) 50px,
                (max-width: 1200px) 100px,
                200px
            "
            type="image/webp"/>
            <img
                src="{portret}?format=png&width=100"
                alt="Avatar van {person.name}"
                width="50"
                height="50"
                class="avatar-img"
                fetchpriority="high"/>           
    </picture>

    <!-- Contact opnemen -->
    <section>
        <h3>Contact opnemen</h3>
        <DarkButton href="mailto:amber.schalker@hva.nl">Contact</DarkButton>
    </section>
</div>

<div class="right">
    <!-- Extra informatie over mij -->
    <section class="info">
        <h1>{person.name}</h1>
        <p>{person.bio}</p>
    </section>

    <!-- Social media -->
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

    .left picture {
        width: 100%;
    }

    .left img {
        width: 100%;
        height: auto;
        object-fit: cover;
        object-position: 0% 10%;
    }

    @media screen and (min-width: 900px) {
        .left img {
            width: 20em;
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