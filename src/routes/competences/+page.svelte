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
</script>

<section class="glass section topSections" id="competences">
    <h1 class=" section topSections w-100 my-4">Compétences</h1>
    <div class="d-grid p-4" style="grid-template-columns: repeat(20, 1fr); grid-template-rows: repeat(20, 1fr);">
        <div class="glass section topSections d-flex justify-content-around flex-column w-100 p-3" style=" grid-row:1/9; grid-column:1/12;">
            <h2>Web</h2>
            <div class="containerCompetences d-flex align-items-center justify-content-center flex-wrap flex-rows gap-3">
                <div class="glass element d-flex align-items-center justify-content-center gap-2">
                    <img src="{base}/logoCompetences/laravel.png" width="30" height="30">
                    <span>Laravel</span>
                </div>
                <div class="glass element d-flex align-items-center justify-content-center gap-2">
                    <img src="{base}/logoCompetences/svelte.png" width="30" height="30">
                    <span>Svelte</span>
                </div>
                <div class="glass element d-flex align-items-center justify-content-center gap-2">
                    <img src="{base}/logoCompetences/angular.png" width="30" height="30">
                    <span>Angular</span>
                </div>
                <div class="glass element d-flex align-items-center justify-content-center gap-2">
                    <img src="{base}/logoCompetences/figma.png" width="30" height="30">
                    <span>Figma</span>
                </div>
                <div class="glass element d-flex align-items-center justify-content-center gap-2">
                    <img src="{base}/logoCompetences/bootstrap.png" width="30" height="30">
                    <span>Boostrap</span>
                </div>
                <div class="glass element d-flex align-items-center justify-content-center gap-2">
                    <img src="{base}/logoCompetences/tailwind_CSS.png" width="30" height="30">
                    <span>Tailwind CSS</span>
                </div>
            </div>
        </div>
        <div class="glass section rightSections d-flex justify-content-around flex-column w-100 p-3" style=" grid-row:1/15; grid-column:13/21;">
            <h2>Programmation</h2>
            <div class="containerCompetences d-flex align-items-center justify-content-center flex-wrap flex-rows gap-3">
                <div class="glass element d-flex align-items-center justify-content-center gap-2">
                    <img src="{base}/logoCompetences/PHP.png" width="30" height="30">
                    <span>PHP</span>
                </div>
                <div class="glass element d-flex align-items-center justify-content-center gap-2">
                    <img src="{base}/logoCompetences/python.png" width="30" height="30">
                    <span>Python</span>
                </div>
                <div class="glass element d-flex align-items-center justify-content-center gap-2">
                    <img src="{base}/logoCompetences/c-sharp.png" width="30" height="30">
                    <span>C#</span>
                </div>
                <div class="glass element d-flex align-items-center justify-content-center gap-2">
                    <img src="{base}/logoCompetences/java.png" width="30" height="30">
                    <span>Java</span>
                </div>
                <div class="glass element d-flex align-items-center justify-content-center gap-2">
                    <img src="{base}/logoCompetences/spring-boot.png" width="30" height="30">
                    <span>Spring Boot</span>
                </div>
            </div>
        </div>
        <div class="glass section leftSections d-flex justify-content-around flex-column w-100 p-3" style=" grid-row:10/21; grid-column:1/8;">
            <h2>DevOps</h2>
            <div class="containerCompetences d-flex align-items-center justify-content-center flex-wrap flex-rows gap-3">
                <div class="glass element d-flex align-items-center justify-content-center gap-2">
                    <img src="{base}/logoCompetences/docker.png" width="30" height="30">
                    <span>Docker</span>
                </div>
                <div class="glass element d-flex align-items-center justify-content-center gap-2">
                    <img src="{base}/logoCompetences/gitHub.png" width="30" height="30">
                    <span>Github</span>
                </div>
                <div class="glass element d-flex align-items-center justify-content-center gap-2">
                    <img src="{base}/logoCompetences/gitLab.png" width="30" height="30">
                    <span>GitLab</span>
                </div>
            </div>
        </div>
        <div class="glass section bottomSections d-flex justify-content-around flex-column w-100 p-3" style=" grid-row:16/21; grid-column:9/21;">
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

    img  {
        box-shadow: none;
    }

    @media (max-width: 1024px) {
        .d-grid {
            display: flex !important;
            flex-direction: column;
            align-items: center;
            gap: 1.5rem;
        }

        .d-grid > div {
            grid-column: auto !important;
            grid-row: auto !important;
            width: 100% !important;
            max-width: 700px;
        }
    }

    @media (max-width: 576px) {
        .d-grid > div {
            padding: 1rem !important;
        }

        h1, h2 {
            text-align: center;
        }

        .containerCompetences {
            flex-direction: column;
            gap: 0.75rem;
        }
    }
</style>