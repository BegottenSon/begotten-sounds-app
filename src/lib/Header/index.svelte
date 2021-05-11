<script>
    import { page } from '$app/stores';
    import icon from './Icon.svg';

</script>

<header>
    <nav>
        <ul id="nav1">
            <li id="home" class:active={$page.path === '/'}><a sveltekit:prefetch href="/">Home</a></li>
            <li class:active={$page.path === '/music'}><a sveltekit:prefetch href="/music">Music</a></li>
            <li class:active={$page.path === '/begotten-tv'}><a sveltekit:prefetch href="/begotten-tv">Begotten TV</a></li>
        </ul>
    </nav>
    <a sveltekit:prefetch href="/" id="icon"><img src={icon} alt="Begotten Sounds Icon"></a>
    <nav id="nav2">
        <ul>
            <li class:active={$page.path === '/services'}><a sveltekit:prefetch href="/services">Services</a></li>
            <li class:active={$page.path === '/store'}><a sveltekit:prefetch href="/store">Store</a></li>
        </ul>
    </nav>  
</header>

<style>
    header {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        justify-items: center;
        justify-content: space-around;
        z-index: 20;
    }

    nav {
        display: flex;
    }

    ul {
        display: flex;
        position: relative;
        list-style: none;
        padding: 0;
    }

    ul li {
        margin: 0 1em;
        padding: 0;
    }

    ul:hover li:not(:hover){
        filter: brightness(0.4);
    }

    li {
        position: relative;
        transition: ease 300ms;
    }

    .active::after {
        content: "";
        height: 2px;
        width: 100%;
        position: absolute;
        bottom: -4px;
        left: 0;
        background-image: var(--gradient);
        transition: ease-in-out 400ms;
    }

    img {
        height: 2.5em;
    }

    @media (max-width: 480px) {
        header {
            background-color: var(--dark);
            bottom: 0;
            display: flex;
            font-size: 0.7em;
            justify-content: space-evenly;
            padding-block: 0.5em 1.4em;
            position: fixed;
            width: 97%;
        }

        ul {
            justify-content: end;
        }

        li a:not(.active a) {
            color: var(--white);
        }

        .active::after {
            height: 0;
            width: 0;
        }

        #home {
            display: none;
        }
        /* SETTINGS FOR THE ICON */
        img {
            height: 2.3em;
        }

        header > a {
            display: flex;
            align-items: center;
            justify-items: center;
            text-align: center;
        }
    }
</style>