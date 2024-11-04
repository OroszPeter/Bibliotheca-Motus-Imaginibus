<script>
    export let nightMode = false; // Átadott prop
    let night_Mode = false;
    import { nightMode as nightModeStore } from '../store.js';
    
    function toggleLight() {
        nightModeStore.update(mode => !mode);
        night_Mode = !night_Mode;
    }
    

</script>

<div class="d-flex flex-row w-100 h-25">
    <nav class="{night_Mode ? 'nightMode' : ''} w-100 py-2 h-100">
        <a href="/" class="first-link ms-4">
             <b>Bibliotheca Motus Imaginibus</b>
        </a>
        <a href="/" class="ms-4">
            Menu
        </a>
        <div class="{night_Mode ? 'nightMode' : ''} d-inline ms-4" id="search">
            <input class="m-0 w-50" type="text" placeholder="Keresés. . .">
            <a href="/result" class="m-0 p-0 sb"><i class="bi bi-search"></i></a>
        </div>
        <a href="/watchlist" class="ms-4">
            Watchlist
        </a>
        <a href="/login" class="ms-4">
            Bejelentkezés
        </a>
        <a href="" class="ms-4 me-4" on:click={toggleLight}>
            CC
        </a>
    </nav>
</div>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Lato:ital,wght@0,100;0,300;0,400;0,700;0,900;1,100;1,300;1,400;1,700;1,900&display=swap');

    a {
        text-decoration: none;
        color: #FEFFD2; /* Eredeti szín */
        font-family: "Lato", sans-serif;
        font-weight: 400;
        font-style: normal;
    }
    
    nav {
        background-color: #FF7D29; /* Eredeti szín */
    }

    button {
        border: none;
        background-color: #FFF2D7;
        height: 21px;
    }

    input {
        border: none;
        background-color: #FFF2D7;
        height: 21px;
        outline: none;
    }

    #search {
        background-color: #FFF2D7; /* Eredeti szín */
        height: 21px;
        border-radius: 10px;
        padding: 1px 10px;
    }

    #search:focus-within {
        outline: 2px solid black;
        border-radius: 10px;
    }

    .sb {
        color: black;
    }

    .nightMode {
        background-color: black; /* A nav új háttérszíne éjszakai üzemmódban */
    }

    .nightMode a {
        color: white; /* A linkek új színe éjszakai üzemmódban */
    }

    .nightMode .first-link {
        color: red; /* Az első link színe piros éjszakai üzemmódban */
    }

    .nightMode input {
        background-color: #444; /* Kereső input háttérszíne éjszakai üzemmódban */
        color: white; /* Kereső input szöveg színe éjszakai üzemmódban */
    }

    .nightMode .sb {
        color: white; /* Kereső ikon színe éjszakai üzemmódban */
    }

    /* Kereső div éjszakai üzemmódban */
    .nightMode #search {
        background-color: #444; /* Kereső div háttérszíne éjszakai üzemmódban */
        border: 1px solid white; /* Kereső div kerete éjszakai üzemmódban */
    }

    .nightMode #search:focus-within {
        outline: 2px solid white; /* Kereső div fókusz kerete éjszakai üzemmódban */
    }
</style>
