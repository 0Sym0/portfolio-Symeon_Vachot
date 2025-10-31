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

<section class="glass section topSections my-4 p-4" id="veille">
    <h1>Veille technologique</h1>
<!--    <p>Dernières découvertes...</p>-->
    <p style="text-align:center;">Section à venir, soyez patient !</p>
</section>