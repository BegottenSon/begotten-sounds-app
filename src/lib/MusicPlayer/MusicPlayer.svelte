<script>
    import BSonPlaylist from "./Playlist.svelte";
    import { playlist } from "./BSonPlaylist.js";
    import Controls from "./Controls.svelte";

    // GET TRACK
    let trackIndex = 0;
    let audio = new Audio(playlist[trackIndex].url);
    let trackTitle = playlist[trackIndex].title;

    const loadTrack = () => {
        audio = new Audio(playlist[trackIndex].url);
        audio.onloadedmetadata = () => {
            totalTrackTime = audio.duration;
            updateTime();
        }
        trackTitle = playlist[trackIndex].title;
    }

    const autoPlayNextTrack = () => {
        if(trackIndex <= playlist.length - 1) {
            trackIndex += 1;
            loadTrack();
            audio.play();
            isPlaying = true;
            toggleTimeRunning();
        } else {
            trackIndex = 0;
            loadTrack();
            audio.play();
            isPlaying = true;
            toggleTimeRunning();
        }
    }
    //TRACK TIME AND PROGRESS BAR
    let totalTrackTime;

    audio.onloadedmetadata = () => {
        totalTrackTime = audio.duration;
        updateTime();
    }

    let totalTimeDisplay = " Loading...";
    let currentTimeDisplay = "0:00:00";
    let progress = 0;
    let trackTimer;

    function updateTime() {
        // totalTrackTime = audio.duration
        progress = audio.currentTime * (100 / totalTrackTime);

        let currHrs = Math.floor((audio.currentTime / 60) / 60);
        let currMins = Math.floor(audio.currentTime / 60);
        let currSecs = Math.floor(audio.currentTime - currMins * 60);

        let durHrs = Math.floor((totalTrackTime / 60) / 60);
        let durMins = Math.floor((totalTrackTime / 60) % 60);
        let durSecs = Math.floor(totalTrackTime - (durHrs * 60 * 60) - (durMins *60));

        if(currSecs < 10) currSecs = `0${currSecs}`;
        if(durSecs < 10) durSecs = `0${durSecs}`;
        if (currMins < 10) currMins = `0${currMins}`;
        if (durMins < 10) durMins = `0${durMins}`;

        currentTimeDisplay = `${currHrs}:${currMins}:${currSecs}`;
        totalTimeDisplay = `${durHrs}:${durMins}:${durSecs}`;
        if(audio.ended) {
            toggleTimeRunning();
            autoPlayNextTrack();
        }
    }

    const toggleTimeRunning = () => {
        if (audio.ended) {
            isPlaying = false;
            clearInterval(trackTimer);
        } else {
            trackTimer = setInterval(updateTime, 100);
        }
    }
    //CONTROLS
    let isPlaying = false;

    const playPause = () => {
        if (audio.paused) {
            toggleTimeRunning();
            audio.play();
            isPlaying = true;
        } else {
            toggleTimeRunning();
            audio.pause();
            isPlaying = false;
        }
    }

    const rewindAudio = () => audio.currentTime -= 15;
    const forwardAudio = () => audio.currentTime += 15;

    //PLAYLIST
    const handleTrack = (e) => {
        if (!isPlaying) {
            trackIndex = Number(e.target.dataset.trackId);
            loadTrack();
            playPause();
        } else {
            isPlaying = false;
            audio.pause();
            trackIndex = Number(e.target.dataset.trackId);
            loadTrack();
            playPause();
        }
    }
</script>

<main>
    <img src="https://res.cloudinary.com/begottenson/image/upload/c_scale,h_300/v1619630123/Begotten%20Sounds/BSon-on-throne_tqtm8x.jpg" alt="Begotten Son">
    <div>
        <Controls {isPlaying} {trackTitle} {currentTimeDisplay} {totalTimeDisplay} {progress} 
            on:playPause={playPause}
            on:rewind={rewindAudio}
            on:forward={forwardAudio}/>
        <BSonPlaylist 
            on:click={handleTrack}/>    
    </div>
    
    
</main>

<style>
    main {
        display: flex;
        flex-wrap: wrap;
        gap: 1.5em;
        justify-content: center;
    }

    img {
        border-radius: 8px;
        /* height: 30vh; */
    }

    div {
        border: solid 2px var(--grey);
        border-radius: 8px;
        padding: 1em;
        width: 60vw;
    }

    @media (max-width: 480px) {
        main {
            margin-bottom: 2em;
        }
    }
</style>