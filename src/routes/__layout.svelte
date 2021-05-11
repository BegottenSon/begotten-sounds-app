<script>
    import Header from '$lib/Header/index.svelte';
    import '../app.css';
</script>

<Header />

<main>
	<slot></slot>
</main>


<style>
    main {
		align-items: center;
		box-sizing: border-box;
		display: grid;
		justify-content: center;
		margin: 0 auto;
		overflow-x: hidden;
		padding: 1em;
		width: 100%;
    }
</style>