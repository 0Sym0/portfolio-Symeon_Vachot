<script>
    import { onMount } from "svelte";
    import { page } from "$app/stores";
    import { base } from "$app/paths";

    $: pathSegments = $page.url.pathname
        .replace(new RegExp(`^${base}`), '')
        .split('/')
        .filter(Boolean);

    $: breadcrumbs = pathSegments.map((segment, index) => {
        const url = `${base}/` + pathSegments.slice(0, index + 1).join('/');

        let name = decodeURIComponent(segment);
        name = name.replace(/([a-zéàèù])([A-Z])/g, '$1 $2');
        name = name.replace(/-/g, ' ');
        name = name.charAt(0).toUpperCase() + name.slice(1);
        return { name, url };
    });

    onMount(() => {
        const sections = document.querySelectorAll('.section');
        sections.forEach(section => {
            setTimeout(() => {
                section.classList.add('mountEffect');
            }, 100);
        });
    });
</script>

<section class="glass section topSections my-4 p-4 d-flex flex-column" id="realisations">

    {#if pathSegments.length > 1}
        <nav aria-label="breadcrumb" class="breadcrumb-container mb-3">
            <a href="{base}/">Accueil</a>
            {#each breadcrumbs as crumb, i}
                <span class="separator">></span>
                {#if i === breadcrumbs.length - 1}
                    <span class="current" aria-current="page">{crumb.name}</span>
                {:else}
                    <a href={crumb.url}>{crumb.name}</a>
                {/if}
            {/each}
        </nav>
    {/if}

    <h1 class="m-4 text-center">Réalisations</h1>

    <slot />
</section>
<style>
    .breadcrumb-container {
        display: flex;
        align-items: center;
        flex-wrap: wrap; /* Gère les petits écrans si le fil est trop long */
        gap: 0.5rem;
        font-size: 0.95rem;
        opacity: 0.9;
    }

    .breadcrumb-container a {
        text-decoration: none;
        color: inherit;
        transition: opacity 0.2s ease, text-decoration 0.2s ease;
    }

    .breadcrumb-container a:hover {
        text-decoration: underline;
        opacity: 1;
    }

    .breadcrumb-container .separator {
        opacity: 0.5;
        user-select: none;
    }

    .breadcrumb-container .current {
        font-weight: bold;
        opacity: 1;
    }

    @media (max-width: 576px) {
        .breadcrumb-container {
            font-size: 0.85rem;
            justify-content: center;
        }
    }
</style>