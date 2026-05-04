<script>
    import {onMount} from "svelte";
    import {base} from "$app/paths";

    const tableauImages =
        [
            "/realisations/lumi/lumi1.webp",
            "/realisations/lumi/lumi2.webp",
        ];

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
<h2 class="mb-4">Application Web LUMI</h2>
<div class="containerGeneral d-flex align-items-center justify-content-center flex-rows gap-3">
    <div class="imagesProjets section leftSections d-flex align-items-center justify-content-center flex-column gap-5" style="width:70%;">
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
    <div class="section rightSections d-flex align-items-center justify-content-center flex-column gap-2 px-3" style="width:40%;">
                <h3>Technologies utilisées</h3>
                <div class="technos d-flex align-items-center justify-content-center flex-rows flex-wrap gap-3 mb-4">
                    <div class="glass text-center p-1">Java</div>
                    <div class="glass text-center p-1">Spring&nbsp;Boot</div>
                    <div class="glass text-center p-1">Maven</div>
                    <div class="glass text-center p-1">JOOQ</div>
                    <div class="glass text-center p-1">Liquibase</div>
                    <div class="glass text-center p-1">Angular</div>
                </div>
        <h3>Description du projet</h3>
        <p style="text-align: justify">
            Dans le cadre de mon stage de seconde année chez EDF, j'ai eu l'opportunité de développer
            et d'améliorer un socle technique applicatif nommé Lumi.
            L'objectif principal de ce projet était de faire de ce socle une application blanche,
            réutilisable pour l'ensemble des futurs projets d'EDF, avec une mise en place concrète des
            bonnes pratiques de développement et d'architectures logicielles strictes.
            Dans ce contexte, ma mission initiale consistait à concevoir et implémenter un "tracker" (suivi)
            d'usage et de performance. Ce dernier devait être appliquable à d’autres classes ou
            méthodes avec le moins de code possible.
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