<script>
    import ContentCard from "$lib/cards/ContentCard.svelte";
    import Transition from "$lib/Transition.svelte";
    import { images } from "$lib/image-links/images";
</script>

<svelte:head>
    <title>Begotten Sounds</title>
</svelte:head>
<Transition>
    <h1>Where Music Is Born</h1>
    <section class="content-section">
        <ContentCard
        picture = {images.bSonThrone300}
        headline = "#BegottenSonDay"
        description = "Listen to the Guiness World Record weekly project!"
        buttonTitle = "Play Now"
        />
        <ContentCard 
        picture = {images.creativeDiscourse}
        headline = "Take Part in the Big Event"
        description = "Artists, Producers and Creatives. It's time to assemble!"
        buttonTitle = "Reserve Spot"
        link = "https://begotten.live/"
        target = "_blank"
        rel = "noopener noreferrer"
        />
        <ContentCard 
        picture = {images.atlasRemoved}
        headline = "Atlas.removed Album"
        description = "Discover the story of Atlas and his new found freedom..."
        buttonTitle = "Listen Now"
        />
    </section>
</Transition>
<style>
    h1 {
        text-align: center;
    }

    .content-section {
        display: flex;
        flex-wrap: wrap;
        gap: 1em;
        justify-content: center;
    }
</style>
