<div>
    <h3>
        <slot name="cta">Yes! I want my Product Now!</slot>
    </h3>
    <h4>
        <slot name="details">You pay only $97 down payment to get the ball rolling now!</slot>
    </h4>

</div>

<style>
    div {
        background-color: var(--red);
        border-radius: 8px;
        cursor: pointer;
        display: flex;
        flex-direction: column;
        place-items: center;
        padding: 1em;
    }

    div:hover {
        filter: saturate(1.2);
    }

    div:active {
        filter: saturate(0.9);
    }

    h3 {
        text-transform: uppercase;
        margin: 0.4em;
    }

    h4 {
        font-size: 0.7em;
        font-weight: lighter;
        margin: 0.4em;
    }
</style>