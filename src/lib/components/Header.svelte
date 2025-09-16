<script>
    import {onMount } from "svelte"
    import {base} from "$app/paths";

    onMount(() => {
        const prefersDark = window.matchMedia('(prefers-color-scheme: dark)').matches;
        const savedTheme = localStorage.getItem('  ');

        if (savedTheme === 'dark' || (!savedTheme && prefersDark)) {
            document.body.classList.add('dark');
        }

        document.getElementById('dark-toggle').addEventListener('click', () => {
            document.body.classList.toggle('nuit')
            const theme = document.body.classList.contains('dark') ? 'dark' : 'light'
            localStorage.setItem('theme', theme)
        });
    })
</script>

<header class="container glass d-flex align-items-center justify-content-center m-3">
    
    <nav class="navbar navbar-expand-lg w-100">
        <div class="container-fluid">
            <div class="d-flex justify-content-between collapse navbar-collapse" id="navbarNav">
                <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                <li class="nav-item"><a class="nav-link" href="{base}/">Accueil</a></li>
                <li class="nav-item"><a class="nav-link" href="{base}/formation">Formation</a></li>
                <li class="nav-item"><a class="nav-link" href="{base}/competences">Compétences techniques</a></li>
                <li class="nav-item"><a class="nav-link" href="{base}/realisations">Réalisations</a></li>
                <li class="nav-item"><a class="nav-link" href="{base}/bts_sio">BTS SIO</a></li>
<!--                <li class="nav-item"><a class="nav-link" href="{base}/veille">Veille Technologique</a></li>-->
<!--                <li class="nav-item"><a class="nav-link" href="{base}/contact">Contact</a></li>-->
                </ul>

                <div class="d-flex align-items-center">
<!--                <button id="search-btn" class="btn btn-link text-light" aria-label="Rechercher">-->
<!--                    <i class="bi bi-search"></i>-->
<!--                </button>-->
                <button id="dark-toggle" class="btn btn-link text-light" aria-label="Activer/Désactiver le mode sombre">
                    <i class="bi bi-moon"></i>
                </button>
                </div>
            </div>
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
        height: 56px;
    }

    .container .nav-link {
        color: inherit !important;
    }

    li:hover {
        opacity: 0.6;
        transition: all 0.2s ease;
    }
</style>