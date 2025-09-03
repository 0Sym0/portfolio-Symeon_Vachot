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
<section class="glass section topSections my-4 p-4">
    <h1 class="mb-4">Parcours académique</h1>
    <div class="d-grid px-3 column-gap-5 row-gap-3" style="grid-template-columns: 1fr 10px 1fr; grid-template-rows: repeat(3, auto);">
        <div class="glass section leftSections p-3 mx-auto" style=" grid-row:1/2; grid-column:1/2;">
            <h2>BTS SIO</h2>
            <h3>Service Informatique aux Organisation</h3>
            <p>Conçu comme une classe préparatoire au diplôme d’Ingénieur Informatique et Cybersécurité.</p>
            <p>Spécialisé en <b>SLAM</b> (<b>S</b>olutions <b>L</b>ogicielles et <b>A</b>pplications <b>M</b>étiers)</p>
            <i class="mt-1">Institution des Chartreux - Lyon 1 (69), France</i>
        </div>
        <div class="glass section rightSections p-3 mx-auto" style=" grid-row:2/3; grid-column:3/4;">
            <h2>BUT HSE</h2>
            <h3>Hygiène Sécurité Environnement</h3>
            <p>Principes de prévention et de protection des salariés en entreprise,
              connaissance des obligations réglementaires,
              analyse de poste de travail,
              connaissances juridiques (droit du travail, droit de l’environnement)
            </p>
            <i class="mt-1">IUT Lumière Lyon 2 - Bron (69), France</i>
        </div>
        <div class="glass section leftSections p-3 mx-auto" style=" grid-row:3/4; grid-column:1/2;">
            <h2>Baccalauréat général</h2>
            <p>Profil pluridisciplinaire avec les spécialités :<p>
            <ul>
                <li>Histoire Géopolitiques et Sciences Politiques</li>
                <li>Sciences de la Vie et de la Terre</li>
                <li>Option maths complémentaire</li>
            </ul>
            <i class="mt-1">Notre Dame de la Galaure - Saint Bonnet de Galaure (26), France</i>
        </div>
        <div class="glass section bottomSections" style="grid-row:1/5; grid-column:2/3;"></div>
        <div class="section bottomSections d-flex align-items-center justify-content-center flex-column gap-3" style="grid-row:1/2; grid-column:2/3;">
            <div class="evenement glass d-flex"></div>
            <div class="dateEvenement text-center fst-italic">2024 - 2026</div>
        </div>
        <div class="section bottomSections d-flex align-items-center justify-content-center flex-column gap-3" style="grid-row:2/3; grid-column:2/3;">
            <div class="evenement glass d-flex"></div>
            <div class="dateEvenement text-center fst-italic">2021 - 2024</div>
        </div>
        <div class="section bottomSections d-flex align-items-center justify-content-center flex-column gap-3" style="grid-row:3/4; grid-column:2/3;">
            <div class="evenement glass d-flex"></div>
            <div class="dateEvenement text-center fst-italic">2018-2021</div>
        </div>
    </div>
</section>

<style>
    .evenement {
        height:25px;
        width:25px;
        background-color: rgba(255, 255, 255, 0.8);
    }

    .dateEvenement {
        width:200px;
        font-size: 0.75rem;
    }
</style>