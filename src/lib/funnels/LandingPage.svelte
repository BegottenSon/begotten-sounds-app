<script>
    import FunnelButton from "./FunnelButton.svelte";
</script>
<section>
    <h1>
        <slot name="heading">Your Personal Mixing Engineer</slot>
    </h1>
    <h3>
        <slot name="tagline">Time to get you music soundng right</slot>
    </h3>
    <FunnelButton>
        <span slot="cta">Yes! I want my free mix</span>
        <span slot="details"> Receive an email to upload your song for a FREE mix of a section of your song</span>
    </FunnelButton>

</section>

