<script>
    import { createEventDispatcher } from 'svelte';

    const dispatch = createEventDispatcher();

    const icons = {
		play: "/images/play.png",
		pause: "/images/pause.png",
		rewind: "/images/rr.png",
		fwd: "/images/ff.png"
	};

    export let trackTitle = "Choose a Song";
    export let currentTimeDisplay;
    export let totalTimeDisplay;
    export let progress;
    export let isPlaying;

    $: fullRound = progress > 98 ? true : false;
    $: pauseSize = isPlaying ? true : false;

</script>
<main>
    <h2>{trackTitle}</h2>
    <section class="timeSection">
        <span id="progress-time">{currentTimeDisplay}</span>
        <span id="track-duration">{totalTimeDisplay}</span>
    </section>
    <section class="progress-bar">
        <span class="bar" class:fullRound style="width: {progress}%"></span>
    </section>
    
    <section class="controls">
        <button id="rewind" on:click={() => dispatch('rewind')}>
            <img src={icons.rewind} alt="rewind">
        </button>
        <button id="play" on:click={() => dispatch('playPause')}>
            <img src={isPlaying ? icons.pause : icons.play} class:pauseSize alt="play">
        </button>
        <button id="forward" on:click={() => dispatch('forward')}>
            <img src={icons.fwd} alt="forward">
        </button>
    </section>
</main>


<style>
    main {
        display: grid;
        place-items: center;
    }
    h2 {
        background-image: var(--gradient);
        background-color: var(--yellow);
        border-radius: 8px;
        color: var(--dark);
        padding: 0.4em;
        width: 70%;
    }
    /* CONTROLS */
    .controls {
        display: flex;
        justify-content: space-between;
        justify-self: normal;
    }
    button {
        background-color: transparent;
        background-image: none;
        margin: 0.6em;
        padding: 0;
        width: 30px;
    }

    button img {
        width: 100%;
    }

    .pauseSize {
        width: 30px;
    }

    /* PROGRESS BAR AND TIME */
    .timeSection {
        display: flex;
        justify-content: space-between;
        width: 100%;
    }

    .progress-bar {
        background-color: var(--grey-glass);
        border: 1px solid var(--grey);
        border-radius: 8px;
        cursor: pointer;
        display: flex;
        align-items: center;
        height: 12px;
        margin: 0.5em 0 0.5em;
        width: 100%;
    }

    .bar {
        background-color: var(--red);
        border-radius: 8px 0px 0px 8px;
        width: 0%;
        height: 12px;
    }

    .fullRound {
        border-radius: 8px;
        transition: ease 1s;
    }
</style>