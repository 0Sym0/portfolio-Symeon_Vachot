<script>
    import {onMount } from "svelte"
    import {base} from "$app/paths";
    import { afterNavigate } from '$app/navigation';

    let darkMode = false;
    let isMobile = false;

    onMount(() => {
        const savedTheme = localStorage.getItem('theme');
        if (savedTheme === 'dark') {
            darkMode = true;
            document.body.classList.add('nuit');
        }

        const checkMobile = () => {
            isMobile = window.matchMedia('(max-width: 800px)').matches;
        };
        checkMobile();
        window.addEventListener('resize', checkMobile);
        return () => window.removeEventListener('resize', checkMobile);
    });

    function toggleTheme() {
        darkMode = !darkMode;
        document.body.classList.toggle('nuit', darkMode);
        localStorage.setItem('theme', darkMode ? 'dark' : 'light');
    }

    function toggleNavBar() {
        const burgerMenu = document.getElementById("burgerMenu");
        const crossMenu = document.getElementById("crossMenu");
        const menu = document.getElementById("menu");


        burgerMenu.classList.toggle('hideMenu');
        crossMenu.classList.toggle('hideMenu');
        menu.classList.toggle('hideMenu');

    }

    afterNavigate(() => {
        const menu = document.getElementById("menu");
        const burgerMenu = document.getElementById("burgerMenu");
        const crossMenu = document.getElementById("crossMenu");

        if (!menu || !burgerMenu || !crossMenu) return;

        // Forcer fermeture du menu au changement de page
        menu.classList.add('hideMenu');
        crossMenu.classList.add('hideMenu');
        burgerMenu.classList.remove('hideMenu');
    });
</script>

<header class="container glass d-flex align-items-center justify-content-center m-3">
    <nav class="w-100 d-flex align-items-start justify-content-between">
        <div class="d-flex align-items-start justify-content-center flex-column">
            {#if isMobile }
                <i id="burgerMenu" class="bi bi-list burgerMenu" on:click={toggleNavBar}></i>
                <i id="crossMenu" class="bi bi-x burgerMenu hideMenu" on:click={toggleNavBar}></i>
                <ul id ="menu" class="d-flex align-items-start justify-content-center flex-column navbar-nav hideMenu">
                    <li class="nav-item"><a class="nav-link" href="{base}/">Accueil</a></li>
                    <li class="nav-item"><a class="nav-link" href="{base}/formation">Formation</a></li>
                    <li class="nav-item"><a class="nav-link" href="{base}/competences">Compétences techniques</a></li>
                    <li class="nav-item"><a class="nav-link" href="{base}/realisations">Réalisations</a></li>
                    <li class="nav-item"><a class="nav-link" href="{base}/bts_sio">BTS SIO</a></li>
                    <!-- <li class="nav-item"><a class="nav-link" href="{base}/veille">Veille Technologique</a></li>-->
                    <!-- <li class="nav-item"><a class="nav-link" href="{base}/contact">Contact</a></li>-->
                </ul>
            {:else}
                <ul class="d-flex align-items-center justify-content-center flex-row gap-4 navbar-nav">
                    <li class="nav-item"><a class="nav-link" href="{base}/">Accueil</a></li>
                    <li class="nav-item"><a class="nav-link" href="{base}/formation">Formation</a></li>
                    <li class="nav-item"><a class="nav-link" href="{base}/competences">Compétences techniques</a></li>
                    <li class="nav-item"><a class="nav-link" href="{base}/realisations">Réalisations</a></li>
                    <li class="nav-item"><a class="nav-link" href="{base}/bts_sio">BTS SIO</a></li>
                    <!-- <li class="nav-item"><a class="nav-link" href="{base}/veille">Veille Technologique</a></li>-->
                    <!-- <li class="nav-item"><a class="nav-link" href="{base}/contact">Contact</a></li>-->
                </ul>
            {/if}
        </div>
        <div class="d-flex align-items-center">
            <!-- <button id="search-btn" class="btn btn-link text-light" aria-label="Rechercher">-->
            <!-- <i class="bi bi-search"></i>-->
            <!-- </button>-->
            <button class="btn btn-link text-light nav-item" on:click={toggleTheme} aria-label="Basculer le mode">
                {#if darkMode}
                    <i class="bi bi-sun" ></i>
                {:else}
                    <i class="bi bi-moon icon-moon"></i>
                {/if}
            </button>
        </div>
    </nav>
</header>

<style>
    body.dark {
        --bg: #121212;
        --text-color: #f0f0f0;
        --glass-bg: rgba(255, 255, 255, 0.05);
        --glass-border: rgba(255, 255, 255, 0.1);
    }

    .container {
        max-width: 1200px;
        width: 97%;
        padding: 0.5rem 1rem;
    }

    .container .nav-link {
        color: inherit !important;
    }

    .icon-moon {
        color: black;
    }

    .burgerMenu {
        font-size: 1.7rem;
        cursor: pointer;
    }

    .hideMenu {
        display: none !important;
    }

    li:hover {
        opacity: 0.6;
        transition: all 0.2s ease;
    }
</style>