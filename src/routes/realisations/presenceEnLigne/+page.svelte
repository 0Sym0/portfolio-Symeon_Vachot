<script>
    import {onMount} from "svelte"
    import {base} from "$app/paths"

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
            "/realisations/presenceEnLigne/immersicorp1.png",
            "/realisations/presenceEnLigne/immersicorp2.png",
            "/realisations/presenceEnLigne/immersicorp3.png",
            "/realisations/presenceEnLigne/immersicorp4.png",
            "/realisations/presenceEnLigne/immersicorp5.png"
        ]

    let indexActuel = 0;
    function allerA(i) {
        indexActuel = i;
    }

</script>

<h2 class="mb-4">Présence en ligne</h2>
<div class="d-flex align-items-center justify-content-center flex-rows gap-3">
    <div class="imagesProjets section leftSections d-flex align-items-center justify-content-center flex-column gap-5" style="width:70%;">
        <img src={base}{tableauImages[indexActuel]} class="w-100" />
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
    <div class="section rightSections d-flex align-items-center justify-content-center flex-column gap-2 px-3" style="width:30%;">
        <h3>Technologies utilisées</h3>
        <div class="technos d-flex align-items-center justify-content-center flex-rows flex-wrap gap-3 mb-4">
            <div class="glass text-center p-1">Wordpress</div>
            <div class="glass text-center p-1">Elementor</div>
            <div class="glass text-center p-1">Yoast SEO</div>
            <div class="glass text-center p-1">Brevo</div>
        </div>
        <h3>Description du projet</h3>
        <p style="text-align: justify">
            Dans le cadre de mon cours de présence en ligne, j'ai eu l'opportunité de créér un site web ainsi qu'une entreprise fictive.<br>
            L'objectif de ce travail était de simuler une véritable entreprise ayant des objectifs précis (KPI).
            J'ai alors eu l'occasion d'optimsier le classement dans les moteurs de recherche (ranking), créer des campagnes d'emailing personnalisés,
            suivis des indices (KPI), et utilisation d'Elementor pour la création du site web.
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
</style>