<script>
    import Transition from "$lib/Transition.svelte";
    import LandingPage from "$lib/LandingPage.svelte";
</script>
<Transition>
<main>
    <h1>This is Services</h1>
    <LandingPage>
        <h1 slot="heading">Mixing Engineer</h1>
        <h3 slot="tagline">Your music deserves better care</h3>
    </LandingPage>
</main>    
</Transition>
