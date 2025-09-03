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
    <h1 class="my-3">Copyright</h1>
    <p>&copy; 2025 Syméon Vachot. Tous droits réservés.</p>
    <h1 class="my-3">Réutilisation</h1>
    <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Possimus voluptatum, deserunt, nisi ipsam facere fuga voluptatem libero obcaecati ratione eum et doloribus iure aliquam fugit eaque minima deleniti sunt quas.</p>
    <h2 class="my-2">Code source</h2>
    <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Distinctio numquam ipsa obcaecati praesentium, quia ducimus provident sequi cumque perspiciatis consequatur consectetur alias, veniam magnam officiis quis odio. Consequuntur, id recusandae?</p>
    <h2 class="my-2">Contenu</h2>
    <p>Il est interdit de copier ou re-publier le contenu de ce site web. Cela inclut les images, mots utilisés ainsi que le code source.</p>
    <h3 class="my-1">Images</h3>
    <p><b>Informations :</b> Les bannières de fond de ce portfolio ont été générées par IA.</p>
</div>

<style>
    h1, h2, h3{
        text-align: start;
    }
</style>