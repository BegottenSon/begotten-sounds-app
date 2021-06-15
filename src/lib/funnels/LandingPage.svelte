<script>
    import FunnelButton from "./FunnelButton.svelte";
    import MixForm from "../forms/MixForm.svelte";
    import { images } from "../image-links/images";
</script>
<section>
    <h1>
        <slot name="heading">Your Personal Mixing Engineer</slot>
    </h1>
    <h3>
        <slot name="tagline">Time to get you music soundng right</slot>
    </h3>
    <div class="btn">
    <FunnelButton>
        <span slot="cta">Yes! I want my free mix</span>
        <span slot="details"> Receive an email to upload your song for a FREE mix of a section of your song</span>
    </FunnelButton>    
    </div>
    <div>
      <MixForm />  
    </div>
    
    <!-- <div class="klaviyo-form-Ue7T5f"></div> -->
    
    <img src={images.bSonThrone} alt="Begotten Son sitting on a throne" class="full-bleed">
    <p>We need to get this together so we can have someting to post</p>
</section>

<style>
    section {
        display: grid;
        grid-template-columns: 1fr minmax(65ch, 100%) 1fr;
        place-items: center;
        width: 100%;
    }

    section > * {
        grid-column: 2;
    }

    .btn {
        display: flex;
        justify-content: center;
    }

    img {
        grid-column: 1/-1;
        object-fit: cover;
        object-position: 0% 30%;
        width: 100%;
        height: 30vh;
    }

    @media(max-width: 480px) {
        section {
            grid-template-columns: 1fr 1fr 1fr;
        }
    }
</style>