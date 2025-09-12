<script>
    import {onMount} from "svelte"
    import {base} from "$app/paths"

    onMount(() => {

        const sections = document.querySelectorAll('.section')
        sections.forEach(section => {
            setTimeout(() => {
                section.classList.add('mountEffect')
            }, 100)
        })
    })

        const headers = [
        "Gérer le patrimoine informatique",
        "Répondre aux incidents et aux demandes d'assistance et d'évolution",
        "Développer la présence en ligne de l'organisation",
        "Travailler en mode projet",
        "Mettre à disposition des utilisateurs un service informatique",
        "Organiser son développement professionnel"
        ]

        const rows = [
        { type: 'section', label: 'Projets personnels' },
        { type: 'row', label: "Développement du site web Au Mont Dieu", url: "/preuves/Festival_AuMontDieu.pdf", values: [false, true, false, false, false, false] },
        { type: 'section', label: 'Projets en cours de formation' },
        { type: 'row', label: "Dossier de certification", url: "/preuves/DossierCertification.pdf", values: [false, false, false, false, false, true] },
        { type: 'row', label: "Développement de présence en ligne", url: "/preuves/PresenceEnLigne_Immersicorp.pdf", values: [false, false, true, false, false, false] },
        { type: 'row', label: "Développement de l'application ResAppli", url: "/preuves/Application_ResAppli.pdf", values: [true, false, false, true, false, false] },
        { type: 'section', label: 'Projets durant le stage de première année' },
        { type: 'row', label: "Application web npsa-ng", url: "/preuves/Application_NPSA-NG.pdf", values: [false, false, false, false, true, false] }
        // { type: 'section', label: 'Projets durant le stage de seconde année' }
        ]
</script>

<section class="glass section topSections d-flex align-items-center justify-content-center flex-column my-4 p-4" id="realisations">
    <h1>Grille de compétences du BTS SIO</h1>
    <table class="table-bordered text-center mt-3">
        <thead>
        <tr>
            <th scope="col"></th>
            {#each headers as header}
                <th scope="col" class="fontEffect p-1">{header}</th>
            {/each}
        </tr>
        </thead>
        <tbody>
        {#each rows as row}
            {#if row.type === 'section'}
                <tr>
                    <td colspan={headers.length + 1} class="fontEffect">{row.label}</td>
                </tr>
            {:else}
                <tr>
                    <th scope="row" class="fontEffect p-1">
                        {#if row.url}
                            <a title="Lien vers la preuve" target="_blank" href={base}{row.url}>{row.label}</a>
                        {:else}
                            {row.label}
                        {/if}
                    </th>
                    {#each row.values as value}
                        <td class="fw-bold">{value ? 'X' : ''}</td>
                    {/each}
                </tr>
            {/if}
        {/each}
        </tbody>
    </table>
    <a class="glass section bottomSections text-center p-1 mt-3" href="{base}/preuves/tableauSyntheseOfficiel.pdf" target="_blank" style="width: 300px;">Grille de compétences officielle</a>
</section>

<style>
    .fontEffect {
        font-size: 0.95rem;
        text-shadow: 1px 1px 2px rgba(255, 255, 255, 0.25);
    }
</style>