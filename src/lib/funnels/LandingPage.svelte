<script>
    import FunnelButton from "./FunnelButton.svelte";
    import { images } from "../image-links/images";
    let link = "/music";
</script>
<section>
    <h1>
        <slot name="heading">Your Personal Mixing Engineer</slot>
    </h1>
    <h3>
        <slot name="tagline">Time to get you music soundng right</slot>
    </h3>
    <FunnelButton {link}>
        <span slot="cta">Yes! I want my free mix</span>
        <span slot="details"> Receive an email to upload your song for a FREE mix of a section of your song</span>
    </FunnelButton>
    <img src={images.bSonThrone} alt="Begotten Son sitting on a throne">
    <p>We need to get this together so we can have someting to post</p>
</section>

<style>
    section {
        display: grid;
        place-items: center;
        width: 90vw;
    }
    img {
        object-fit: cover;
        object-position: 0% 30%;
        width: 100%;
        height: 30%;
    }
</style>