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

<section class="glass section topSections" id="competences">
    <h1 class=" section topSections w-100 my-4">Compétences</h1>
    <div class="d-grid p-4" style="grid-template-columns: repeat(20, 1fr); grid-template-rows: repeat(20, 1fr);">
        <div class="glass section leftSections d-flex justify-content-around flex-column w-100 p-3" style=" grid-row:1/9; grid-column:1/12;">
            <h2>Web</h2>
            <div class="containerCompetences d-flex align-items-center justify-content-center flex-wrap flex-rows gap-3">
                <div class="glass element d-flex align-items-center justify-content-center gap-2">
                    <img src="/logoCompetences/laravel.png" width="30" height="30">
                    <span>Laravel</span>
                </div>
                <div class="glass element d-flex align-items-center justify-content-center gap-2">
                    <img src="/logoCompetences/svelte.png" width="30" height="30">
                    <span>Svelte</span>
                </div>
                <div class="glass element d-flex align-items-center justify-content-center gap-2">
                    <img src="/logoCompetences/figma.png" width="30" height="30">
                    <span>Figma</span>
                </div>
                <div class="glass element d-flex align-items-center justify-content-center gap-2">
                    <img src="/logoCompetences/bootstrap.png" width="30" height="30">
                    <span>Boostrap</span>
                </div>
                <div class="glass element d-flex align-items-center justify-content-center gap-2">
                    <img src="/logoCompetences/tailwind_CSS.png" width="30" height="30">
                    <span>Tailwind CSS</span>
                </div>
            </div>
        </div>
        <div class="glass section rightSections d-flex justify-content-around flex-column w-100 p-3" style=" grid-row:1/15; grid-column:13/21;">
            <h2>Programmation</h2>
            <div class="containerCompetences d-flex align-items-center justify-content-center flex-wrap flex-rows gap-3">
                <div class="glass element d-flex align-items-center justify-content-center gap-2">
                    <img src="/logoCompetences/PHP.png" width="30" height="30">
                    <span>PHP</span>
                </div>
                <div class="glass element d-flex align-items-center justify-content-center gap-2">
                    <img src="/logoCompetences/python.png" width="30" height="30">
                    <span>Python</span>
                </div>
                <div class="glass element d-flex align-items-center justify-content-center gap-2">
                    <img src="/logoCompetences/c-sharp.png" width="30" height="30">
                    <span>C#</span>
                </div>
            </div>
        </div>
        <div class="glass section leftSections d-flex justify-content-around flex-column w-100 p-3" style=" grid-row:10/21; grid-column:1/8;">
            <h2>DevOps</h2>
            <div class="containerCompetences d-flex align-items-center justify-content-center flex-wrap flex-rows gap-3">
                <div class="glass element d-flex align-items-center justify-content-center gap-2">
                    <img src="/logoCompetences/docker.png" width="30" height="30">
                    <span>Docker</span>
                </div>
                <div class="glass element d-flex align-items-center justify-content-center gap-2">
                    <img src="/logoCompetences/gitHub.png" width="30" height="30">
                    <span>Github</span>
                </div>
                <div class="glass element d-flex align-items-center justify-content-center gap-2">
                    <img src="/logoCompetences/gitLab.png" width="30" height="30">
                    <span>GitLab</span>
                </div>
            </div>
        </div>
        <div class="glass section rightSections d-flex justify-content-around flex-column w-100 p-3" style=" grid-row:16/21; grid-column:9/21;">
            <h2>Autres</h2>
            <div class="containerCompetences d-flex align-items-center justify-content-center flex-wrap flex-rows gap-3">
                <div class="glass element d-flex align-items-center justify-content-center gap-2">
<!--                    <img width="30" height="30">-->
                    <span>Wordpress</span>
                </div>
                <div class="glass element d-flex align-items-center justify-content-center gap-2">
<!--                    <img width="30" height="30">-->
                    <span>Référencement</span>
                </div>
                <div class="glass element d-flex align-items-center justify-content-center gap-2">
<!--                    <img width="30" height="30">-->
                    <span>E-mailing</span>
                </div>
            </div>
        </div>
    </div>
</section>

<style>
    .containerCompetences .element {
        padding: 8px;
        border-radius: 7px;
        transition: all 0.2s ease;
        background: none;
    }

    .element {
        width: fit-content;
    }
</style>