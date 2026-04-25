<script>
    import {onMount} from "svelte";
    import {base} from "$app/paths";

    const tableauImages =
        [
            "/realisations/ppeWeb/ppeWeb1.webp",
            "/realisations/ppeWeb/ppeWeb2.webp",
            "/realisations/ppeWeb/ppeWeb3.webp",
            "/realisations/ppeWeb/ppeWeb4.webp",
            "/realisations/ppeWeb/ppeWeb5.webp",
            "/realisations/ppeWeb/ppeWeb6.webp",
            "/realisations/ppeWeb/ppeWeb7.webp",
            "/realisations/ppeWeb/ppeWeb8.webp"
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

<h2 class="mb-4">PPE web : SAAS de gestion d'établissement scolaire</h2>
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
            <div class="glass text-center p-1">HTML</div>
            <div class="glass text-center p-1">CSS</div>
            <div class="glass text-center p-1">JS</div>
            <div class="glass text-center p-1">Laravel</div>
            <div class="glass text-center p-1">Docker</div>
            <div class="glass text-center p-1">MariaDB</div>
        </div>
        <h3>Description du projet</h3>
        <p style="text-align: justify">
            Dans le cadre des Projets Personnalisés Encadrés (PPE) de ma formation, j'ai pris la décision de crééer une application web de gestion d'établissement scolaire.
            Les fonctionnalités principales de l'application sont les suivantes : onboarding de configuration initiale guidée, gestion des effectifs (enseignants, élèves), gestion des locaux (salles, bâtiments, capacité, type de salles),
            attribution des élèves et des enseignants aux classes, modélisation des rythmes scolaires (heure de début, durée des cours, temps de pause, etc.), définition des programmes par niveau d'enseignement,
            gestion des spécialités et options des élèves, etc.
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