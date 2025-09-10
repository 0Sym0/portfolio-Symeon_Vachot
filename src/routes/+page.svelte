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

<svelte:head>
    <meta name="description" content="A FAIRE">
</svelte:head>

<h1 class="glass section topSections text-center p-3">Bonjour, et bienvenue sur mon portfolio&nbsp;!</h1>
<div class="containerPresentation d-flex align-items-center justify-content-center flex-row gap-3">
    <div class="glass section leftSections text-center p-3 d-flex align-items-center justify-content-center flex-column">
        <img src="/photoAccueil.jpg" alt="Photo de Syméon Vachot" class="rounded-4">
    </div>
    <div class="glass section rightSections text-center p-3 d-flex align-items-center justify-content-center flex-column">
        <h3 class="text-center p-3">Je suis Syméon Vachot, futur développeur informatique.</h3>
<!--        <p>Vous ne vous êtes pas retrouvés sur mon portfolio par hasard, alors commencons au plus vite !<br>-->
        <p>Réorienté depuis peu au sein du BTS SIO de l'Institution des Chartreux, j'aspire à devenir développeur.
        Je présente ici mes différentes créations et travaux, mon parcours, mes passions...
        </p>
    </div>
</div>

<p class="glass section bottomSections text-center p-3">
    Découvrez mon <a href="formation">parcours académique</a>, mes <a href="realisations">réalisations académiques ou personnelles</a>, mes <a href="competences">compétences</a> et d'autres sections pour me connaitre davantage !<br>
    Bonne visite !
</p>


<style>
    .containerPresentation {
        max-width: 1100px;
    }
    img {
        width: 300px;
        margin-bottom: 1rem;
    }
</style>