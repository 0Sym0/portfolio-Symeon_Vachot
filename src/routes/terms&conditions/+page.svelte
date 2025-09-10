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

<div class="glass section bottomSections p-3">
    <h2 class="my-3">Copyright</h2>
    <p>&copy; 2025 Syméon Vachot. Tous droits réservés.</p>
    <h2 class="my-3">Réutilisation</h2>
    <p>
        L’ensemble des éléments présents sur ce portfolio (structure, design, textes, code et médias) est protégé par le droit d’auteur et le droit de la propriété intellectuelle.
        Toute réutilisation, modification, reproduction, diffusion ou exploitation commerciale, totale ou partielle, sans autorisation écrite préalable, est strictement interdite.
        Une utilisation à des fins pédagogiques ou personnelles non commerciales peut être tolérée à condition de citer l’auteur et de ne pas altérer le contenu.
    </p>
    <h2 class="my-2">Code source</h2>
    <p>
        Le code source de ce portfolio est protégé par le droit d’auteur.
        Il ne peut être copié, redistribué ou intégré dans un projet tiers qu’après accord écrit de l’auteur.
    </p>
    <h2 class="my-2">Contenu</h2>
    <p>
        Le contenu rédactionnel, les textes, et la présentation sont la propriété exclusive de l’auteur.
        Toute reproduction, même partielle, sans autorisation est interdite.
        La citation courte (dans la limite du droit de citation et avec mention claire de l’auteur) reste possible.
    </p>
    <h2 class="my-1">Images</h2>
    <p>
        Certaines images et bannières présentes sur ce site ont été générées par intelligence artificielle, tandis que d’autres proviennent de créations personnelles ou de ressources libres de droits.
        Dans tous les cas, elles sont réservées à un usage strictement personnel et ne peuvent être copiées, modifiées ou réutilisées sans accord préalable.
        Toute exploitation non autorisée pourrait constituer une violation du droit d’auteur ou du droit à l’image.
    </p>
</div>

<style>
    h1, h2, h3{
        text-align: start;
    }
</style>