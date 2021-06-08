<script>
    export let link = "/";
</script>

<a href={link}>
    <span class="cta">
        <slot name="cta">Yes! I want my Product Now!</slot>
    </span>
    <span class="details">
        <slot name="details">You pay only $97 down payment to get the ball rolling now!</slot>
    </span>
</a>

<style>
    a {
        background-color: var(--red);
        border-radius: 8px;
        color: var(--white);
        display: flex;
        flex-direction: column;
        place-items: center;
        padding: 1em;
        width: 70%;
    }

    a:hover {
        filter: saturate(1.2);
    }

    a:active {
        filter: saturate(0.9);
    }

    .cta {
        font-size: 1.2em;
        text-transform: uppercase;
        font-weight: bold;
        margin: 0.4em;
    }

    .details {
        font-size: 0.7em;
        font-weight: lighter;
        margin: 0.4em;
    }
</style>