<script>
    import { playlist } from "./BSonPlaylist.js"
</script>

<section class="playlist">
    <ul>
        {#each playlist as {title}, i}
            <li data-track-id={i} on:click>
                {title}
            </li>
        {/each}
    </ul>
</section>

<style>
    ul {
        list-style: none;
        margin: 0;
        padding: 0;
    }

    li {
		line-height: 150%;
		border-bottom: 2px solid var(--grey);
		cursor: pointer;
        padding-block: 1em 0.2em;
        text-align: left;
	}

    li:active, li:hover {
		background-color: var(--grey);
	}
</style>