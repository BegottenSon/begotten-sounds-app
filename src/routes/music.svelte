<script>
    import Transition from "$lib/Transition.svelte";
    import MusicPlayer from "$lib/MusicPlayer/MusicPlayer.svelte";

    let begottenMusic = false;

    function showBegottenMusic() {
        begottenMusic = !begottenMusic
    }
</script>

<svelte:head>
    <title>Begotten Sounds Music</title>
</svelte:head>
<Transition>
<main>
    <h1>Music</h1>

    {#if begottenMusic}
    <h3 on:click={showBegottenMusic} class="close button">Close</h3>
      <MusicPlayer />  
    {:else}
        <h3>Choose The Artist Below</h3>
        <section class="bson" on:click={showBegottenMusic}>
            <h2>D. Brown the Begotten Son</h2>
            <img src="https://res.cloudinary.com/begottenson/image/upload/c_scale,h_500/v1619630498/Begotten%20Sounds/B_Son_Card_2_yfp0wz.png" alt="Artist D. Brown the Begotten Son" class="artists">
        </section>
    {/if}
</main>
</Transition>

<style>
    main {
        text-align: center;
    }

    .bson {
        cursor: pointer;
        position: relative;
    }

    .bson:hover {
        
    }

    .artists {
        height: 40vh;
        box-shadow: 0 0 4em var(--grey-glass);
        /* clip-path: circle(40% at 40%); */
    }

    .close {
        background-color: var(--white);
        background-image: none;
        color: var(--grey);
        
    }
</style>