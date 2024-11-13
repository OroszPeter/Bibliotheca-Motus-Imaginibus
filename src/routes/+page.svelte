<script>
    import { nightMode } from '../store.js'; // Importáljuk a nightMode store-t
    import { onMount } from 'svelte';

    let isRendered = false; // Ezzel az állapottal biztosíthatod, hogy csak egyszer renderelje a komponenst.

    onMount(() => {
        isRendered = true; // Ha betöltődött, egyszerűen `true` értékre állítjuk.
    });

    let isMenuOpen = false;
    function toggleMenu() {
        isMenuOpen = !isMenuOpen;
    }
</script>

{#if isRendered}
<main class="{ $nightMode ? 'nightMode' : '' } ">
    <div class="container">
        <!-- Első Carousel (3 képpel) -->
        <h1 class="pt-5 ps-3">Új filmek</h1>
        <div id="carouselExample1" class="carousel slide" data-bs-ride="carousel">
            <div class="carousel-inner">
                <div class="carousel-item active">
                    <div class="d-flex justify-content-center">
                        <img src="https://via.placeholder.com/800x400" class="d-block w-75" alt="Kép 1">
                    </div>
                    <div class="carousel-caption d-none d-md-block">
                        <h5>Film 1</h5>
                    <p>Műfaj</p>
                </div>
            </div>
            <div class="carousel-item">
                <div class="d-flex justify-content-center">
                    <img src="https://via.placeholder.com/800x400" class="d-block w-75" alt="Kép 2">
                </div>
                <div class="carousel-caption d-none d-md-block">
                    <h5>Film 2</h5>
                    <p>Műfaj</p>
                </div>
            </div>
            <div class="carousel-item">
                <div class="d-flex justify-content-center">
                    <img src="https://via.placeholder.com/800x400" class="d-block w-75" alt="Kép 3">
                </div>
                <div class="carousel-caption d-none d-md-block">
                    <h5>Film 3</h5>
                    <p>Műfaj</p>
                </div>
            </div>
        </div>
            <button class="carousel-control-prev" type="button" data-bs-target="#carouselExample1" data-bs-slide="prev">
                <span class="carousel-control-prev-icon" aria-hidden="true"></span>
                <span class="visually-hidden">Előző</span>
            </button>
            <button class="carousel-control-next" type="button" data-bs-target="#carouselExample1" data-bs-slide="next">
                <span class="carousel-control-next-icon" aria-hidden="true"></span>
                <span class="visually-hidden">Következő</span>
            </button>
        </div>

        <h1 class="pt-5 ps-3">Új sorozatok</h1>
        <div id="carouselExample3" class="carousel slide" data-bs-ride="carousel">
            <div class="carousel-inner">
                <div class="carousel-item active">
                    <div class="d-flex justify-content-center">
                        <img src="https://via.placeholder.com/800x400" class="d-block w-75" alt="Kép 1">
                    </div>
                    <div class="carousel-caption d-none d-md-block">
                        <h5>Sorozat 1</h5>
                        <p>Műfaj</p>
                    </div>
                </div>
                <div class="carousel-item">
                    <div class="d-flex justify-content-center">
                        <img src="https://via.placeholder.com/800x400" class="d-block w-75" alt="Kép 2">
                    </div>
                    <div class="carousel-caption d-none d-md-block">
                        <h5>Sorozat 2</h5>
                        <p>Műfaj</p>
                    </div>
                </div>
                <div class="carousel-item">
                    <div class="d-flex justify-content-center">
                        <img src="https://via.placeholder.com/800x400" class="d-block w-75" alt="Kép 3">
                    </div>
                    <div class="carousel-caption d-none d-md-block">
                        <h5>Sorozat 3</h5>
                        <p>Műfaj</p>
                    </div>
                </div>
            </div>
            <button class="carousel-control-prev" type="button" data-bs-target="#carouselExample3" data-bs-slide="prev">
                <span class="carousel-control-prev-icon" aria-hidden="true"></span>
                <span class="visually-hidden">Előző</span>
            </button>
            <button class="carousel-control-next" type="button" data-bs-target="#carouselExample3" data-bs-slide="next">
                <span class="carousel-control-next-icon" aria-hidden="true"></span>
                <span class="visually-hidden">Következő</span>
            </button>
        </div>

        <h1 class="pt-5 ps-3">Népszerű filmek, sorozatok</h1>
        <div id="carouselExample2" class="carousel slide" data-bs-interval="false">
            <div class="carousel-inner">
                <div class="carousel-item active">
                    <div class="d-flex justify-content-around gap-3"> <!-- A justify-content-around egyenlő távolságot biztosít -->
                        {#each Array(5).fill(0) as _, index}
                            <div class="col text-center carousel-item-wrapper">
                                <img src="https://i.twic.pics/v1/placeholder:500x600" class="d-block" alt="Kép {index + 1}">
                                <div class="carousel-caption position-static">
                                    <h5  class="{ $nightMode ? 'nightMode' : '' } nfs-h5">Cím {index + 1}</h5>
                                </div>
                            </div>
                        {/each}
                    </div>
                </div>
                <div class="carousel-item">
                    <div class="d-flex justify-content-around gap-3">
                        {#each Array(5).fill(0) as _, index}
                            <div class="col text-center carousel-item-wrapper">
                                <img src="https://i.twic.pics/v1/placeholder:500x600" class="d-block" alt="Kép {index + 6}">
                                <div class="carousel-caption position-static">
                                    <h5 class="{ $nightMode ? 'nightMode' : '' } nfs-h5">Cím {index + 6}</h5>
                                </div>
                            </div>
                        {/each}
                    </div>
                </div>
            </div>
            <button class="carousel-control-prev" type="button" data-bs-target="#carouselExample2" data-bs-slide="prev">
                <span class="carousel-control-prev-icon" aria-hidden="true"></span>
                <span class="visually-hidden">Előző</span>
            </button>
            <button class="carousel-control-next" type="button" data-bs-target="#carouselExample2" data-bs-slide="next">
                <span class="carousel-control-next-icon" aria-hidden="true"></span>
                <span class="visually-hidden">Következő</span>
            </button>
        </div>
    </div>
</main>
{/if}

<style>
    main{
        background-color: #FFF2D7; /* Eredeti háttérszín */
    }
    body {
        transition: background-color 0.3s, color 0.3s; /* Színváltozás animálása */
    }
    .nightMode {
        background-color: #444444; /* Háttérszín sötét módban */
        color: #ffffff; /* Szöveg színe sötét módban */
    }

    h1 {
        color: #FFBF78; /* Cím színe világos módban */
    }

    .nightMode h1 {
        color: red; /* Cím színe sötét módban */
    }

    /* Carousel kép stílus */
    .carousel-inner .col img {
        max-height: 310px;
    }

    .carousel-caption.position-static {
        position: static;
        color: #333;
        font-size: 1rem;
        padding-top: 5px;
    }

    .nightMode .carousel-caption.position-static {
        color: white; /* Sötét módban a felirat színe */
    }

    .carousel-item-wrapper {
        padding: 0 10px;
        flex: 1 1 0;
    }
</style>
