<script>
    import Header from '$lib/Header/index.svelte';
    import '../app.css';
</script>

<Header />

<main>
	<slot></slot>
	<!-- Drip -->
	<script type="text/javascript">
		var _dcq = _dcq || [];
		var _dcs = _dcs || {};
		_dcs.account = '2600038';
	
		(function() {
		var dc = document.createElement('script');
		dc.type = 'text/javascript'; dc.async = true;
		dc.src = '//tag.getdrip.com/2600038.js';
		var s = document.getElementsByTagName('script')[0];
		s.parentNode.insertBefore(dc, s);
		})();
	</script>
  <!-- end Drip -->  
</main>


<style>
    main {
		align-items: center;
		box-sizing: border-box;
		display: grid;
		margin: 0 auto;
		overflow-x: hidden;
		width: 100%;
    }
</style>