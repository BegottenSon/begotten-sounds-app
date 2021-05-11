<script>
    import { onMount, onDestroy } from 'svelte';
    import { fly } from 'svelte/transition';

    onMount(() => { transitionIn = true; });
    onDestroy(() => { transitionOut = true; });

    let transitionIn = false;
    let transitionOut = false;
    let transitionTime = 200
</script>

<style>
    div {
        position: relative;
    }
</style>

    {#if transitionIn || transitionOut}

    <div in:fly="{{y: 500, duaration: transitionTime, delay: transitionTime}}" out:fly="{{y: 500, duration: transitionTime}}">
        <slot></slot>
    </div>
        
    {/if}