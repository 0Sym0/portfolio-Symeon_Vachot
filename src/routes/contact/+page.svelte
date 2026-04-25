<script>
    import { onMount } from "svelte";

    let nom = '';
    let prenom = '';
    let sujet = '';
    let message = '';
    let statusMsg = '';
    let isSending = false;

    onMount(() => {
        const sections = document.querySelectorAll('.section')
        sections.forEach(section => {
            setTimeout(() => {
                section.classList.add('mountEffect')
            }, 100);
        });
    });

    async function handleSubmit() {
        isSending = true;
        statusMsg = '';

        try {
            const res = await fetch('https://api.web3forms.com/submit', {
                method: 'POST',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify({
                    access_key: "ca3055b5-6876-4ae8-bedb-52f7e6622f9d",
                    subject: `Portfolio - Nouvelle demande : ${sujet}`,
                    from_name: `${prenom} ${nom}`,
                    message: message
                })
            });

            if (res.ok) {
                statusMsg = 'success';
                nom = ''; prenom = ''; sujet = ''; message = '';
            } else {
                statusMsg = 'error';
            }
        } catch (err) {
            statusMsg = 'error';
        } finally {
            isSending = false;
        }
    }
</script>

<section class="glass section topSections my-4 p-4" id="contact">
    <h1 class="text-center">Me contacter</h1>
    <p class="text-center mb-4">Une demande de <b>prestation web/mobile</b> ou une <b>suggestion</b> pour ce portfolio ?<br>Discutons-en !</p>

    <form on:submit|preventDefault={handleSubmit} class="contact-form">
        <div class="row gap-3 mb-3">
            <div class="col d-flex flex-column">
                <label for="prenom">Prénom</label>
                <input type="text" id="prenom" bind:value={prenom} required class="glass-input">
            </div>
            <div class="col d-flex flex-column">
                <label for="nom">Nom</label>
                <input type="text" id="nom" bind:value={nom} required class="glass-input">
            </div>
        </div>

        <div class="d-flex flex-column mb-3">
            <label for="sujet">Sujet</label>
            <select id="sujet" bind:value={sujet} required class="glass-input">
                <option value="" disabled selected>Choisissez un sujet...</option>
                <option value="Prestation Site/App Web">Création d'un site ou d'une application Web</option>
                <option value="Prestation App Mobile">Création d'une application Mobile</option>
                <option value="Amélioration Portfolio">Recommandation d'amélioration du portfolio</option>
                <option value="Autre">Autre demande</option>
            </select>
        </div>

        <div class="d-flex flex-column mb-4">
            <label for="message">Message</label>
            <textarea id="message" bind:value={message} rows="5" required class="glass-input"></textarea>
        </div>

        <div class="text-center">
            <button type="submit" class="glass-btn" disabled={isSending}>
                {isSending ? 'Envoi en cours...' : 'Envoyer le message'}
            </button>
        </div>

        {#if statusMsg === 'success'}
            <p class="msg-success text-center mt-3">Votre message a été envoyé avec succès !</p>
        {:else if statusMsg === 'error'}
            <p class="msg-error text-center mt-3">Une erreur est survenue lors de l'envoi du message.</p>
        {/if}
    </form>
</section>

<style>
    .contact-form {
        max-width: 800px;
        margin: 0 auto;
    }

    .row {
        display: flex;
    }

    .col {
        flex: 1;
    }

    label {
        margin-bottom: 0.5rem;
        font-weight: 500;
    }

    /* Style qui s'adapte à ton effet 'glass' */
    .glass-input {
        background: rgba(255, 255, 255, 0.2);
        border: 1px solid rgba(255, 255, 255, 0.3);
        border-radius: 8px;
        padding: 0.8rem;
        color: inherit;
        font-family: inherit;
        outline: none;
        transition: border-color 0.3s;
    }

    .glass-input:focus {
        border-color: rgba(255, 255, 255, 0.8);
        background: rgba(255, 255, 255, 0.3);
    }

    .glass-input option {
        background: #333; /* Ajuste selon ton thème clair/sombre car les options héritent mal du glass */
        color: white;
    }

    .glass-btn {
        background: rgba(255, 255, 255, 0.2);
        border: 1px solid rgba(255, 255, 255, 0.5);
        padding: 0.8rem 2rem;
        border-radius: 8px;
        cursor: pointer;
        font-weight: bold;
        transition: all 0.3s ease;
    }

    .glass-btn:hover:not(:disabled) {
        background: rgba(255, 255, 255, 0.4);
    }

    .glass-btn:disabled {
        opacity: 0.5;
        cursor: not-allowed;
    }

    .msg-success {
        color: #00cc4c;
        font-weight: bold;
    }

    .msg-error {
        color: #a31212;
        font-weight: bold;
    }

    @media (max-width: 576px) {
        .row {
            flex-direction: column;
        }
    }
</style>