<script>
    export let picture = "https://res.cloudinary.com/begottenson/image/upload/c_scale,h_500/v1601428932/Begotten%20Sounds/Main_BSN_Logo.png";
    export let headline = "The is the Headline";
    export let description = "This is the short description";
    export let buttonTitle = "Click Me";
    export let link = "#";
    export let target = "";
    export let rel = ""

</script>

<main>
    <img src={picture} alt="All Music Pic Here">
    <h1>{headline}</h1>
    <p>{description}</p>
    <a href={link} target={target} rel={rel} class="button">{buttonTitle}</a>
</main>

<style>
    main {
        background-color: var(--dark);
        box-shadow: inset 0 0 10px 1px rgb(12, 4, 9);
        background-image: radial-gradient(#0f0e0e, #1a1a1a);
        border-radius: 12px;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: space-between;
        padding: 2em;
        width: clamp(20vw, 300px, 400px);
    }

    img {
        border-radius: 8px;
        height: 300px;
        object-fit: cover;
        width: clamp(100px, 300px, 400px);
    }

    p {
        margin-block-end: 2em;
    }

    .button {
        background-image: var(--gradient);
        border: none;
        border-radius: 8px;
        color: var(--white);
        cursor: pointer;
        margin-block-end: 1em;
        padding: 1em 4em;
        transition: cubic-bezier(.79,.01,.48,1) 50ms;
    }

    .button:active {
        background-image: var(--active-gradient);
        /* filter: brightness(0.9); */
        transform: scale(0.95);
    }
</style>