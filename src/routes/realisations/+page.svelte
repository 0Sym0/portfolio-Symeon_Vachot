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

<div class=" d-flex justify-content-center align-items-start gap-4 flex-row w-100">
    <div class="section leftSections d-flex justify-content-around flex-column w-100 px-3 py-4">
        <h2 class="mb-4">Projets académiques</h2>
        <div class="containerCompetences d-flex align-items-center justify-content-center flex-wrap flex-rows gap-4">
            <a href="/realisations/dossierDeCertification" class="glass element projet d-flex align-items-center justify-content-center flex-column gap-3 p-4">
               <h3>Dossier de certification</h3>
                <div>
                      <img src="/realisations/certification/dossierDeCertification1.png" class="w-100">
                </div>
            </a>
            <a href="/realisations/presenceEnLigne" class="glass element projet d-flex align-items-center justify-content-center flex-column gap-3 p-4">
                <h3>Présence en ligne</h3>
                <div>
                    <img src="/realisations/presenceEnLigne/immersicorp1.png" class="w-100">
                </div>
            </a>
            <a href="/realisations/resAppli"  class="glass element projet d-flex align-items-center justify-content-center flex-column gap-3 p-4">
                <h3>Application ResAppli</h3>
                <div>
                    <img src="/realisations/resappli/resappli1.png" class="w-100">
                </div>
            </a>
        </div>
    </div>
    <div class="section rightSections d-flex justify-content-around flex-column w-100 px-3 py-4">
        <h2 class="mb-4">Projets professionnels</h2>
        <div class="containerCompetences d-flex align-items-center justify-content-center flex-wrap flex-rows gap-4">
            <a href="/realisations/auMontDieu"  class="glass element projet d-flex align-items-center justify-content-center flex-column gap-3 p-4">
                <h3>Au Mont Dieu</h3>
                <div>
                    <img src="/realisations/auMontDieu/festivalAMD1.png" class="w-100">
                </div>
            </a>
            <a href="/realisations/webserviceAlphafold2" class="glass element projet d-flex align-items-center justify-content-center flex-column gap-3 p-4">
                <h3>Webservice NPSA-NG</h3>
                <div>
                    <img src="/realisations/npsa-ng/NPSA-NG1.png" class="w-100">
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
</style>