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

<div class="d-flex justify-content-center align-items-start gap-4 flex-row w-100">
    <div class="section leftSections d-flex justify-content-around flex-column w-100 px-3 py-4">
        <h2 class="mb-4">Projets académiques</h2>
        <div class="containerCompetences d-flex align-items-center justify-content-center flex-wrap flex-rows gap-4">
            <a href="{base}/realisations/dossierDeCertification" class="glass element projet d-flex align-items-center justify-content-center flex-column gap-3 p-4">
               <h3 class="text-center">Dossier de certification</h3>
                <div>
                      <img src="{base}/realisations/certification/dossierDeCertification1.webp" class="w-100">
                </div>
            </a>
            <a href="{base}/realisations/presenceEnLigne" class="glass element projet d-flex align-items-center justify-content-center flex-column gap-3 p-4">
                <h3 class="text-center">Présence en ligne</h3>
                <div>
                    <img src="{base}/realisations/presenceEnLigne/immersicorp1.webp" class="w-100">
                </div>
            </a>
            <a href="{base}/realisations/resAppli"  class="glass element projet d-flex align-items-center justify-content-center flex-column gap-3 p-4">
                <h3 class="text-center">Application ResAppli</h3>
                <div>
                    <img src="{base}/realisations/resappli/resappli1.webp" class="w-100">
                </div>
            </a>
            <a href="{base}/realisations/ppeWeb"  class="glass element projet d-flex align-items-center justify-content-center flex-column gap-3 p-4">
                <h3 class="text-center">PPE Web : SAAS de gestion d'établissement scolaire</h3>
                <div>
                    <img src="{base}/realisations/ppeWeb/ppeWeb3.webp" class="w-100">
                </div>
            </a>
        </div>
    </div>
    <div class="section rightSections d-flex justify-content-around flex-column w-100 px-3 py-4">
        <h2 class="mb-4">Projets professionnels</h2>
        <div class="containerCompetences d-flex align-items-center justify-content-center flex-wrap flex-rows gap-4">
            <a href="{base}/realisations/auMontDieu"  class="glass element projet d-flex align-items-center justify-content-center flex-column gap-3 p-4">
                <h3 class="text-center">Au Mont Dieu</h3>
                <div>
                    <img src="{base}/realisations/auMontDieu/festivalAMD1.webp" class="w-100">
                </div>
            </a>
            <a href="{base}/realisations/webserviceAlphafold2" class="glass element projet d-flex align-items-center justify-content-center flex-column gap-3 p-4">
                <h3 class="text-center">Webservice NPSA-NG</h3>
                <div>
                    <img src="{base}/realisations/npsa-ng/NPSA-NG1.webp" class="w-100">
                </div>
            </a>
        </div>
    </div>
</div>

<style>
    h2 {
        text-align: center;
    }

    .projet {
        width: 80%;
    }

    @media (max-width: 992px) {
        .d-flex {
            flex-direction: column !important;
            align-items: center !important;
        }

        .leftSections, .rightSections {
            padding: 1.5rem 0 !important;
        }

        .projet {
            width: 85% !important;
        }
    }

    @media (max-width: 576px) {
        .projet {
            width: 100% !important;
        }
    }
</style>