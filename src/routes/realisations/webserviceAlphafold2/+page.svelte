<script>
    import {onMount} from "svelte";
    import {base} from "$app/paths";

    const tableauImages =
        [
            "/realisations/npsa-ng/NPSA-NG1.webp",
            "/realisations/npsa-ng/NPSA-NG2.webp",
            "/realisations/npsa-ng/NPSA-NG3.webp",
            "/realisations/npsa-ng/NPSA-NG4.webp",
            "/realisations/npsa-ng/NPSA-NG5.webp"
        ]

    let indexActuel = 0;

    onMount(() => {
        const sections = document.querySelectorAll('.section')
        sections.forEach(section => {
            setTimeout(() => {
                section.classList.add('mountEffect')
            }, 100);
        });

        // Précharger les images
        tableauImages.forEach(chemin => {
            const img = new Image();
            img.src = `${base}${chemin}`;
        });
    });


    function allerA(i) {
        indexActuel = i;
    }

</script>

<h2 class="mb-4">Webservice NPSA-NG</h2>
<div class="containerGeneral d-flex align-items-center justify-content-center flex-rows gap-3">
    <div class="imagesProjets section leftSections d-flex align-items-center justify-content-center flex-column gap-5" style="width: 70%;">
        <img src={base}{tableauImages[indexActuel]} class="w-100 glass" />
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
    <div class="section rightSections d-flex align-items-center justify-content-center flex-column gap-2 px-3" style="width: 30%;">
        <h3>Technologies utilisées</h3>
        <div class="technos d-flex align-items-center justify-content-center flex-rows flex-wrap gap-3 mb-4">
            <div class="glass text-center p-1">HTML</div>
            <div class="glass text-center p-1">CSS</div>
            <div class="glass text-center p-1">JS</div>
            <div class="glass text-center p-1">Python</div>
            <div class="glass text-center p-1">Svelte</div>
        </div>
        <h3>Description du projet</h3>
        <p style="text-align: justify">
            A l'issue de ma première année, j'ai eu l'opportunité de réaliser un stage de 5 semaines au CNRS.<br>
            J'ai notamment pu participer au développement du webservice AlphaFold2 permettant de prédire la structure 3D des protéines.
            Je devais finaliser la communication avec le cluster de calcul et mettre en forme les résultats une fois les données calculées.
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
        border-radius: 15px;
    }

    @media (max-width: 992px) {
        .containerGeneral {
            flex-direction: column-reverse !important;
            align-items: center !important;
            gap: 1.5rem !important;
        }

        .leftSections, .rightSections {
            width: 85% !important;
        }
    }

    @media (max-width: 576px) {
        .leftSections, .rightSections {
            width: 100% !important;
        }
    }
</style>