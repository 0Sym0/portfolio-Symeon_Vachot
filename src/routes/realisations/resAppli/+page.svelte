<script>
    import {onMount} from "svelte";
    import {base} from "$app/paths";

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
            "/realisations/resappli/resappli1.png",
            "/realisations/resappli/resappli2.png",
            "/realisations/resappli/resappli3.png"
        ]

    let indexActuel = 0;
    function allerA(i) {
        indexActuel = i;
    }

</script>

<h2 class="mb-4">Application ResAppli</h2>
<div class="d-flex align-items-center justify-content-center flex-rows gap-3">
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
    <div class="section rightSections d-flex align-items-center justify-content-center flex-column gap-2px-3" style="width: 30%;">
        <h3>Technologies utilisées</h3>
        <div class="technos d-flex align-items-center justify-content-center flex-rows flex-wrap gap-3 mb-4">
            <div class="glass text-center p-1">HTML</div>
            <div class="glass text-center p-1">CSS</div>
            <div class="glass text-center p-1">JS</div>
            <div class="glass text-center p-1">Laravel</div>
            <div class="glass text-center p-1">Figma</div>
            <div class="glass text-center p-1">MySQL</div>
        </div>
        <h3>Description du projet</h3>
        <p style="text-align: justify">
            Sous la forme d'un véritable projet professionnel, j'ai eu l'opportunité de développer une application de location de salle de formation.
            Développée en équipe, l'objectif de notre application web était d'offrir à chaque utilisateur une interface personnalisée et connectée.
            La disponibilité des salles apparaissait dans un calendrier, les visiteurs avaient des accès différents selon leurs niveaux d'autorisation (admin, client, employé).
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