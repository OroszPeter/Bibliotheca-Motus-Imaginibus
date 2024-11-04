<script>
    import { nightMode } from '../store.js'; // Importáld a nightMode store-t
</script>

<main class="{ $nightMode ? 'nightMode' : '' } vh-100">
    <h1>Főoldal</h1>
</main>

<style>
    main {
        background-color: #FFF2D7; /* Eredeti háttérszín */
        transition: background-color 0.3s; /* Simább átmenet */
    }

    .nightMode {
        background-color: #444444; /* Háttérszín sötét módban */
    }

    h1 {
        color: #FFBF78; /* Cím színe */
    }
    .nightMode h1{
        color: red;
    }
</style>
