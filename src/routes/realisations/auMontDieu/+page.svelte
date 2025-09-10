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

    const tableauImages =
        [
            "/realisations/auMontDieu/festivalAMD1.png",
            "/realisations/auMontDieu/festivalAMD2.png",
            "/realisations/auMontDieu/festivalAMD3.png",
            "/realisations/auMontDieu/festivalAMD4.png",
            "/realisations/auMontDieu/festivalAMD5.png"
        ]

    let indexActuel = 0;
    function allerA(i) {
        indexActuel = i;
    }

</script>

<h2 class="mb-4">Festival Au Mont Dieu</h2>
<div class="d-flex align-items-center justify-content-center flex-rows gap-3">
    <div class="imagesProjets section leftSections d-flex align-items-center justify-content-center flex-column gap-5" style="width:70%;">
        <img src={tableauImages[indexActuel]} class="w-100 glass" />
        {#if tableauImages.length > 1}
            <div class="section bottomSections d-flex align-items-center justify-content-center flex-rows gap-3">
                {#each tableauImages as img, i}
                    <div class="elem glass d-flex align-items-center justify-content-center {i === indexActuel ? 'active' : ''}" on:click={() => allerA(i)}>
                        {i + 1}
                    </div>
                {/each}
            </div>
        {/if}
    </div>
    <div class="section rightSections d-flex align-items-center justify-content-center flex-column gap-2 px-3" style="width:40%;">
                <h3>Technologies utilisées</h3>
                <div class="technos d-flex align-items-center justify-content-center flex-rows gap-3 mb-4">
                    <div class="glass text-center p-1">HTML</div>
                    <div class="glass text-center p-1">CSS</div>
                    <div class="glass text-center p-1">JS</div>
                </div>
        <h3>Description du projet</h3>
        <p style="text-align: justify">
            Dans le cadre d'une prestation informatique bénévole, j'ai eu l'opportunité de développer un site statique pour un festival chrétien.<br>
            Néophyte dans l'informatique, formé au développement web depuis à peine 6 mois, c'était mon premier projet concret.
            L'objectif était de créer un design innovant, des boutons appel à action, une bonne gestion du responsive design...<br>
            Ce projet à été déterminant dans mon choix de réorientation dans l'informatique.
        </p>
    </div>

</div>

<style>
    h2 {
        text-align: center;
    }

    .elem {
        width: 50px;
        height: 50px;
        border-radius: 50%;
        cursor: pointer;
    }

    .elem.active {
        --glass-bg: rgba(255, 255, 255, 0.5);
    }

    .technos div {
        width: 100px;
        border-radius: 15px;
    }
</style>