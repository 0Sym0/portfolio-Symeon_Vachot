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
            "/realisations/certification/dossierDeCertification1.png"
        ]

    let indexActuel = 0;
    function allerA(i) {
        indexActuel = i;
    }

</script>

<h2 class="mb-4">Dossier de certification</h2>
<div class="d-flex align-items-center justify-content-center flex-rows gap-3">
    <div class="imagesProjets section leftSections d-flex align-items-center justify-content-center flex-column w-50 gap-5">
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
    <div class="section rightSections d-flex align-items-center justify-content-center flex-column gap-2 w-50 px-3">
        <h3>Description du projet</h3>
        <p style="text-align: justify">
            Rédaction d'un écrit réflexif en 2 étapes ; au début et à la fin de l'année.
            Cela m'a donné à réflechir sur ma place dans le BTS, les différentes forces de ma personnalité, et le lien avec mon projet professionnel.<br>
            J'ai pu voir l'évolution de ma mentalité au fil de la première année afin d'afiner davantage mon projet professionnel.
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
        --glass-bg: rgba(255, 255, 255, 0.45);
    }

    .technos div {
        width: 100px;
    }
</style>