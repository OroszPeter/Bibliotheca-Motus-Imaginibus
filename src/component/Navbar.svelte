<script>
    export let nightMode = false;
    let night_Mode = false;
    import { nightMode as nightModeStore } from '../store.js';

    // Állapot a lenyíló menühöz
    let isMenuOpen = false;

    function toggleLight() {
        nightModeStore.update(mode => !mode);
        night_Mode = !night_Mode;
    }

    function toggleMenu() {
        isMenuOpen = !isMenuOpen;
    }
</script>

<div class="d-flex flex-row w-100 h-25">
    <nav class="{night_Mode ? 'nightMode' : ''} w-100 py-2 h-100">
        <a href="/" class="first-link ms-4">
             <b>Bibliotheca Motus Imaginibus</b>
        </a>
        <a href="" class="ms-3" on:click={toggleMenu}>
            Menu
        </a>
        <!-- Lenygó tartalom, ha isMenuOpen igaz -->
        {#if isMenuOpen}
            <div class="{night_Mode ? 'nightMode' : ''} dropdown-menu w-100">
                <div>
                    <a href="/movies">Filmek</a><br>
                    <a href="/tv-shows">Sorozatok</a><br>
                    <a href="/about">Gyakran ismételt kérdések</a><br>
                </div>
            </div>
        {/if}
        <div class="{night_Mode ? 'nightMode' : ''} d-inline ms-3" id="search">
            <input class="m-0 w-50" type="text" placeholder="Keresés. . .">
            <a href="/result" class="m-0 p-0 sb"><i class="bi bi-search"></i></a>
        </div>
        <a href="/watchlist" class="ms-3">
            Watchlist
        </a>
        <a href="/login" class="ms-3">
            Bejelentkezés
        </a>
        <a href="" class="ms-3 me-4" on:click={toggleLight}>
            CC
        </a>
    </nav>
</div>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Lato:ital,wght@0,100;0,300;0,400;0,700;0,900&display=swap');

    a {
        text-decoration: none;
        color: #FEFFD2;
        font-family: "Lato", sans-serif;
        font-weight: 400;
        font-style: normal;
        font-size: 20px;
    }
    .dropdown-menu a{
        font-size: 20px;
    }
    
    nav {
        background-color: #FF7D29;
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
        background-color: #FFF2D7;
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
        background-color: black;
    }

    .nightMode a {
        color: white;
    }

    .nightMode .first-link {
        color: red;
    }

    .nightMode input {
        background-color: #444;
        color: white;
    }

    .nightMode .sb {
        color: white;
    }

    .nightMode #search {
        background-color: #444;
        border: 1px solid white;
    }

    .nightMode #search:focus-within {
        outline: 2px solid white;
    }

    /* Dropdown menü stílusa */
    .dropdown-menu {
        position: absolute;
        background-color: #FF7D29;
        border: 1px solid #FFF2D7;
        padding: 10px;
        border-radius: 5px;
        top: 40px; /* Ellenőrizzük ezt az értéket */
        left: 0px; /* Szükség szerint változtassuk meg */
        z-index: 9999; /* Nagyobb érték a biztos láthatóságért */
        display: block; /* Győződjünk meg róla, hogy a display értéke block */
    }

    .dropdown-item {
        display: block;
        padding: 5px 10px;
        color: #FEFFD2;
    }

    .dropdown-item:hover {
        background-color: #FFE0B3;
    }
</style>
