<script>
    import Transition from "$lib/Transition.svelte";
    import MusicPlayer from "$lib/MusicPlayer/MusicPlayer.svelte";
    import { blur } from "svelte/transition";
    import { ring } from "$lib/SVG/artistBKG";

    let begottenMusic = false;

    function showBegottenMusic() {
        begottenMusic = !begottenMusic
    }

    let blurAmount = 6;
    let duration = 200;
</script>

<svelte:head>
    <title>Begotten Sounds Music</title>
</svelte:head>
<Transition>
<main>
    <h1>Music</h1>

    {#if begottenMusic}
    <div class="music-view" in:blur="{{amount: blurAmount, duration: duration}}">
        <h3 on:click={showBegottenMusic} class="close button">Close</h3>
        <MusicPlayer />
    </div>
    {:else}
    <div class="artists-view" in:blur="{{amount: blurAmount, duration: duration}}">
        <h3>Choose The Artist Below</h3>
        <div class="artists-list">
           <section class="bson" on:click={showBegottenMusic}>
                <h2>D. Brown the Begotten Son</h2>
                <img src="https://res.cloudinary.com/begottenson/image/upload/c_scale,h_500/v1619630498/Begotten%20Sounds/B_Son_Card_2_yfp0wz.png" alt="Artist D. Brown the Begotten Son" class="artists">
            </section>
            <section class="tykillzem" on:click={showBegottenMusic}>
                <h2>Tykillzem</h2>
                <img src="https://res.cloudinary.com/begottenson/image/upload/c_scale,h_500/v1621343074/Begotten%20Sounds/Ty-web_u1y8y8.png" alt="Tykillzem" class="artists">
            </section> 
        </div>        
    </div>     
    {/if}
</main>
</Transition>

<style>
    main {
        display: grid;
        justify-items: center;
        text-align: center;
    }

    .artists-list {
        display: flex;
        flex-wrap: wrap;
        gap: 1em;
        justify-content: center;
    }

    .bson {
        cursor: pointer;
        position: relative;
    }

    .artists {
        position: relative;
        /* clip-path: circle(); */
        height: 40vh;
    }

    .artists::after {
        background-image: url("data:image/svg+xml;charset=utf8,%3C?xml version='1.0' encoding='UTF-8' standalone='no'?%3E%3C!DOCTYPE svg PUBLIC '-//W3C//DTD SVG 1.1//EN' 'http://www.w3.org/Graphics/SVG/1.1/DTD/svg11.dtd'%3E%3Csvg width='100%25' height='100%25' viewBox='0 0 200 200' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink' xml:space='preserve' xmlns:serif='http://www.serif.com/' style='fill-rule:evenodd;clip-rule:evenodd;stroke-linejoin:round;stroke-miterlimit:2;'%3E%3Ccircle cx='100' cy='100' r='100' style='fill:rgb(235,235,235);'/%3E%3Cg id='ring' transform='matrix(0.980392,0,0,0.980392,1.96078,1.96078)'%3E%3Cpath d='M100,-2C43.705,-2 -2,43.705 -2,100C-2,156.295 43.705,202 100,202C156.295,202 202,156.295 202,100C202,43.705 156.295,-2 100,-2ZM100,2C154.088,2 198,45.912 198,100C198,154.088 154.088,198 100,198C45.912,198 2,154.088 2,100C2,45.912 45.912,2 100,2Z' style='fill:rgb(233,27,80);'/%3E%3C/g%3E%3C/svg%3E");
        content: "";
        height: 100%;
        width: 2em;
        position: absolute;
        top: 0;
        left: 0;
    }

    .music-view {
        display: flex;
        flex-direction: column;
    }
    
    .close {
        background-color: var(--white);
        background-image: none;
        color: var(--grey);
        align-self: center;
    }
</style>