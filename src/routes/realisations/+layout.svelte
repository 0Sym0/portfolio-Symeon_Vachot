<script>
    import {onMount} from "svelte";

    onMount(() => {

        const sections = document.querySelectorAll('.section')
        sections.forEach(section => {
            setTimeout(() => {
                section.classList.add('mountEffect')
            }, 100);
        });
    });
</script>

<section class="glass section topSections my-4 p-4" id="realisations">
    <h1 class="m-4">Réalisations</h1>
    <slot />
</section>