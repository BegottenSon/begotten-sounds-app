<script>
    import ContentCard from "$lib/cards/ContentCard.svelte";
    import Transition from "$lib/Transition.svelte";
</script>

<svelte:head>
    <title>Begotten Sounds</title>
</svelte:head>
<Transition>
    <h1>Where Music Is Born</h1>
    <section class="content-section">
        <ContentCard
        picture = "https://res.cloudinary.com/begottenson/image/upload/c_scale,h_300/v1619630123/Begotten%20Sounds/BSon-on-throne_tqtm8x.jpg"
        headline = "#BegottenSonDay"
        description = "Listen to the Guiness World Record weekly project!"
        buttonTitle = "Play Now"
        />
        <ContentCard 
        picture = "https://res.cloudinary.com/begottenson/image/upload/v1619630457/Begotten%20Sounds/Creative_Discourse_zn5utl.jpg"
        headline = "Take Part in the Big Event"
        description = "Artists, Producers and Creatives. It's time to assemble!"
        buttonTitle = "Reserve Spot"
        link = "https://begotten.live/"
        target = "_blank"
        rel = "noopener noreferrer"
        />
        <ContentCard 
        picture = "https://res.cloudinary.com/begottenson/image/upload/v1619656777/Begotten%20Sounds/Atlas.removed_website_tbrs7i.png"
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
