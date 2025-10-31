<script>
    import "../app.css";
    import Header from "$lib/components/Header.svelte";
    import Footer from "$lib/components/Footer.svelte";

</script>

<Header />

<main class="d-flex align-items-center justify-content-center flex-column w-100 gap-3" style="flex:1;">
    <slot />
</main>

<Footer />